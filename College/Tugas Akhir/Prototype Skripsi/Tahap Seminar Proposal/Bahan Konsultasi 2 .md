1. Bahas sedikit latar belakang : 

Oke Lip, aku rangkumkan secara jelas dan _step-by-step_ ya supaya kamu siap banget buat ketemu Bu Prof Anindita.  
Aku juga sudah baca proposal kamu dari file PDF ✔️

---

# **1. Mulai Konsul dari Mana? (Urutan yang Paling Aman)**

Kalau ini _konsultasi kedua_, dan kamu sudah punya draft proposal lengkap seperti file itu, maka urutan pembahasan yang paling tepat:

### ✅ **1. Latar Belakang**

Pastikan beliau paham dulu _kenapa topik ini penting_.  
Kamu tinggal jelasin:

- Masalah kerusakan jalan di Samarinda nyata & sering terlambat ditangani
    
- Sistem pelaporan Jalan Peduli masih verifikasi manual → lama & subjektif
    
- CNN + VGG19 bisa mengotomatisasi validasi foto
    
- Kamu pakai **dataset lokal Samarinda** → relevan & unik ( yang akan dibahas pada bab 3 di pengumpulan data )
    

"Di berbagai wilayah, termasuk Kota Samarinda, masalah kerusakan jalan tetap menjadi perhatian serius. Faktor-faktor seperti beban kendaraan yang berlebihan, kondisi cuaca ekstrem, dan pemeliharaan yang tidak teratur sering mempercepat kerusakan (Kerusakan Jalan Di Samarinda Masalah Sistemik, Akademisi Ungkap Masalah Keterbatasan Anggaran, n.d.). Bentuk kerusakan yang umum meliputi retakan pada permukaan jalan, lubang jalan, dan permukaan jalan yang tidak rata. Jika kerusakan ini tidak ditangani segera, kualitas jalan akan terus menurun dan biaya perbaikan di masa depan akan lebih tinggi (Kurniawan et al., 2025)."

Langsung to the point ke

"Hingga saat ini, proses pelaporan kerusakan jalan oleh masyarakat umumnya dilakukan secara manual melalui formulir online seperti Google Forms. Meskipun praktis, metode ini memiliki beberapa keterbatasan, termasuk ketidakhadiran sistem validasi otomatis untuk foto yang dikirimkan,"

disampaikan lebih online 


Teknolog Artifical Intellegince


Gunakan kata citra perbanya k


"Gunakan data yang membuat...."

Kata manual tidak perlu di tonjolkan 

"Tidak perlu kata mengimplementasikan" jika sudah merancang 



"Dengan demikian, penelitian ini tidak hanya menjadi solusi teknis, tetapi juga acuan untuk pengembangan kota cerdas (smart city) yang lebih responsif dan berbasis data." Tidak perlu ini yang to the point aja tidak perlu berbunga bunga kalimatnya 


"ang dapat menjadi referensi bagi 6 pengembangan Smart City di Indonesia, serta memberikan solusi validasi otomatis untuk mengatasi bottleneck pada pelaporan manual di DPUPR."

Dihapus saja 

"Ambil abstrak saja di bagian penelitian terkait "


2.2.1 kasi lurus ke kiri 

Processing & Augmentasi masuknya di perancangan data


Dataset yg dihasilkan pada pengumpulan data 

Testing Data langsung masu ke evaluasi

Data testing lgsg masuk ke 



Konfigurasi model masuknya di pelatihan model 

Tabel 3. 6 Jadwal Penelitian , mulai dari januari

keseluruhan ditunjukkan pada Gambar 3.3

Ini bagian pertama yang harus kamu bahas karena _dasar dari semuanya_.

---

### ✅ **2. Rumusan Masalah & Tujuan**

Minta Bu Prof cek apakah rumusan & tujuan kamu sudah:

- Terukur
    
- Tidak terlalu luas
    
- Tidak terlalu sempit
    

Ini penting karena mereka biasanya _ngecek apakah penelitianmu bisa selesai tepat waktu_.


Lebih ringkas, to the point bahasanya
bukan citranya tapi isinya.
jangan kata "hanya"  
no 3 dijawab dengan no 1  ( tidak perlu )


---

### ✅ **3. Batasan Masalah**

Ini penting biar beliau yakin kamu tidak “kemana-mana”.

Contohnya kamu sudah membatasi:

- Hanya klasifikasi, bukan deteksi
    
- Tidak pakai drone
    
- Tidak full-stack aplikasi
    

Bu Prof biasanya suka mahasiswa yang **jelas batasnya**.

---

### ✅ **4. Dataset & Teknis Pengolahan**

Ini bagian paling sering ditanya.

Sampaikan:

- Dataset kamu benar-benar dari **foto manual Samarinda**
    
- Berapa banyak total datanya
    
- Kualitas gambar (pencahayaan, noise, dsb.)
    
- Bagaimana rencana augmentasi
    
- Pembagian train/val/test
    

Kalau dataset-mu masih sedikit, beliau pasti akan ngasih masukan.  
Dan itu normal — tugas pembimbing memang begitu.

---

### ✅ **5. Metode: VGG19 + Transfer Learning**

Bahas dengan sederhana:

- Kenapa pilih VGG19?  
    → Stabil, mudah di-train, cocok dataset kecil
    
- Transfer learning tujuannya apa?  
    → Mengatasi dataset lokal yang terbatas
    
- Apakah kamu mau feature extraction, fine tuning, atau keduanya?  
    (ini biasanya ditanya)
    

Proposal kamu sudah cukup lengkap pada bagian ini, tapi jelasin secara ringkas pas konsultasi.

---

### ✅ **6. Evaluasi Model**

Ini penting karena menyangkut _hasil skripsimu nanti_.

Kamu evaluasi pakai:

- Akurasi
    
- Precision
    
- Recall
    
- F1-score
    

Pastikan kamu paham fungsinya walau kamu “kurang matematika”.  
Nggak perlu hafal rumus, yang penting ngerti maknanya.

---

# **2. Kekhawatiran Kamu Soal Matematika**

Tenang, topikmu **sangat aman** untuk mahasiswa yang kurang kuat matematika.

Kenapa?

- Framework (TensorFlow/Keras) sudah mengurus matematika berat
    
- Kamu tidak menghitung turunan, matrix multiplication, atau gradient
    
- Kamu hanya perlu paham konsep:
    
    - Apa itu learning rate
        
    - Apa itu epoch
        
    - Apa itu overfitting
        
    - Apa itu akurasi/precision/recall
        
- Implementasi hanya menulis beberapa baris kode
    

Yang paling penting itu **pemahaman konsep**, bukan rumus.

Justru topik kamu masuk kategori yang aman buat pemula.

---

# **3. Checklist Bicara dengan Bu Prof Anindita**

Ini bisa kamu bawa ke ruang konsultasi:

### **A. Yang harus kamu jelaskan**

- Sudah punya draft lengkap
    
- Sudah punya dataset lokal
    
- Sudah bentuk kerangka metode
    
- Sudah tahu rencana hasil & evaluasi
    

### **B. Yang harus kamu tanyakan**

1. **Apakah latar belakangku sudah fokus dan tepat?**
    
2. **Apakah rumusan masalah dan tujuan sudah jelas?**
    
3. **Datasetku cukup atau perlu diperbanyak?**
    
4. **Bagian metode VGG19-ku perlu diperdalam atau sudah baik?**
    
5. **Perlu pakai fine-tuning penuh atau cukup feature extraction?**
    
6. **Bagian 3.4 Flowchart proses apakah sudah benar?**
    
7. **Apa ada bagian yang biasanya harus diperbaiki mahasiswa tahun lalu?** (Ini trik bagus!)
    

---

# **4. Tips Saat Konsultasi**

- Jangan menunggu ditanya, kamu yang memulai:  
    “Bu, saya ingin membahas dari latar belakang dulu ya Bu, apakah sudah tepat arahnya?”
    
- Bawa proposal versi PDF + catatan kecil di bagian yang kamu mau tanya
    
- Kalau Bu Prof minta revisi, langsung catat.  
    Mereka suka mahasiswa yang cepat nangkap.
    

---

Kalau mau, aku bisa bikinin:  
✅ draft kalimat pembuka saat konsultasi  
✅ daftar pertanyaan paling aman + elegan  
✅ penjelasan “math ringan” untuk akurasi/precision/recall  
Cukup bilang saja mau yang mana.


Tentang Fine Tuning :

Saya menggunakan feature extraction karena dataset saya jumlahnya masih terbatas dan variannya belum terlalu besar. Dengan membekukan seluruh layer konvolusi VGG19, model menjadi lebih stabil dan tidak mudah overfitting.  
Kalau fine-tuning, saya harus membuka beberapa layer CNN dan melatih ulang, yang biasanya memerlukan dataset jauh lebih banyak serta waktu training lebih lama. Jadi pada kondisi dataset saya saat ini, feature extraction lebih tepat.