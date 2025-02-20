**Selamat pagi/siang/sore semuanya,**

Hari ini saya akan mempresentasikan penelitian yang berjudul **"Analisis Sentimen Terhadap Opini Masyarakat Tentang Vaksin Covid-19 Menggunakan Algoritma Naïve Bayes Classifier."**

### **Pendahuluan**

Pandemi COVID-19 telah membawa banyak perubahan dalam kehidupan sosial dan ekonomi masyarakat. Salah satu langkah utama yang diambil untuk mengatasi pandemi ini adalah vaksinasi. Namun, kebijakan vaksinasi mendapat berbagai tanggapan dari masyarakat, terutama di media sosial seperti Twitter. Oleh karena itu, penelitian ini bertujuan untuk menganalisis sentimen masyarakat Indonesia terhadap vaksinasi COVID-19 berdasarkan data tweet yang dikumpulkan.

### **Metode Penelitian**

Dalam penelitian ini, kami menggunakan teknik _data mining_ dengan beberapa tahapan utama:

1. **Pengumpulan Data:**
    
    - Data dikumpulkan dari Twitter menggunakan API.
    - Sebanyak **3.780 tweet** terkait vaksinasi COVID-19 dikumpulkan dan disimpan dalam format CSV.
2. **Data Preparasi:**
    
    - _Cleansing_ → Menghapus URL, tanda baca, dan karakter yang tidak relevan.
    - _Convert emoticon_ → Mengubah emotikon menjadi teks.
    - _Tokenization_ → Memecah kalimat menjadi kata-kata.
    - _Stemming & Stopword Removal_ → Mengubah kata ke bentuk dasar dan menghapus kata tidak penting.
    - _TF-IDF Weighting_ → Memberikan bobot pada kata berdasarkan tingkat kepentingannya.
3. **Modeling Data Mining:**
    
    - Kami menggunakan **Naïve Bayes Classifier**, salah satu metode klasifikasi berbasis probabilitas.
    - Model ini memprediksi apakah sebuah tweet memiliki sentimen **positif, netral, atau negatif** berdasarkan kata-kata yang digunakan.

### **Hasil dan Pembahasan**

Setelah proses analisis, hasilnya menunjukkan bahwa:  
✅ **60.3% tweet memiliki sentimen positif** terhadap vaksinasi.  
😐 **34.4% tweet bersifat netral.**  
❌ **Hanya 5.4% tweet yang menunjukkan sentimen negatif.**  
Selain itu, model yang digunakan memiliki tingkat akurasi sebesar **93%**, yang menunjukkan bahwa metode _Naïve Bayes Classifier_ cukup efektif dalam analisis sentimen.

### **Kesimpulan**

Berdasarkan penelitian ini, dapat disimpulkan bahwa mayoritas masyarakat Indonesia di Twitter memiliki pandangan positif terhadap vaksinasi COVID-19. Dengan tingkat akurasi yang tinggi, metode _Naïve Bayes_ terbukti dapat digunakan untuk menganalisis opini publik secara efektif.

![[Data Preparation-Romi.pdf]]