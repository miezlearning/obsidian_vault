Pembahasan pada Perancangan Proses/Algoritma:
- **Dataset citra kerusakan jalan**  
    “Input saya berupa foto kerusakan jalan yang sudah berlabel 9 kelas (jenis×tingkat).”
    
- **Preprocessing (Resize + Normalisasi)**  
    “Resize 224×224 karena VGG19 standar inputnya 224. Normalisasi biar distribusi pixel stabil dan training lebih cepat konvergen.”
    
- **Validation Data itu dipakai kapan?**  
    “Validation dipakai _selama training_ buat memantau performa. Kalau train naik tapi val turun → indikasi overfitting, jadi saya pakai sebagai acuan early stopping/penyetelan parameter.”
    
- **Training Data → Augmentasi**  
    “Augmentasi hanya di training supaya model tidak ‘hafal’ data—tujuannya supaya robust di variasi cahaya/sudut.”
    
- **Model CNN VGG19 + Transfer Learning → Pelatihan Model**  
    “Saya pakai transfer learning karena dataset lokal terbatas; backbone VGG19 menangkap fitur tekstur/pola kerusakan, lalu layer akhir saya sesuaikan untuk output 9 kelas.”
    
- **Testing Data → Evaluasi Model → Output Klasifikasi**  
    “Testing itu benar-benar data yang tidak dilihat saat training. Hasilnya dievaluasi pakai confusion matrix dan metrik multi-kelas, lalu output akhirnya adalah kelas prediksi (jenis+severity).”

Jika dosen bertanya, _"Ini namanya metode apa? Kok outputnya bisa tahu Jenis DAN Tingkat padahal cuma 1 model?"_

**Jawabanmu:**

> "Secara teknis, ini adalah **Single-Label Multi-Class Classification**, Pak/Bu.
> 
> Disebut **Multi-Class** karena model memilih satu probabilitas tertinggi dari **9 kelas** yang tersedia (seperti tertera di Batasan Masalah poin 2 ).
> 
> Disebut **Single-Label** karena setiap gambar hanya akan diprediksi masuk ke dalam satu kategori pemenang saja (menggunakan Softmax).
> 
> Namun, label yang saya gunakan bersifat **Compound (Gabungan)**. Artinya, saya menggabungkan atribut 'Jenis' dan 'Tingkat' menjadi satu kelas unik. Contohnya, kelas 'Lubang' dan 'Ringan' digabung menjadi satu kelas bernama 'Lubang-Ringan'."

### I. Pertanyaan Fundamental (Bab I - Pendahuluan)

_Pertanyaan ini menguji pemahamanmu terhadap masalah dasar._

1. **Mengapa harus menggunakan Dataset Lokal Samarinda?**
    
    - _Antisipasi Jawaban:_ Jalan di tiap daerah punya karakteristik berbeda (tekstur aspal, pencahayaan, tipe tanah). Dataset global mungkin tidak merepresentasikan kondisi riil di Samarinda.
        
2. **Apa urgensinya sistem ini bagi DPUPR? Kenapa validasi manual dianggap gagal?**
    
    - _Antisipasi Jawaban:_ Validasi manual lambat, subjektif, dan bias penilai. Sistem otomatis mempercepat respon penanganan.
        
3. **Kenapa memilih Klasifikasi (Classification) bukan Deteksi Objek (Object Detection)?**
    
    - _Antisipasi Jawaban:_ Batasan masalah menyebutkan fokus pada jenis dan tingkat kerusakan, bukan letak koordinat objek. Klasifikasi lebih efisien untuk sekadar memvalidasi "apa jenis kerusakannya" dibanding harus menandai posisinya.
        

---

### II. Pertanyaan Metodologi & Teknis (Bab II - Tinjauan Pustaka)

_Pertanyaan ini menguji alasan pemilihan algoritma._

4. **Kenapa VGG19? Kenapa tidak ResNet, MobileNet, atau YOLO?**
    
    - _Pertanyaan Kritis:_ VGG19 itu model yang sangat berat (banyak parameter). Kenapa memilih ini padahal ada model yang lebih ringan (lightweight)?
        
    - _Antisipasi Jawaban:_ VGG19 dipilih karena stabilitas dan kemampuan ekstraksi fiturnya yang kuat dan terbukti superior di berbagai kondisi, serta penggunaan _Transfer Learning_ mengurangi beban pelatihan dari nol.
        
5. **Jelaskan mekanisme Transfer Learning yang kamu pakai! Apa bedanya _Feature Extraction_ dan _Fine-Tuning_?**
    
    - _Antisipasi Jawaban:_ Kamu menggunakan strategi _Feature Extraction_ di mana _layer_ konvolusi dibekukan (frozen) dan hanya melatih _layer_ klasifikasi akhir (fully connected).
        
    
        
6. **Apa fungsi dari Layer _Pooling_ pada VGG19?**
    
    - _Antisipasi Jawaban:_ Untuk mengurangi dimensi spasial citra, mengurangi jumlah parameter, dan mencegah overfitting.
        

---

### III. Pertanyaan Tentang Data & Skenario (Bab III - Metodologi)

_Pertanyaan ini biasanya yang paling "menyerang" logika penelitian._

7. **Bagaimana kamu menentukan tingkat kerusakan (Ringan, Sedang, Berat) secara objektif?**
    
    - _Pertanyaan Menjebak:_ Di proposal tertulis penentuan tingkat kerusakan dilakukan secara "kualitatif". Bagaimana kamu menjamin label "Sedang" menurut kamu sama dengan "Sedang" menurut petugas DPUPR?
        
    - _Tips:_ Kamu harus punya pedoman visual yang sangat jelas (Standard Operating Procedure) saat pelabelan agar konsisten.
        
8. **Bagaimana jika dalam satu foto terdapat 2 jenis kerusakan (misal: ada lubang DAN retak)?**
    
    - _Pertanyaan Kritis:_ Modelmu menggunakan Softmax yang biasanya _single-label_. Bagaimana sistem menanganinya?
        
    - _Tips:_ Jelaskan batasan masalah. Jika fokus _single-label_, maka foto akan dilabeli berdasarkan kerusakan yang paling dominan.
        
9. **Kenapa Augmentasi Data hanya dilakukan pada Data Latih (Training)?**
    
    - _Antisipasi Jawaban:_ Agar Data Validasi dan Uji tetap merepresentasikan kondisi nyata (real) di lapangan tanpa manipulasi, sehingga evaluasi model objektif.
        

---

### IV. Pertanyaan "Out of the Box" & Skenario Lapangan

_Pertanyaan ini menguji logika implementasi dan kasus ekstrem._

10. **Bagaimana performa model jika foto diambil saat hujan atau aspal basah?**
    
    - _Logika:_ Aspal basah memantulkan cahaya (refleksi) dan mengubah tekstur visual. Apakah modelmu akan bingung mengira genangan air sebagai "Permukaan Tidak Rata"?
        
    - _Jawaban Diplomatis:_ Ini bisa dimasukkan ke batasan masalah atau saran pengembangan, karena fokus saat ini adalah kondisi visual yang jelas.
        
11. **Masalah VGG19 dan Server DPUPR:**
    
    - _Pertanyaan:_ VGG19 ukuran filenya besar (>500MB). Jika nanti di-deploy ke web Jalan Peduli, apakah server DPUPR kuat menampung beban _inference_ jika ada 1000 laporan masuk bersamaan?
        
    - _Jawaban:_ Fokus penelitian ini adalah pada **akurasi model** (proof of concept), bukan optimasi _deployment_ sistem (sesuai batasan masalah: tidak mencakup full-stack/sistem keamanan).
        
12. **Bias Pengambilan Gambar (Angle/Sudut):**
    
    - _Pertanyaan:_ Foto laporan masyarakat seringkali asal-asalan (miring, _zoom_ terlalu dekat, atau terlalu jauh). Apakah model VGG19 yang dilatih dengan _resize_ $224\times224$ mampu mengenali lubang yang difoto dari jarak 10 meter vs 1 meter?
        
    - _Tips:_ Jawab dengan strategi Augmentasi Data (rotasi, zoom, dll) yang membantu model mengenali variasi tersebut.
        
13. **Apa yang terjadi jika Akurasi tinggi tapi _Recall_ rendah?**
    
    - _Logika:_ Jika Recall rendah, berarti banyak jalan rusak yang dianggap "jalan bagus" oleh sistem (False Negative).
        
    - _Pertanyaan:_ Mana yang lebih berbahaya untuk kasus DPUPR: Sistem bilang "Rusak" padahal "Bagus" (False Positive), atau sistem bilang "Bagus" padahal "Rusak" (False Negative)?
        
    - _Jawaban:_ False Negative lebih berbahaya karena kerusakan jadi tidak tertangani dan membahayakan pengendara. Maka _Recall_ harus diperhatikan.
        

### Tips Tambahan Saat Menjawab:

- Jika ditanya tentang teknis yang mendalam (rumus matematika), rujuk ke **Bab 2** proposalmu.
    
- Jika ditanya tentang hal yang belum kamu lakukan, jawab dengan: _"Hal tersebut belum tercakup dalam batasan masalah penelitian ini, namun menjadi saran yang menarik untuk pengembangan selanjutnya."_
    
- Selalu kaitkan jawaban dengan **dataset lokal Samarinda** karena itu adalah _novelty_ (kebaruan) penelitianmu.
    
    +1