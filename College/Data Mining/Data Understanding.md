**Data Understanding** adalah tahap kedua dalam metodologi **CRISP-DM**, setelah **Business Understanding**. Tahap ini berfokus pada eksplorasi dan pemahaman data yang akan digunakan dalam analisis atau model machine learning.

---

## 🔍 **Apa yang Dilakukan dalam Data Understanding?**

1️⃣ **Mengumpulkan Data** 📥

- Mengidentifikasi sumber data (database, CSV, API, dll.).
- Memastikan data sesuai dengan tujuan bisnis.

2️⃣ **Memeriksa Struktur Data** 🧐

- Berapa banyak **baris dan kolom**?
- Apa saja **tipe data** (numerik, kategori, teks, dll.)?
- Apakah ada data yang tidak lengkap atau tidak relevan?

3️⃣ **Eksplorasi Data Awal** 📊

- Statistik dasar: **rata-rata, median, modus, standar deviasi**.
- Distribusi data dengan grafik **histogram, boxplot, scatterplot**.
- Korelasi antar variabel.

4️⃣ **Menangani Masalah Data** 🛠

- **Data hilang (missing values)** → Apakah perlu dihapus atau diisi ulang?
- **Data duplikat** → Apakah ada entri yang harus dibersihkan?
- **Pencilan (outliers)** → Apakah ada nilai ekstrem yang perlu diperhatikan?

---

## 🎯 **Contoh Data Understanding dalam Clustering**

Misalkan kita ingin melakukan **customer segmentation** berdasarkan kebiasaan belanja pelanggan.

📥 **Data yang dikumpulkan:**

|ID|Pendapatan ($1000)|Skor Belanja (1-100)|
|---|---|---|
|1|15|39|
|2|16|81|
|3|28|77|
|4|45|40|
|5|50|42|
|...|...|...|

📊 **Analisis Awal:**

- **Cek jumlah data** → Misalnya ada **200 pelanggan**.
- **Distribusi pendapatan** → Rata-rata **35K**, ada yang sangat tinggi/rendah?
- **Cek missing values** → Ada data kosong atau tidak?
- **Pencilan (outlier)** → Ada pelanggan dengan **pendapatan ekstrem**?

Setelah memahami data, kita bisa lanjut ke tahap **Data Preparation** untuk membersihkan dan menyiapkannya sebelum digunakan dalam model clustering.

---

## 🚀 **Kesimpulan**

Tahap **Data Understanding** memastikan bahwa kita memahami struktur, kualitas, dan pola dalam data sebelum membuat model machine learning.

