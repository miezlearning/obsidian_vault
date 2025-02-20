**Model Neuron** adalah representasi matematis dari cara kerja sel saraf (neuron) dalam otak manusia, yang digunakan dalam **Jaringan Syaraf Tiruan (JST)** untuk memproses informasi.

### **Bagian Utama Model Neuron:**

1. **Input** → Data masuk (bisa dari sensor, gambar, teks, dll.).
2. **Bobot (Weight)** → Setiap input dikalikan dengan bobot untuk menentukan seberapa penting input tersebut.
3. **Penjumlahan (Summation)** → Semua input berbobot dijumlahkan.
4. **Fungsi Aktivasi** → Mengubah hasil penjumlahan menjadi output yang lebih terkontrol, misalnya **0 atau 1 (step function), antara 0-1 (sigmoid), atau nilai lain (ReLU, tanh, dll.).**
5. **Output** → Hasil akhir yang digunakan untuk keputusan atau diteruskan ke neuron lain.

### **Analoginya**

Model neuron mirip seperti keputusan manusia:

- **Input** = Informasi yang kita terima.
- **Bobot** = Seberapa penting informasi itu buat kita.
- **Penjumlahan** = Kita menggabungkan semua informasi.
- **Fungsi Aktivasi** = Kita memutuskan mau bertindak atau tidak berdasarkan informasi tadi.
- **Output** = Keputusan akhir kita.

Contoh di AI:  
Misalnya, model neuron digunakan untuk mendeteksi spam. Email masuk dianalisis berdasarkan kata-kata tertentu (**input**), dihitung seberapa mencurigakan (**bobot & penjumlahan**), lalu ditentukan apakah **spam atau bukan** (**output**). 😊