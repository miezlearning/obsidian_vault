Jadi, pembahasan yang perlu dibahas pertama dulu alurnya bahas tentang bab 1 dulu apa saja yang sudah direvisi apakah sudah jelas latar belakagnya dan sudah menggunakan latar belakang jenis "[[Study/Struktur Latar Belakang .md|deduktif]]" , 

Daftar Revisi [[Revisian Seminar Proposal]]

Di bab 2 jangan lupa tanyakan apakah perlu ditambahkan streamlit dan google colab di tinjauan pustaka...

Terus di bab 3, khususnya di rancangan proses apakah sudah benar alurnya.... 

> Bisa baca seperti ini saja alurnya

```md
Alur penelitian ini dimulai dari pengumpulan dataset citra kerusakan jalan yang dibagi ke dalam 9 kelas. Setelah data dikumpulkan, tahap pertama adalah **Preprocessing**, di mana seluruh citra diubah ukurannya (_resize_) menjadi 224x224 piksel agar kompatibel dengan arsitektur VGG19, serta dinormalisasi agar nilai pikselnya berada di rentang 0 hingga 1.

Selanjutnya, dataset dipisahkan menjadi tiga bagian: **Training Data** (70%), **Validation Data** (15%), dan **Testing Data** (15%).

Untuk memperkaya variasi data dan mencegah _overfitting_, saya menerapkan **Augmentasi** _hanya_ pada data latih (Training Data). Sedangkan data validasi dan uji dibiarkan natural agar merepresentasikan kondisi jalan yang sesungguhnya di Samarinda.

Masuk ke tahap pemodelan, data latih dimasukkan ke dalam model VGG19 untuk proses **Feature Extraction**. Selama proses ini berjalan, **Validation Data** digunakan secara _real-time_ untuk memantau performa model dan mencegah _overfitting_ menggunakan _Early Stopping_.

Setelah mendapatkan bobot awal, dilanjutkan dengan tahap **Fine-Tuning** dengan membuka beberapa lapisan (_layer_) terakhir dari VGG19 (khususnya block 5) agar model lebih spesifik mengenali fitur kerusakan jalan.

Terakhir, model dievaluasi menggunakan **Testing Data** yang sama sekali belum pernah dilihat oleh model (Evaluasi Akhir). Jika akurasi dirasa belum cukup, maka akan dilakukan evaluasi ulang pada tahap Fine-Tuning atau penyesuaian parameter. Jika akurasi sudah memenuhi target, maka model siap menghasilkan **Output Klasifikasi** berupa prediksi jenis dan tingkat kerusakan jalan.
```

Pertanyaan "akurasi cukup?" [[[Cara Jawab Akurasi Cukup]].

pertanyaan "kenapa hanya membuka 1 blok yaitu blok 5"  [[[Cara Jawab Block 5 VGG]].

Tujuan fine tuning pada penelitian ini untuk mengerucutkan atau memfokuskan model dalam mengenali kelas yang saya teliti atau lebih spesifik.

>Pada tabel summary tersebut, trainable parameter masih sebesar 396.297, yang berasal dari layer classifier tambahan. Artinya, berdasarkan summary itu, VGG19 masih dalam kondisi frozen sepenuhnya. Jika block5 benar-benar dibuka, jumlah trainable parameter akan bertambah karena parameter convolution pada block5 ikut dilatih. Jadi, tabel tersebut kemungkinan merepresentasikan tahap feature extraction, bukan tahap fine-tuning block5.

Penjelasan tentang blok atau fine tuning [[[Penjelasan VGG19 dan setiap Bloknya]].

Jelaskan lagi tentang apa saja yang sudah dibahas pada bab 4, scroll pelan untuk ibunya lihat lihat 