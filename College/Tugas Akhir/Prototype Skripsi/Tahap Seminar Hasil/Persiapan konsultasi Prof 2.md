Jadi, pembahasan yang perlu dibahas pertama dulu alurnya bahas tentang bab 1 dulu apa saja yang sudah direvisi apakah sudah jelas latar belakagnya dan sudah menggunakan latar belakang jenis "[[Study/Struktur Latar Belakang .md|deduktif]]" , 

Daftar Revisi [[Revisian Seminar Proposal]]

Di bab 2 jangan lupa tanyakan apakah perlu ditambahkan streamlit dan google colab di tinjauan pustaka...

Terus di bab 3, khususnya di rancangan proses apakah sudah benar alurnya.... 

> Bisa baca seperti ini saja alurnya

```html
Alur penelitian ini dimulai dari pengumpulan dataset citra kerusakan jalan yang dibagi ke dalam 9 kelas. Setelah data dikumpulkan, tahap pertama adalah **Preprocessing**, di mana seluruh citra diubah ukurannya (_resize_) menjadi 224x224 piksel agar kompatibel dengan arsitektur VGG19, serta dinormalisasi agar nilai pikselnya berada di rentang 0 hingga 1.

Selanjutnya, dataset dipisahkan menjadi tiga bagian: **Training Data** (70%), **Validation Data** (15%), dan **Testing Data** (15%).

Untuk memperkaya variasi data dan mencegah _overfitting_, saya menerapkan **Augmentasi** _hanya_ pada data latih (Training Data). Sedangkan data validasi dan uji dibiarkan natural agar merepresentasikan kondisi jalan yang sesungguhnya di Samarinda.

Masuk ke tahap pemodelan, data latih dimasukkan ke dalam model VGG19 untuk proses **Feature Extraction**. Selama proses ini berjalan, **Validation Data** digunakan secara _real-time_ untuk memantau performa model dan mencegah _overfitting_ menggunakan _Early Stopping_.

Setelah mendapatkan bobot awal, dilanjutkan dengan tahap **Fine-Tuning** dengan membuka beberapa lapisan (_layer_) terakhir dari VGG19 (khususnya block 5) agar model lebih spesifik mengenali fitur kerusakan jalan.

Terakhir, model dievaluasi menggunakan **Testing Data** yang sama sekali belum pernah dilihat oleh model (Evaluasi Akhir). Jika akurasi dirasa belum cukup, maka akan dilakukan evaluasi ulang pada tahap Fine-Tuning atau penyesuaian parameter. Jika akurasi sudah memenuhi target, maka model siap menghasilkan **Output Klasifikasi** berupa prediksi jenis dan tingkat kerusakan jalan.
```