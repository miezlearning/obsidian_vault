Model belajar dari data berlabel untuk menemukan pola atau struktur tersembunyi. Model ini belajar dari pasangan input-output, di mana setiap input memiliki label atau output yang sesuai. Tujuannya adalah untuk mempelajari hubungan antara input dan output sehingga model dapat memprediksi output yang benar untuk input baru yang belum pernah dilihat sebelumnya.

Proses ini dikenal sebagai **pembelajaran terawasi (supervised learning)**. Dalam pembelajaran terawasi, model dilatih menggunakan dataset yang sudah diberi label, dan tujuannya adalah untuk menggeneralisasi pola yang dipelajari dari data pelatihan sehingga dapat membuat prediksi yang akurat pada data yang belum pernah dilihat sebelumnya.

Contoh aplikasi dari pembelajaran terawasi termasuk:
- **Klasifikasi**: Memprediksi kategori atau kelas dari suatu input, seperti mengklasifikasikan email sebagai spam atau bukan spam.
- **Regresi**: Memprediksi nilai kontinu, seperti memprediksi harga rumah berdasarkan fitur-fitur seperti luas tanah, jumlah kamar, dan lokasi.

Dengan demikian, tujuan utama dari model yang belajar dari data berlabel adalah untuk mengidentifikasi pola atau hubungan dalam data yang dapat digunakan untuk membuat prediksi yang akurat pada data baru.


Traning Phase : model dilatih menggunakan data berlabel
Validation Phase: Model diuji dengna dataset validasi untuk menghindari overfitting ()
Testing Phase : Model diuji dengan data baru untuk mengukur performa



Overfitting : 

**Overfitting** dalam machine learning adalah kondisi di mana model pembelajaran mesin belajar *terlalu baik* pada data pelatihan (training data), hingga mengakibatkan kinerja buruk pada data baru yang belum pernah dilihat sebelumnya (misalnya data validasi atau uji). 

### **Apa yang Terjadi Saat Overfitting?**
- Model "menghafal" pola, noise, atau detail spesifik pada data pelatihan, termasuk **outlier** atau **random noise** yang tidak relevan.
- Akibatnya, model menjadi sangat kompleks dan kehilangan kemampuan untuk **menggeneralisasi** (beradaptasi pada data baru).
- **Contoh**: Model klasifikasi gambar kucing vs anjing bisa salah karena terlalu fokus pada latar belakang tertentu (misalnya rumput) yang muncul di data pelatihan, alih-alih fokus pada ciri hewan itu sendiri.

---

### **Ciri-Ciri Overfitting**
1. **Akurasi tinggi pada data pelatihan**, tetapi **akurasi rendah pada data uji/validasi**.
   - Contoh: Akurasi training 98%, akurasi testing 70%.
2. Model memiliki **kompleksitas berlebihan** (misalnya neural network dengan terlalu banyak layer/parameter).
3. Performa model sangat sensitif terhadap perubahan kecil pada data input.

---

### **Penyebab Overfitting**
1. **Model Terlalu Kompleks**: 
   - Model memiliki terlalu banyak parameter (misalnya deep neural network dengan layer berlebihan) sehingga "memaksa" untuk mempelajari noise.
2. **Data Pelatihan Terlalu Sedikit**:
   - Jumlah data tidak cukup untuk menangkap variasi yang ada di dunia nyata.
3. **Pelatihan Terlalu Lama** (over-training):
   - Pada algoritma seperti neural network, pelatihan terlalu banyak epoch menyebabkan model mulai menghafal data.

---

### **Contoh Overfitting**
- **Regresi**: Model regresi polinomial derajat tinggi (misalnya polinomial derajat 15) yang menghasilkan kurva "bergelombang" tidak wajar untuk data sederhana.
- **Klasifikasi**: Decision tree yang memiliki cabang terlalu dalam hingga setiap leaf node hanya berisi 1 sampel.

---

### **Cara Mengatasi Overfitting**
1. **Cross-Validation**:
   - Membagi data menjadi training, validasi, dan testing untuk memantau kinerja model.
2. **Regularisasi**:
   - Menambahkan "hukuman" pada kompleksitas model (misalnya L1/L2 regularization pada regresi).
3. **Pruning** (pada decision tree):
   - Memotong cabang yang tidak penting untuk mengurangi kompleksitas.
4. **Early Stopping** (pada neural network):
   - Menghentikan pelatihan sebelum model mulai overfitting.
5. **Data Augmentation**:
   - Menambah data pelatihan dengan teknik seperti rotasi, scaling, atau noise (untuk data gambar/teks).
6. **Mengurangi Kompleksitas Model**:
   - Menggunakan model yang lebih sederhana (misalnya mengurangi jumlah layer pada neural network).
7. **Dropout** (pada neural network):
   - Mematikan neuron secara acak selama pelatihan untuk mencegah ketergantungan berlebihan pada fitur tertentu.

---

### **Perbedaan Overfitting vs Underfitting**
- **Overfitting**: Model terlalu kompleks, baik pada data training tetapi buruk pada data uji.
- **Underfitting**: Model terlalu sederhana, buruk pada data training dan data uji (gagal belajar pola dasar).

---

Intinya, overfitting adalah musuh utama dalam machine learning karena model harus **seimbang** antara mempelajari pola penting dan tetap bisa beradaptasi pada data baru.



Oke, kita bahas lebih detail tapi tetap dengan bahasa yang gampang dicerna! 😎

---

## **🧠 Supervised Learning = Belajar Pakai Jawaban (Contekan)**

Bayangin kamu belajar buat ujian, tapi gurunya udah kasih **buku kunci jawaban**. Jadi tugas kamu tinggal belajar dari soal-soal dan jawabannya, lalu memahami polanya.

Di dunia AI, **Supervised Learning** berarti komputer dikasih **data yang udah ada labelnya**, lalu dia belajar dari situ buat bikin prediksi di masa depan.

🔍 **Ciri-ciri Supervised Learning:**  
✅ Ada input **(soal)** dan output **(jawaban)**  
✅ Model dilatih dengan data yang sudah ada labelnya  
✅ Bisa dipakai buat **prediksi** atau **klasifikasi**

💡 **Contoh real life-nya:**

- **Deteksi email spam 📩** → AI dilatih dengan contoh email yang udah dikasih label **spam / bukan spam**.
- **Face recognition 📸** → AI belajar dari foto wajah yang udah dikasih nama, jadi dia bisa ngenalin orang di foto baru.
- **Prediksi harga rumah 🏡** → AI dikasih data rumah (luas, lokasi, jumlah kamar) & harganya, terus dia bisa nebak harga rumah lain.

✏️ **Supervised Learning dibagi jadi 2 jenis:**  
1️⃣ **Klasifikasi** → Prediksi kategori (contoh: spam/bukan spam, anjing/kucing)  
2️⃣ **Regresi** → Prediksi angka (contoh: harga rumah, jumlah penjualan)

---

## **🌀 Unsupervised Learning = Belajar Sendiri Tanpa Jawaban**

Nah, kalau ini beda. Bayangin kamu dikasih setumpuk soal tapi **tanpa kunci jawaban**. Jadi, kamu harus **cari pola sendiri** buat ngerti isi soal itu.

Di AI, **Unsupervised Learning** berarti komputer cuma dikasih data **tanpa label**, lalu dia disuruh nyari pola atau kelompok-kelompok sendiri.

🔍 **Ciri-ciri Unsupervised Learning:**  
✅ **Gak ada jawaban (label)**, AI cuma nemuin pola sendiri  
✅ Biasanya dipakai buat **ngelompokkan data (clustering)** atau **nyari pola tersembunyi**  
✅ Sering dipakai buat **analisis & rekomendasi**

💡 **Contoh real life-nya:**

- **Rekomendasi lagu di Spotify 🎵** → AI ngelompokin orang-orang yang suka lagu mirip & kasih rekomendasi sesuai pola itu.
- **Toko online 🛒** → AI ngelompokin pembeli jadi "anak hypebeast", "pecinta diskon", atau "sultan dadakan" biar bisa kasih promo yang pas.
- **Anomali di transaksi bank 💰** → AI bisa ngenalin transaksi yang mencurigakan karena beda dari pola biasanya.

✏️ **Jenis utama dalam Unsupervised Learning:**  
1️⃣ **Clustering** → AI ngelompokkan data yang mirip (contoh: rekomendasi produk, segmentasi pelanggan)  
2️⃣ **Association** → AI nyari hubungan antar data (contoh: orang yang beli sepatu sering beli kaus kaki juga)

---

## **⚔️ Perbandingan Supervised vs. Unsupervised**

|Fitur|Supervised Learning|Unsupervised Learning|
|---|---|---|
|**Label data**|Ada (pakai contekan) ✅|Gak ada (cari pola sendiri) ❌|
|**Tujuan**|Prediksi sesuatu berdasarkan contoh|Ngelompokin atau nyari pola di data|
|**Contoh**|Deteksi spam, face recognition, prediksi harga|Rekomendasi lagu, segmentasi pelanggan, deteksi fraud|
|**Metode utama**|Klasifikasi, Regresi|Clustering, Association|

---

### **📌 Kesimpulan Simpel:**

📖 **Supervised Learning** → AI belajar pakai contekan (data ada jawabannya) buat prediksi masa depan.  
🔍 **Unsupervised Learning** → AI disuruh nebak pola sendiri tanpa dikasih jawaban.

Gampangnya:

- **Supervised = Kayak sekolah pakai buku paket & kunci jawaban**
- **Unsupervised = Kayak detektif yang nyari pola sendiri (Sherlock Holmes vibes 🔍)**

Udah ngerti kan? Sekarang kalau ada yang nanya, tinggal jelasin pakai analogi ini! 🚀🔥

- **Unsupervised Learning:** Penambahan data baru biasanya memerlukan pembuatan model baru dari awal (remodelling) karena model unsupervised mempelajari struktur inheren dari data tanpa panduan label.
    
- **Supervised Learning:** Model yang sudah dilatih dapat langsung digunakan untuk memproses data baru. Pemodelan ulang (retraining) pada supervised learning umumnya hanya diperlukan jika:
    - Ada penambahan data dalam jumlah besar.    
    - Data baru tersebut memiliki label yang berbeda atau memperkenalkan kelas baru (dalam kasus klasifikasi, misalnya dari 2 kelas menjadi 3 kelas). Ini menunjukkan adanya perubahan signifikan dalam distribusi data atau munculnya pola baru yang belum dipelajari model.


Apa itu ground turth : 




_Flatten layer_ berfungsi untuk mengubah representasi multi-dimensi dari _feature maps_ menjadi vector satu dimensi. Layer ini diperlukan sebagai penghubung antara _convolutional layers_ yang menghasilkan output tiga dimensi (lebar × tinggi × channel) dan _fully connected layers_ yang memerlukan input satu dimensi.

Jika input memiliki dimensi h×w×dh×w×d (height × width × depth/channels), maka output flatten adalah vector dengan dimensi h×w×dh×w×d elemen. Proses _flattening_ tidak mengubah atau menghilangkan informasi dalam data, tetapi hanya merestrukturisasi format representasi.