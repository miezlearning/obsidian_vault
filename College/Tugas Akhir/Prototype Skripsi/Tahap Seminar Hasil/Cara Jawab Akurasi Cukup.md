Izin menjawab Bapak/Ibu penguji.

Pada penelitian ini, indikator **“akurasi cukup”** tidak saya tentukan dengan angka target tertentu, seperti 80% atau 90%, karena dataset yang digunakan merupakan dataset lokal Kota Samarinda dan baru pertama kali diuji untuk klasifikasi 9 kelas secara bersamaan.

Dalam penelitian ini, “cukup” saya artikan berdasarkan proses pelatihan model, khususnya melalui **Early Stopping**. Jika akurasi masih rendah atau model mengalami overfitting, maka proses dilanjutkan ke tahap **fine-tuning**, yaitu penyesuaian hyperparameter seperti learning rate dan penggunaan ReduceLROnPlateau.

Hasil akhirnya, pelatihan berhenti pada akurasi **66,54%**. Angka ini saya anggap cukup karena merupakan hasil terbaik dari arsitektur yang digunakan, dengan kondisi dataset yang cukup sulit, terutama karena ketidakseimbangan kelas yang tinggi dan adanya 9 jenis/tingkat kerusakan yang harus dibedakan secara bersamaan.

Jadi, sistem ini saya posisikan sebagai **proof-of-concept** dan **sistem pendukung keputusan awal** bagi petugas DPUPR, bukan sebagai sistem yang menentukan keputusan secara mutlak.