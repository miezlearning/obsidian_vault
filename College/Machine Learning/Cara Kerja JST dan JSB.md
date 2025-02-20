### **Cara Kerja Jaringan Syaraf Biologi dan Jaringan Syaraf Tiruan Berdasarkan Fausset**

**Fausset** menjelaskan bahwa cara kerja jaringan syaraf, baik yang biologis maupun tiruan, didasarkan pada prinsip **pemrosesan sinyal** dan **pembelajaran**. Berikut adalah penjelasan lebih rinci mengenai masing-masing jaringan berdasarkan konsep ini:

---

## **1. Cara Kerja Jaringan Syaraf Biologi**

Jaringan syaraf biologis terdiri dari **neuron** yang berfungsi sebagai unit pemrosesan dasar dalam sistem saraf manusia. Proses kerja jaringan syaraf biologis dapat dijelaskan dalam beberapa tahap:

### **A. Struktur Dasar Neuron Biologi**

Setiap neuron memiliki tiga bagian utama:

1. **Dendrit** → Menerima sinyal dari neuron lain.
2. **Badan Sel (Soma)** → Memproses sinyal yang diterima.
3. **Akson** → Mengirim sinyal ke neuron lain melalui sinapsis.

### **B. Proses Pemrosesan Sinyal**

4. **Penerimaan Sinyal**
    
    - Neuron menerima impuls listrik atau kimia dari neuron lain melalui **dendrit**.
5. **Integrasi Informasi**
    
    - Badan sel menggabungkan sinyal yang masuk dan menentukan apakah sinyal tersebut cukup kuat untuk diteruskan.
    - Jika **potensial aksi** mencapai ambang batas, maka sinyal akan diteruskan melalui akson.
6. **Transmisi Sinyal**
    
    - Sinyal listrik dikirim melalui **akson** menuju sinapsis.
    - Di sinapsis, sinyal listrik dapat dikonversi menjadi sinyal kimia dengan melepaskan **neurotransmitter**.
    - Neurotransmitter kemudian diterima oleh neuron lain, melanjutkan proses pemrosesan informasi.

### **C. Proses Pembelajaran dan Adaptasi**

- **Plastisitas Sinaptik** → Neuron dapat menguatkan atau melemahkan koneksi antar sel berdasarkan pengalaman dan pembelajaran.
- **Hebbian Learning** → "Neurons that fire together, wire together" → Jika dua neuron sering aktif bersamaan, hubungan di antara keduanya menjadi lebih kuat.

---

## **2. Cara Kerja Jaringan Syaraf Tiruan (JST)**

Jaringan Syaraf Tiruan (JST) meniru cara kerja jaringan syaraf biologis dengan menggunakan model matematika yang disebut **neuron buatan**. Berikut adalah tahapan cara kerja JST:

### **A. Struktur Dasar JST**

JST terdiri dari beberapa lapisan utama:

7. **Lapisan Input (Input Layer)** → Menerima data masukan.
8. **Lapisan Tersembunyi (Hidden Layer)** → Memproses informasi dengan bobot dan fungsi aktivasi.
9. **Lapisan Output (Output Layer)** → Menghasilkan prediksi atau hasil akhir.

### **B. Proses Pemrosesan Informasi di JST**

10. **Penerimaan Input**
    
    - Data masukan diberikan dalam bentuk angka (misalnya piksel gambar atau nilai numerik).
11. **Perhitungan Bobot dan Aktivasi**
    
    - Setiap neuron dalam JST memiliki **bobot (weight)** yang menentukan seberapa kuat pengaruh setiap input.
    - Input dikalikan dengan bobot dan ditambah dengan bias: z=∑(xi⋅wi)+bz = \sum (x_i \cdot w_i) + b
    - Hasilnya dilewatkan ke **fungsi aktivasi** (misalnya Sigmoid, ReLU) untuk menentukan apakah neuron akan aktif atau tidak.
12. **Forward Propagation**
    
    - Informasi diteruskan dari lapisan input ke lapisan tersembunyi, kemudian ke lapisan output.
13. **Perbandingan dengan Target (Error Calculation)**
    
    - Output dibandingkan dengan target yang diinginkan, lalu dihitung **error** (kesalahan).
14. **Backpropagation & Pembaruan Bobot**
    
    - JST menggunakan **backpropagation** untuk memperbaiki bobot berdasarkan error yang dihitung.
    - Metode **Gradient Descent** membantu JST menemukan bobot terbaik dengan mengurangi error secara bertahap.
15. **Iterasi & Pembelajaran**
    
    - Proses ini diulang berkali-kali hingga JST belajar mengenali pola dengan baik.

---

## **3. Perbandingan Cara Kerja Syaraf Biologi dan Syaraf Tiruan**

|**Aspek**|**Jaringan Syaraf Biologi**|**Jaringan Syaraf Tiruan (JST)**|
|---|---|---|
|**Struktur**|Neuron biologis dengan dendrit, soma, dan akson|Neuron buatan dengan bobot dan fungsi aktivasi|
|**Pemrosesan Sinyal**|Sinyal listrik dan kimiawi melalui neurotransmitter|Operasi matematika berbasis bobot dan aktivasi|
|**Pembelajaran**|Hebbian learning, adaptasi berdasarkan pengalaman|Backpropagation, update bobot melalui training|
|**Kecepatan**|Lambat tetapi efisien dalam energi|Cepat tetapi membutuhkan daya besar (GPU/TPU)|
|**Fleksibilitas**|Dapat beradaptasi dengan lingkungan baru|Membutuhkan dataset besar untuk belajar|
|**Transmisi Informasi**|Sinyal dikirim antar neuron melalui sinapsis|Data dihitung melalui matriks bobot|

---

## **4. Kesimpulan**

Berdasarkan konsep **Fausset**, baik jaringan syaraf biologis maupun jaringan syaraf tiruan memiliki proses pemrosesan informasi yang mirip, tetapi dengan implementasi yang berbeda:

- **Jaringan syaraf biologi** bekerja dengan sinyal listrik dan kimia serta memiliki kemampuan adaptasi alami.
- **Jaringan syaraf tiruan** menggunakan perhitungan matematika dan belajar melalui algoritma optimasi seperti **backpropagation**.

Meskipun JST meniru prinsip kerja otak, hingga saat ini kemampuannya masih terbatas dibandingkan dengan fleksibilitas dan efisiensi otak manusia. 🚀