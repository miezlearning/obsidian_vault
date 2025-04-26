Berdasarkan konteks proyek **GetPinjol** sebagai website untuk deteksi dan edukasi pinjaman online, serta pertanyaanmu tentang bentuk **input** untuk proses deteksi (yang menggunakan machine learning seperti analisis sentimen, klasifikasi, clustering, dan deteksi kata kunci), saya akan menjelaskan:
1. **Jenis input** yang dibutuhkan untuk deteksi aplikasi pinjol legal/ilegal.
2. **Bagaimana input ini dikumpulkan dan diproses di website**.
3. **Contoh format input** yang masuk ke sistem, baik dari pengguna (via website) maupun dari sumber eksternal (seperti scraping).
4. **Integrasi dengan website**, termasuk bagaimana formulir pelaporan (dari diskusi sebelumnya) berkontribusi sebagai input.

Saya juga akan memastikan penjelasan ini selaras dengan dokumen proyek (yang menyebutkan penggunaan Scikit-Learn, Flask, Vite, dan dataset seperti OJK, Google Play Store, serta Kaggle) dan contoh kode deteksi sebelumnya, sambil menjawab kebutuhanmu untuk website.

---

### **1. Jenis Input untuk Deteksi**
Proses deteksi GetPinjol membutuhkan beberapa jenis data sebagai input untuk mengevaluasi apakah aplikasi pinjol legal atau ilegal. Input ini berasal dari berbagai sumber dan digunakan oleh model ML (analisis sentimen, klasifikasi, clustering, TF-IDF). Berikut jenis inputnya:

| **Jenis Input** | **Sumber** | **Deskripsi** | **Contoh** |
|-----------------|------------|---------------|------------|
| **Nama Aplikasi** | Pengguna (via formulir), Scraping (Google Play Store) | Nama aplikasi pinjol yang akan dianalisis. | “Pinjol X” |
| **Ulasan Pengguna** | Pengguna (formulir pelaporan), Scraping (Google Play, forum, berita) | Teks ulasan atau testimoni tentang pengalaman dengan aplikasi. | “Bunga tinggi 30% per minggu, ancaman via WA!” |
| **Rating Aplikasi** | Scraping (Google Play Store) | Skor rating rata-rata aplikasi (1-5). | 2.5 |
| **Status OJK** | Daftar resmi OJK (PDF/XLS) | Indikator apakah aplikasi terdaftar di OJK (1: terdaftar, 0: tidak). | 0 (tidak terdaftar) |
| **Jumlah Unduhan** | Scraping (Google Play Store) | Jumlah unduhan aplikasi sebagai indikator popularitas. | 10.000 |
| **Kategori Masalah** | Pengguna (formulir pelaporan) | Kategori spesifik dari laporan pengguna (misalnya, bunga tinggi, ancaman). | “Ancaman/Penagihan Kasar” |
| **Bukti (File)** | Pengguna (formulir pelaporan) | File pendukung seperti screenshot atau dokumen (opsional). | Screenshot pesan ancaman (PNG) |

**Catatan**:
- **Input Utama untuk ML**: Ulasan pengguna, rating, status OJK, dan kategori masalah adalah fitur kunci untuk model klasifikasi, sentimen, dan deteksi kata kunci.
- **Input Sekunder**: Jumlah unduhan digunakan untuk clustering (misalnya, aplikasi dengan unduhan rendah tapi ulasan negatif tinggi lebih mencurigakan).
- **Bukti File**: Tidak langsung masuk ke model ML, tapi digunakan untuk verifikasi manual oleh tim moderasi.

---

### **2. Bagaimana Input Dikumpulkan di Website?**
Website GetPinjol mengumpulkan input melalui dua cara utama:

1. **Input dari Pengguna (via Website)**:
   - **Formulir Pelaporan**: Pengguna mengisi formulir (seperti yang didesain sebelumnya) untuk melaporkan pengalaman buruk. Formulir ini menghasilkan input seperti:
     - Nama aplikasi.
     - Deskripsi masalah (ulasan/teks).
     - Kategori masalah (checkbox).
     - Tanggal kejadian.
     - Bukti (file opsional).
   - **Pencarian Aplikasi**: Pengguna memasukkan nama aplikasi di kolom pencarian untuk memeriksa skor risiko. Website mengambil data terkait dari database (ulasan, rating, status OJK).
   - **Contoh UI**:
     - Kolom pencarian: “Masukkan nama aplikasi (contoh: Pinjol X)”.
     - Formulir pelaporan: Seperti kode HTML sebelumnya, dengan input teks, checkbox, dan unggahan file.

2. **Input dari Sumber Eksternal (Otomatis)**:
   - **Scraping Google Play Store**: Script Python (menggunakan library seperti `google-play-scraper`) mengumpulkan:
     - Nama aplikasi, rating, jumlah unduhan, ulasan pengguna.
   - **Scraping Forum/Berita**: Menggunakan library seperti `BeautifulSoup` atau `Selenium` untuk mengambil testimoni dari Kaskus, Reddit, atau komentar berita (Detik, Kompas).
   - **Daftar OJK**: File PDF/XLS dari situs OJK diunduh dan dikonversi ke format terstruktur (misalnya, CSV) menggunakan library seperti `pandas` atau `tabula-py`.
   - **Kaggle Dataset**: Dataset Consumer Financial Complaints diunduh sebagai CSV untuk pelatihan model.

**Proses di Website**:
- **Frontend**: Pengguna memasukkan data via formulir atau pencarian (dibangun dengan Vite, HTML/CSS/JavaScript).
- **Backend**: API RESTful (dibangun dengan Flask) menerima input pengguna, mengambil data eksternal dari database, dan mengirimnya ke model ML untuk analisis.
- **Database**: Menyimpan data input (ulasan, rating, status OJK) dalam format terstruktur (misalnya, MongoDB atau MySQL).

---

### **3. Contoh Format Input**
Berikut adalah contoh format input yang masuk ke sistem GetPinjol, baik dari pengguna maupun sumber eksternal, dalam bentuk JSON (karena API RESTful biasanya menggunakan JSON untuk komunikasi).

#### **a. Input dari Pengguna (Formulir Pelaporan)**
Ketika pengguna mengisi formulir pelaporan di website, data dikirim ke backend sebagai JSON:
```json
{
  "report_id": "12345",
  "user_id": "user_789",
  "app_name": "Pinjol X",
  "category": ["high_interest", "harassment"],
  "incident_date": "2025-03-15",
  "description": "Bunga 30% per minggu, penagih mengancam via WhatsApp.",
  "evidence": "path/to/screenshot.png"
}
```
- **Sumber**: Formulir pelaporan (input teks, checkbox, file upload).
- **Penggunaan**: 
  - `description` dianalisis untuk sentimen dan kata kunci (NLP, TF-IDF).
  - `category` digunakan untuk menambah bobot risiko (misalnya, “harassment” meningkatkan skor risiko).
  - `evidence` disimpan untuk moderasi manual.
  - `app_name` digunakan untuk mencocokkan dengan data lain (OJK, Google Play).

#### **b. Input dari Scraping Google Play Store**
Data yang di-scraping dari Google Play disimpan dalam database dan diakses sebagai JSON:
```json
{
  "app_name": "Pinjol X",
  "rating": 2.5,
  "downloads": 10000,
  "reviews": [
    {"text": "Bunga tinggi, sangat menipu!", "score": 1},
    {"text": "Proses cepat tapi syarat aneh.", "score": 3},
    {"text": "Penagih mengancam keluarga!", "score": 1}
  ]
}
```
- **Sumber**: Script scraping (misalnya, `google-play-scraper`).
- **Penggunaan**:
  - `reviews.text` untuk analisis sentimen dan deteksi kata kunci.
  - `rating` dan `downloads` sebagai fitur untuk klasifikasi dan clustering.

#### **c. Input dari Daftar OJK**
Data OJK dikonversi dari PDF/XLS ke JSON:
```json
{
  "app_name": "Pinjol X",
  "ojk_status": 0
}
```
- **Sumber**: File PDF/XLS dari situs OJK, diproses dengan `pandas` atau `tabula-py`.
- **Penggunaan**: `ojk_status` sebagai fitur utama untuk klasifikasi (0 = ilegal, 1 = legal).

#### **d. Input dari Kaggle (Untuk Pelatihan)**
Dataset Consumer Financial Complaints dari Kaggle dalam format CSV, diubah ke JSON untuk pelatihan:
```json
[
  {
    "complaint_id": "123",
    "product": "Payday loan",
    "issue": "Charged fees or interest I didn't expect",
    "company": "Pinjol X",
    "label": "Ilegal"
  },
  ...
]
```
- **Sumber**: File CSV dari Kaggle.
- **Penggunaan**: Melatih model klasifikasi (fitur: teks keluhan, label: legal/ilegal).

#### **e. Input dari Pencarian Pengguna**
Ketika pengguna mencari aplikasi di website:
```json
{
  "app_name": "Pinjol X"
}
```
- **Sumber**: Kolom pencarian di website.
- **Penggunaan**: Backend mencocokkan `app_name` dengan database untuk mengambil data terkait (ulasan, rating, status OJK) dan menghitung skor risiko.

---

### **4. Integrasi dengan Website**

**Alur Input di Website**:
1. **Pengguna Mengisi Formulir atau Mencari Aplikasi**:
   - Pengguna membuka website GetPinjol dan:
     - Mengisi formulir pelaporan (contoh HTML dari diskusi sebelumnya) untuk melaporkan pengalaman buruk.
     - Memasukkan nama aplikasi di kolom pencarian untuk memeriksa risiko.
   - Frontend (Vite, JavaScript) mengirimkan data ke backend via API.

2. **Backend Memproses Input**:
   - **API Endpoint**: Misalnya, `POST /report` untuk formulir pelaporan, `GET /predict` untuk pencarian.
   - **Contoh Panggilan API** (untuk formulir):
     ```bash
     curl -X POST http://getpinjol.com/api/report \
     -H "Content-Type: application/json" \
     -d '{"app_name":"Pinjol X","description":"Bunga tinggi, ancaman!","category":["high_interest"]}'
     ```
   - Backend (Flask) menyimpan data ke database dan mengirimkan teks ulasan ke model ML.

3. **Model ML Menganalisis Input**:
   - **Analisis Sentimen**: Menggunakan NLTK VADER untuk menilai deskripsi (misalnya, “Bunga tinggi, ancaman!” → Sentimen negatif).
   - **Deteksi Kata Kunci**: TF-IDF menghitung skor untuk kata seperti “bunga tinggi” atau “ancaman”.
   - **Klasifikasi**: Model Random Forest memprediksi legal/ilegal berdasarkan fitur (rating, status OJK, sentimen).
   - **Clustering**: K-Means mengelompokkan aplikasi untuk konfirmasi pola berisiko.
   - **Skor Risiko**: Kombinasi hasil ML (contoh: 88/100 untuk Pinjol X).

4. **Tampilan Output**:
   - Frontend menampilkan hasil analisis, misalnya:
     ```
     Pinjol X
     Skor Risiko: 88/100 [Bar Merah]
     Status OJK: Tidak Terdaftar
     Ulasan: 70% Negatif
     Rekomendasi: Hindari. Coba Pinjol Y (Legal).
     ```
   - Jika pengguna melaporkan, mereka mendapat notifikasi: “Laporan diterima, sedang ditinjau.”

**Struktur Database** (contoh MongoDB):
```json
{
  "apps": [
    {
      "app_name": "Pinjol X",
      "ojk_status": 0,
      "rating": 2.5,
      "downloads": 10000,
      "reviews": [
        {"text": "Bunga tinggi, ancaman!", "sentiment": "negatif"},
        ...
      ],
      "risk_score": 88
    }
  ],
  "reports": [
    {
      "report_id": "12345",
      "app_name": "Pinjol X",
      "description": "Bunga tinggi, ancaman!",
      "category": ["high_interest", "harassment"],
      "evidence": "path/to/screenshot.png",
      "status": "pending"
    }
  ]
}
```

---

### **Contoh Kode Integrasi di Website**

Berikut adalah contoh kode sederhana untuk **backend** (Flask) dan **frontend** (JavaScript dengan Vite) yang menangani input dari formulir pelaporan dan menampilkan hasil deteksi.

#### **Backend (Flask)**
```python
from flask import Flask, request, jsonify
from sklearn.ensemble import RandomForestClassifier
from nltk.sentiment.vader import SentimentIntensityAnalyzer
from sklearn.feature_extraction.text import TfidfVectorizer
import pandas as pd
import numpy as np
import nltk

nltk.download('vader_lexicon')

app = Flask(__name__)

# Model ML dan VADER (contoh sederhana, asumsikan sudah dilatih)
sia = SentimentIntensityAnalyzer()
vectorizer = TfidfVectorizer(max_features=10, stop_words='english')
clf = RandomForestClassifier().fit([[2.5, 0, 0.8, 0.9], [4.2, 1, 0.2, 0.1]], ['Ilegal', 'Legal'])  # Dummy model

@app.route('/report', methods=['POST'])
def handle_report():
    data = request.json
    app_name = data['app_name']
    description = data['description']
    category = data['category']
    
    # Analisis Sentimen
    sentiment_score = sia.polarity_scores(description)['compound']
    sentiment_risk = (1 - (sentiment_score + 1) / 2)
    
    # Deteksi Kata Kunci
    tfidf_score = np.mean(vectorizer.transform([description]).toarray())
    keyword_risk = tfidf_score / tfidf_score.max() if tfidf_score.max() > 0 else 0
    
    # Klasifikasi (asumsikan rating dan ojk_status dari database)
    rating = 2.5  # Contoh dari database
    ojk_status = 0  # Contoh dari database
    features = [[rating, ojk_status, sentiment_risk, keyword_risk]]
    prediction = clf.predict(features)[0]
    proba = clf.predict_proba(features)[0][0] * 100
    
    # Skor Risiko
    risk_score = (sentiment_risk * 0.3 + keyword_risk * 0.3 + (1 - ojk_status) * 0.3 + (1 - rating / 5) * 0.1) * 100
    
    # Simpan ke database (contoh, tidak diimplementasikan)
    # db.reports.insert_one(data)
    
    return jsonify({
        'app_name': app_name,
        'prediction': prediction,
        'risk_score': risk_score,
        'message': 'Laporan diterima dan dianalisis.'
    })

if __name__ == '__main__':
    app.run(debug=True)
```

#### **Frontend (JavaScript dengan Vite)**
```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GetPinjol - Laporkan Pinjol</title>
    <style>
        body { font-family: Arial, sans-serif; padding: 20px; }
        .form-container { max-width: 600px; margin: auto; }
        input, textarea { width: 100%; padding: 8px; margin: 5px 0; }
        button { padding: 10px; background: #28a745; color: white; border: none; }
        #result { margin-top: 20px; }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Laporkan Aplikasi Pinjol</h2>
        <form id="report-form">
            <label>Nama Aplikasi:</label>
            <input type="text" id="app-name" required>
            <label>Deskripsi Masalah:</label>
            <textarea id="description" required></textarea>
            <label>Kategori Masalah:</label>
            <input type="checkbox" name="category" value="high_interest"> Bunga Tinggi
            <input type="checkbox" name="category" value="harassment"> Ancaman
            <button type="submit">Kirim Laporan</button>
        </form>
        <div id="result"></div>
    </div>
    <script type="module">
        import { fetch } from 'vite';

        document.getElementById('report-form').addEventListener('submit', async (e) => {
            e.preventDefault();
            const appName = document.getElementById('app-name').value;
            const description = document.getElementById('description').value;
            const categories = Array.from(document.querySelectorAll('input[name="category"]:checked')).map(c => c.value);

            const response = await fetch('http://localhost:5000/report', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    app_name: appName,
                    description: description,
                    category: categories
                })
            });
            const result = await response.json();
            
            document.getElementById('result').innerHTML = `
                <h3>Hasil Analisis</h3>
                <p>Aplikasi: ${result.app_name}</p>
                <p>Prediksi: ${result.prediction}</p>
                <p>Skor Risiko: ${result.risk_score.toFixed(2)}/100</p>
                <p>${result.message}</p>
            `;
        });
    </script>
</body>
</html>
```

**Penjelasan Kode**:
- **Backend**: Menerima JSON dari formulir, menjalankan analisis ML (sentimen, kata kunci, klasifikasi), dan mengembalikan hasil (prediksi, skor risiko).
- **Frontend**: Formulir sederhana mengumpulkan input pengguna (nama aplikasi, deskripsi, kategori) dan mengirimnya ke API. Hasil ditampilkan di halaman.
- **Catatan**: Kode ini adalah prototipe. Dalam produksi, tambahkan:
  - Validasi input (misalnya, regex untuk nama aplikasi).
  - Autentikasi pengguna (login untuk mencegah spam).
  - Integrasi database (MongoDB/MySQL).
  - CAPTCHA (seperti di formulir sebelumnya).

---

### **Kaitan dengan Diskusi Sebelumnya**
- **Formulir Pelaporan**: Input dari formulir (nama aplikasi, deskripsi, kategori) sesuai dengan desain HTML sebelumnya, dengan tambahan pengiriman ke API.
- **Pencegahan Penyalahgunaan**: Formulir di website bisa menyertakan CAPTCHA dan ToS (seperti saran sebelumnya) untuk mencegah laporan palsu dari kompetitor.
- **Dokumen Proyek**: Input menggunakan dataset OJK, Google Play, dan Kaggle, serta diolah dengan Scikit-Learn dan Flask, sesuai rencana proyek.
- **Contoh Deteksi**: Kode di atas adalah implementasi sederhana dari proses deteksi (sentimen, klasifikasi, kata kunci) yang dijelaskan sebelumnya.

---

### **Jika Masih Ada Pertanyaan**
- **Format Input Lain**: Apakah kamu ingin contoh input untuk sumber lain (misalnya, scraping Google Play atau OJK)?
- **Detail Teknis**: Butuh penjelasan lebih tentang bagaimana input diproses oleh model ML tertentu (misalnya, TF-IDF atau Random Forest)?
- **Desain Website**: Ingin mockup lebih rinci untuk halaman formulir atau hasil deteksi (misalnya, Figma)?
- **Kode Tambahan**: Perlu contoh untuk scraping data atau integrasi database?

Silakan beri tahu apa yang masih kurang jelas atau bagian mana yang perlu diperdalam!