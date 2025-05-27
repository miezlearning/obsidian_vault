Sebelum lebih lanjut coba kenalin dulu kelompoknya, dan apa peran kamu (alif) sebagai ketua.

Terus coba lanjut struktur ini sebagai bahan pembicaraan dengan mentor.


1. Perkenalkan Aplikasi GetPinjol ini apa,

Jadi, getpinjol itu sendiri merupakan aplikasi solutif dan edukatif bagi masyarakat, karena maraknya kejadian terjebak dalam praktik, seperti; intimidasi kasar, bunga tinggi, dan penyalahgunaan data pribadi(entah dijadikan senjata untuk mengancam dan dipakai untuk hal negatif lainnya.)

Solutif, yang dimaksud adalah dapat berhati hati dan tahu apa aplikasi yang terlihat legal dan ilegal, dan edukatifnya terletak pada informasi yang bersifat edukasi kepada masyarakat agar dapat mengenali peminjaman yang aman dan legal.

Penggunaan machine learningnya ini rencana 

- TensorFlow
    
- TensorFlow.js
    
- Scikit-learn
    
- NLTK

Tapi ini hanya rencana karena saya masih kebingungan untuk training multiple data sourcenya.

Yang digunakaan sekarnag pun untuk analisis sentimen itu menggunakan logika rating angkanya, dan ini kurang efektif sebenarnya karena bisa saja ada ambiguitas di pengisiana feedbaccknya.
 
 Mungkin seperti raitng 1 isinya positif tapi ratingnya negatif, karena orang ini berpikir, rating 1 dulu jika sudah diperbaiki baru diperbarui juga ratingnya


sedangkan untuk rating 3 ini lebih ambigu lagi karena dia lumayan, atau  "tidak terlalu baik tidak terlalu buruk," atau bahkan mengandung campuran sentimen positif dan negatif yang kuat.



**Note** :
"discrepancy" mengacu pada perbedaan atau ketidaksesuaian antara model yang diprediksi dengan data yang sebenarnya, atau antara hasil prediksi model dengan data yang seharusnya.



2. Berikan disclaimer pertanyaan

Karena aplikasi ini terbilang kontroversial, jadi sangat berhati hati dengan yang namanya pitfalls(boomerang) kedepannya seperti; aplikasi ini bisa di gugat karena aplikasi mereka dianggap berbahaya berdasarkan hasil evaluasi oleh sistemnya(padahal mungkin tidak). Jadi kami juga harus matang dalam persiapan memberikan output yang terbaik, pada akhirnya kami ingin aplikasi ini bisa menjadi ground truth (data yang valid) bagi semua masyarakat.

Jadi, kemungkinan saya sudah mempersiapkan 5-7 pertanyaan lebih dari yang sudah saya berikan sebelumnya kak, atau kemungkinan saya ganti pertanyaan menyesuaikan pembahasan.


### **Opsi 1: Risk Score Approach**

```
Output: Skor Risiko 0-100
- 0-30: Aman (hijau)
- 31-70: Perlu Hati-hati (kuning) 
- 71-100: Berisiko Tinggi (merah)
```

**Keuntungan:**

- Tidak claim "ilegal" secara absolut (hindari masalah legal)
- Lebih nuanced dan informatif
- User bisa ambil keputusan sendiri

**Komponen Skor:**

- Status OJK (30%): 0 jika tidak terdaftar, 1 jika terdaftar
- Sentiment Analysis (25%): Dari ulasan pengguna
- Report Frequency (20%): Jumlah laporan vs total user
- App Store Metrics (15%): Rating, download pattern
- Keyword Detection (10%): Kata-kata mencurigakan (intimidais, bunga tinggi, jaminan cepat, tanpa syarat, penyalahgunaan data)

### Fitur Data Utama dan Kebutuhan

Berdasarkan catatan dan rencana proyek, berikut adalah fitur data utama untuk GetPinjol dan cara mengintegrasikannya:

- **Status OJK (Bobot 30%)**:
    - **Deskripsi**: Indikator biner (0 = tidak terdaftar, 1 = terdaftar).
    - **Sumber**: Daftar aplikasi terdaftar OJK (scraping atau API).
    - **Peran**: Indikator utama legalitas; bobot tinggi karena keandalan.
    - **Prapemrosesan**: Konversi ke fitur biner.
- **Analisis Sentimen (Bobot 25%)**:
    - **Deskripsi**: Skor sentimen (positif, negatif, netral) dari ulasan pengguna.
    - **Sumber**: Ulasan app store, laporan pengguna via GetPinjol.
    - **Peran**: Menangkap pengalaman pengguna (misalnya, keluhan intimidasi).
    - **Prapemrosesan**: Gunakan NLTK VADER atau BERT untuk skor sentimen; tangani kasus ambigu dengan aturan manual atau NLP lanjutan.
- **Frekuensi Laporan (Bobot 20%)**:
    - **Deskripsi**: Rasio laporan terhadap total pengguna atau ulasan.
    - **Sumber**: Laporan pengguna, volume ulasan app store.
    - **Peran**: Menunjukkan skala masalah; frekuensi tinggi = risiko tinggi.
    - **Prapemrosesan**: Normalisasi berdasarkan jumlah pengguna atau ulasan.
- **Metrik App Store (Bobot 15%)**:
    - **Deskripsi**: Rata-rata rating, tren unduhan, volume ulasan.
    - **Sumber**: Google Play, Apple Store (scraping atau API).
    - **Peran**: Validasi eksternal kualitas aplikasi.
    - **Prapemrosesan**: Normalisasi rating (skala 1-5) dan deteksi pola mencurigakan (misalnya, lonjakan rating).
- **Deteksi Kata Kunci (Bobot 10%)**:
    - **Deskripsi**: Keberadaan kata kunci berisiko (misalnya, “intimidasi,” “bunga tinggi”).
    - **Sumber**: Ulasan, laporan pengguna.
    - **Peran**: Menandai red flags spesifik yang tidak terdeteksi sentimen.
    - **Prapemrosesan**: Gunakan regex atau NLTK untuk ekstraksi; buat fitur biner atau berbasis jumlah.

### **Opsi 2: Multi-Class Classification**

```
Output: 4 Kategori
1. "Terdaftar OJK" (Legal confirmed)
2. "Tidak Terdaftar OJK" (Status unclear)
3. "Berpotensi Bermasalah" (Many negative reports)
4. "Sangat Berisiko" (Extreme red flags)
```

### **Opsi 3: Dual Output System**

```
Primary Output: Risk Score (0-100)
Secondary Output: Specific Warnings
- "Tidak terdaftar di OJK"
- "Banyak keluhan penagihan kasar"
- "Rating rendah dengan pola mencurigakan"
- "Kata kunci berisiko terdeteksi"
```



Pertanyaan :

1. Jika ada aplikasi yang tidak terdaftar OJK tapi tidak ada keluhan, **bagaimana labelnya?**
2. **Bagaimana handling false reports?** Misalnya kompetitor sengaja report aplikasi lain.
3. **Apakah perlu verifikasi manual untuk laporan?** Atau langsung masuk ke model?
4. Bagaimana cara terbaik untuk menggabungkan fitur-fitur dari berbagai sumber data (ulasan, rating, status OJK, keyword detection) sebagai input ke model klasifikasi (misalnya Random Forest) untuk memprediksi skor risiko? Apakah pendekatan mengumpulkan semua fitur dalam satu feature vector sudah optimal, atau ada arsitektur lain yang lebih disarankan?
5. Dari 3 tersebut hal, apa output yang paling informatif bagi user experience nantinya.
6. **Apakah ada rekomendasi lain untuk memastikan keakuratan label sentimen, terutama untuk kasus-kasus ambigu atau yang memiliki discrepancy antara rating dan teks?**

Ingat: **Better to have imperfect but useful risk score than perfect but unusable legal/illegal classifier.**

# Catatan 

**Jangan terjebak di "legal vs ilegal"** - ini terlalu binary dan risky secara legal.

**Focus on "risk assessment"** - bantu user make informed decision tanpa claim absolut.

**Prioritas tanyakan ke mentor:**

1. Ground truth strategy
2. Output format recommendation
3. Handling uncertainty in data
4. MVP scope yang realistic


Batasan masaalah, data hanya dipakai untuk ulasan playstorenya

Gunakan kata rekomendasi dan tidak rekomendasi.

Fokus ke titik f1 score , 

![[{D0C64277-5228-487E-99FC-5E43D28B6453}.png]]

false report , outliers, data stoge perlu diperhatikan, perhatikan pola, kalau regresi ada diluar pola