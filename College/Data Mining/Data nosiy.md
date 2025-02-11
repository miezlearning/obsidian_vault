### 🔊 **Apa Itu Data Noisy?**

**Data noisy** adalah data yang mengandung **kesalahan, inkonsistensi, atau informasi yang tidak relevan**, sehingga dapat mengganggu analisis atau model machine learning.

Noisy data bisa muncul karena **human error, kesalahan sensor, gangguan sinyal, atau data yang tidak diketik dengan benar**.

---

## 🚨 **Contoh Data Noisy**

1️⃣ **Data dengan Kesalahan Pengetikan (Typo)**

- Nama: `"J0hn D0e"` (seharusnya `"John Doe"`)
- Kota: `"Jakrta"` (seharusnya `"Jakarta"`)

2️⃣ **Data yang Tidak Konsisten**

- Tanggal lahir: `"12-08-1999"` dan `"08/12/1999"` (format berbeda)
- Mata uang: `"10.000 IDR"` dan `"Rp10,000"`

3️⃣ **Data dengan Nilai Ekstrem atau Outlier**

- Usia pelanggan: **200 tahun** (tidak masuk akal)
- Harga produk: **Rp 999.999.999.999** (terlalu tinggi dibandingkan rata-rata)

4️⃣ **Data dari Sensor yang Error**

- Sensor suhu membaca **"999°C"** (error karena sensor rusak)
- Kamera mengenali **bayangan sebagai objek** dalam pengolahan gambar

5️⃣ **Data yang Tidak Relevan**

- Review produk: **"Beli produk ini di toko sebelah lebih murah!"** (bukan review yang bermanfaat)

---

## 🔧 **Cara Mengatasi Noisy Data**

1️⃣ **Data Cleaning (Pembersihan Data)**

- Menghapus atau memperbaiki data yang mengandung kesalahan.
- Contoh: Mengoreksi `"Jakrta"` menjadi `"Jakarta"`.

2️⃣ **Data Smoothing (Pemerataan Data)**

- Menggunakan teknik statistik untuk menghilangkan noise, seperti **moving average** atau **binning**.

3️⃣ **Outlier Detection & Handling**

- Menggunakan **z-score, IQR (Interquartile Range), atau Machine Learning** untuk mendeteksi data ekstrem.
- Bisa dihapus atau dikoreksi jika tidak masuk akal.

4️⃣ **Data Transformation (Transformasi Data)**

- Normalisasi & standardisasi data agar lebih seragam.
- Contoh: Mengubah semua harga ke format `"Rp 10.000"`.

5️⃣ **Menggunakan AI atau Machine Learning**

- Model **autoencoder atau clustering** bisa mendeteksi dan membersihkan noise dalam data.

---

## 🚀 **Kesimpulan**

**Noisy data bisa mengganggu analisis dan model prediksi,** jadi harus dibersihkan sebelum digunakan. Teknik seperti **data cleaning, smoothing, dan outlier detection** sangat penting untuk menangani data yang berisik!

Mau coba contoh coding buat deteksi noisy data pakai Python? 😃