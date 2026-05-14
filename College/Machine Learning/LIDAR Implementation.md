```cpp
int main (int argc, char **argv)
{
	ros::init (argc, argv, "yolo_lidar_ros1");
	ros::NodeHandle nh("~");
	float ground_level, leaf_size, cluster_tolerance, X_cut;
	double truncate_threshold, bbox_rescale;
	int MinClusterSize;
	nh.param<float>("ground_level", ground_level, -2.0);
	nh.param<float>("leaf_size", leaf_size, 0.1);
	nh.param<float>("cluster_tolerance", cluster_tolerance, 0.35);
	nh.param<double>("truncate_threshold", truncate_threshold, 0.2);
	nh.param<double>("bbox_rescale", bbox_rescale, 0.9);
	nh.param<int>("MinClusterSize", MinClusterSize, 20);
	ROS_INFO("Parameters: ground_level:[%f], leaf_size:[%f], cluster_tolerance:[%f], MinClusterSize:[%d], truncate_threshold:[%f], bbox_rescale:[%f]", ground_level, leaf_size, cluster_tolerance, MinClusterSize, truncate_threshold, bbox_rescale);
	pub = nh.advertise<sensor_msgs::Image>("/projectedImg", 100, true);
	pc_pub = nh.advertise<pcl::PointCloud<pcl::PointXYZRGB>>("/pcl_points", 100, true);
	message_filters::Subscriber<sensor_msgs::PointCloud2> subscriber_pcl(nh,"/hesai/pandar",1,ros::TransportHints().tcpNoDelay());
    	message_filters::Subscriber<vision_msgs::Detection2DArray> subscriber_bbox(nh,"/yolov7",1,ros::TransportHints().tcpNoDelay());
	ROS_INFO("Inintiating");
	typedef message_filters::sync_policies::ApproximateTime<sensor_msgs::PointCloud2, vision_msgs::Detection2DArray> syncPolicy;
	message_filters::Synchronizer<syncPolicy> sync(syncPolicy(10), subscriber_pcl, subscriber_bbox);//10 is the queue size
	ROS_INFO("Synchronizer defined");
	string filename = "/home/nvidia/Data/data_" + getCurrentTimestamp() + ".csv";
	ofstream file(filename, std::ios::app);
	if (!file.is_open()) {
		std::cerr << "Failed to open CSV file!";
		exit(EXIT_FAILURE);
	}
	file << "seq_id,timestamp,class_id,score,Min_distance,Avg_distance,Min_X,Average_X,Min_Y,Average_Y,Original_points,Downsampled_points,Clustered_points,Preprocessing_time,Fusion_time" << endl;
	file.close();
	ROS_INFO("CSV file created");
	sync.registerCallback(boost::bind(&PointCallback, _1, _2, ground_level, leaf_size, cluster_tolerance, MinClusterSize, truncate_threshold, bbox_rescale, filename));
	ROS_INFO("Callback registered");
	ros::spin();
	return 0;
}
```