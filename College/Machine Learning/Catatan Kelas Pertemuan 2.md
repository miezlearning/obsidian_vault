# Klasifikasi

## Pengertian

Pengelompokkan beda, data , atau informasi ke dalam kategori-kategori tertentu berdasarkan kesamaan ciri atau karakteristik klasifikasi bertujua nuntuk mempermudha pengorganisasian, pemahaman, dan anlisis data.


Kata Kunci Klasifikasi : Pengelompokkan

Contoh :
- Berdasarkan gender atau kelamin
- Berdasarkan warna pakaian
- Berdasarkan umur




Tujuan : memudahkan prose aanalisis data 
Proses : klasifikasi melibatkan proses pengelompokkan beda, [[Data Mining]]
Kategori : Bisa kelas, yang dibuat dalam proses klasifikasi
Karakterisktik : membedakan kategori satu saama kategor ilain
Jenis Klasifikasi : klasifikasi kualititaif, dan kuantitatif


Kualittatif : berdasarkan tidak diukur secara numerik ( kelamin, warna, bentuk )
Kuantitatif : berdasarkan ciri atau karakteristik yang dapat diukur secara numerik (usia, tinggi badan, dan berat badan)

Jenis algoirtma : 
Berikut penjelasan singkat untuk setiap jenis algoritma:

1. **K-Means Neighbors**  
   (Algoritma clustering untuk mengelompokkan data berdasarkan kemiripan.)

2. **Decision Tree**  
   (Algoritma berbasis pohon keputusan untuk klasifikasi atau regresi dengan memecah data berdasarkan fitur.)

3. **Naive Bayes**  
   (Algoritma klasifikasi probabilistik berdasarkan teorema Bayes, cocok untuk data teks atau kategori.)

4. **Support Vector Machine (SVM)**  
   (Algoritma untuk klasifikasi atau regresi dengan mencari hyperplane terbaik untuk memisahkan kelas.)

5. **Random Forest**  
   (Algoritma ensemble yang menggabungkan banyak decision tree untuk meningkatkan akurasi dan mengurangi overfitting.)

6. **Artificial Neural Network (ANN)**  / Jaringan Saraf Tiruan 
   (Algoritma terinspirasi dari otak manusia, terdiri dari lapisan neuron untuk memodelkan hubungan kompleks dalam data.)


Hari ini diskusi tentang KNN dan ANN 


Pemilihan Algoritma , tergantung jenis data , dipengaruhi juga oleh ukuran dataset, akurasi 

**Pemilihan Algoritma**  
Pemilihan algoritma tergantung pada:  
1. **Jenis Data**:  
   - Data terstruktur (numerik/kategorikal): Decision Tree, Random Forest.  
   - Data teks/gambar: Naive Bayes, Neural Network.  

2. **Ukuran Dataset**:  
   - Dataset kecil: Naive Bayes, SVM.  
   - Dataset besar: Random Forest, Neural Network.  

3. **Akurasi yang Diinginkan**:  
   - Akurasi tinggi: Random Forest, Neural Network.  
   - Cepat dan sederhana: Decision Tree, Naive Bayes.  

Intinya: Pilih algoritma yang sesuai dengan karakteristik data, ukuran dataset, dan kebutuhan akurasi.

Berikut perbaikan teks Anda:

---

**Citra Gambar**: Algoritma klasifikasi dapat digunakan untuk mengidentifikasi objek dalam gambar.  

**Klasifikasi Email**: Algoritma klasifikasi dapat digunakan untuk mengkategorikan email sebagai spam atau bukan spam.  

**Analisis Sentimen**: Algoritma klasifikasi dapat digunakan untuk menentukan sentimen (positif, negatif, atau netral) dari teks, seperti ulasan atau komentar. 



---

**2 Set/Himpunan**:  
Ada dua himpunan data yang digunakan, yaitu untuk **testing** dan **pelatihan (training)**.  

**Struktur Data**:  
Setiap record terdiri dari sejumlah atribut, dan salah satu atribut tersebut adalah **atribut kelas** atau **label**.  

**Tujuan**:  
Mencari model yang dapat memprediksi atribut kelas sebagai fungsi dari nilai atribut lainnya. Tujuannya adalah agar record yang belum diketahui kelasnya dapat diberi label seakurat mungkin.  

**Evaluasi Model**:  
Untuk mengetahui dan menentukan tingkat akurasi model, digunakan **test set**. Biasanya, dataset dibagi menjadi dua bagian:  
1. **Training Set**: Digunakan untuk membangun model.  
2. **Test Set**: Digunakan untuk memvalidasi model tersebut.  


Langkah Klasifikasi

Berikut perbaikan dan pelengkapan teks Anda:

---

**Langkah Klasifikasi**  

1. **Pembangunan Model**:  
   - Model dibangun dengan mendeskripsikan kelas-kelas yang sudah ditentukan sebelumnya.  
   - Setiap tuple/sample diasumsikan termasuk dalam salah satu kelas, yang ditunjukkan oleh atribut kelas.  
   - Tuple atau record yang digunakan untuk membangun model disebut sebagai **training set**.  
   - Model yang dihasilkan akan mempelajari pola dari data training untuk memprediksi kelas dari data baru.  

2. **Evaluasi Model**:  
   - Model yang telah dibangun diuji menggunakan **test set** (data yang tidak digunakan selama pelatihan).  
   - Tujuannya adalah untuk mengukur akurasi model dalam memprediksi kelas yang benar.  

3. **Penggunaan Model**:  
   - Setelah model dianggap akurat, model tersebut dapat digunakan untuk memprediksi kelas dari data baru yang belum diketahui labelnya.  

---

**Contoh Alur**:  
- **Training Set**: Data dengan label yang digunakan untuk melatih model.  
- **Test Set**: Data tanpa label yang digunakan untuk menguji akurasi model.  
- **Prediksi**: Model digunakan untuk memberi label pada data baru berdasarkan pola yang dipelajari.  

Independen adalah tidak dilibatkan saat pembangunan model.

Semoga lebih jelas dan lengkap! 😊


**Klasifikasi dengan K-Nearest Neighbors (KNN)**  

K-Nearest Neighbors (KNN) adalah salah satu algoritma klasifikasi sederhana yang bekerja berdasarkan prinsip **"tetangga terdekat"**. Algoritma ini memprediksi kelas suatu data dengan melihat kelas dari data-data terdekat di sekitarnya.

---

### **Cara Kerja KNN:**
1. **Input**:  
   - Data training (data yang sudah memiliki label).  
   - Data baru yang akan diprediksi kelasnya.  
   - Nilai **k** (jumlah tetangga terdekat yang akan dipertimbangkan).  

2. **Langkah-Langkah**:  
   - Hitung jarak antara data baru dengan setiap data training menggunakan metode jarak (misalnya, Euclidean Distance).  
   - Pilih **k** data training dengan jarak terdekat.  
   - Lihat kelas dari **k** tetangga terdekat tersebut.  
   - Prediksi kelas data baru berdasarkan kelas mayoritas dari **k** tetangga terdekat.  

3. **Output**:  
   - Kelas yang diprediksi untuk data baru.  

---

### **Contoh Sederhana:**
Misalnya, kita memiliki data training berupa titik-titik di bidang 2D dengan dua kelas: **Merah** dan **Biru**.  
- Data baru: Titik dengan koordinat (3, 4).  
- Nilai **k** = 3.  
- Langkah:  
  1. Hitung jarak titik (3, 4) ke semua titik training.  
  2. Ambil 3 titik terdekat.  
  3. Jika 2 dari 3 tetangga terdekat adalah **Merah**, maka titik (3, 4) diprediksi sebagai **Merah**.  

---

### **Keuntungan KNN:**
- Sederhana dan mudah diimplementasikan.  
- Tidak memerlukan proses pelatihan yang rumit (hanya menyimpan data training).  
- Dapat digunakan untuk klasifikasi dan regresi.  

---

### **Kekurangan KNN:**
- Sensitif terhadap data noise atau outlier.  
- Perlu memilih nilai **k** yang optimal (terlalu kecil atau besar dapat mengurangi akurasi).  
- Komputasi lambat untuk dataset besar karena harus menghitung jarak ke semua data training.  

---

### **Tips Memilih Nilai k:**
- Gunakan nilai **k** ganjil untuk menghindari hasil seri (misalnya, k = 3, 5, 7).  
- Lakukan eksperimen dengan nilai **k** berbeda untuk menemukan yang terbaik.  

---

**Intinya**:  
KNN adalah algoritma klasifikasi yang mengandalkan tetangga terdekat untuk memprediksi kelas data baru. Meskipun sederhana, pemilihan nilai **k** dan metode penghitungan jarak sangat penting untuk hasil yang akurat.

### NOTE KNN
Jika ada data baru maka proses training mulai ulang lagi.


Kapan IBL digunakan?
pada situasi dimana terdapat banyka data pencilan yang menebabkan representasi model berbasis aturan, model distribusi kepadatan peluang atau model pengklasifikasian.


Data pencilan ada data yang keluar dari kelompok atau labelnya, seperti bullet biru masuk ke daerah bullet merah , begitu juga sebaliknya.


### **Menentukan Nilai K Terbaik dalam K-Nearest Neighbors (KNN)**

Dalam **KNN (K-Nearest Neighbors)**, **K** adalah jumlah tetangga terdekat yang digunakan untuk menentukan kelas atau prediksi suatu data.

🔹 **Kecil vs. Besar**:

- **K terlalu kecil** (misalnya K=1 atau K=3) → Model terlalu sensitif terhadap **outlier**, bisa menyebabkan **overfitting**.
- **K terlalu besar** (misalnya K=50) → Model terlalu "smooth", bisa kehilangan pola lokal dan menyebabkan **underfitting**.

---

### **Bagaimana Data Pencilan (Outlier) Mempengaruhi K?**

📌 **Jika ada banyak outlier**, nilai K yang **terlalu kecil** bisa menyebabkan prediksi salah karena outlier lebih berpengaruh.

📌 **Jika K lebih besar**, outlier menjadi kurang berdampak karena mayoritas tetangga memiliki label yang lebih "umum".

---

### **Cara Menentukan Nilai K Terbaik**

✅ **1. Gunakan Cross-Validation**  
Coba berbagai nilai K dan cek akurasi rata-rata dengan **k-fold cross-validation**.

```python
from sklearn.model_selection import cross_val_score
from sklearn.neighbors import KNeighborsClassifier
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split

# Load dataset
iris = load_iris()
X_train, X_test, y_train, y_test = train_test_split(iris.data, iris.target, test_size=0.2, random_state=42)

# Coba beberapa nilai K
for k in range(1, 21):
    knn = KNeighborsClassifier(n_neighbors=k)
    scores = cross_val_score(knn, X_train, y_train, cv=5)
    print(f"K={k}, Akurasi Rata-rata: {scores.mean():.4f}")
```

📌 **Cari K dengan akurasi tertinggi!**

---

✅ **2. Gunakan Plot Error Rate**  
Grafik **error rate vs K** dapat membantu menemukan titik optimal.

```python
import matplotlib.pyplot as plt
import numpy as np

error_rates = []
K_range = range(1, 21)

for k in K_range:
    knn = KNeighborsClassifier(n_neighbors=k)
    knn.fit(X_train, y_train)
    error = 1 - knn.score(X_test, y_test)
    error_rates.append(error)

plt.figure(figsize=(8, 5))
plt.plot(K_range, error_rates, marker='o', linestyle='dashed', color='b')
plt.xlabel('Nilai K')
plt.ylabel('Error Rate')
plt.title('Error Rate vs K')
plt.show()
```

📌 **Pilih K di mana error mulai stabil atau minimum!**

---

✅ **3. Gunakan Metode "Rule of Thumb"**  
Cara cepat untuk perkiraan awal nilai **K**:  
K=nK = \sqrt{n}  
di mana **n** adalah jumlah data dalam training set.

Misalnya:

- Jika **n = 100**, maka K=100=10K = \sqrt{100} = 10.
- Jika **n = 500**, maka K=500≈22K = \sqrt{500} \approx 22.

Namun, ini **hanya perkiraan awal**, tetap disarankan menggunakan cross-validation!

---

### **Kesimpulan**

🔹 **Jika ada banyak outlier** → **Gunakan K lebih besar** (misal **5-10**), agar hasil lebih stabil.  
🔹 **Gunakan cross-validation** untuk mencari **K terbaik** yang memberikan akurasi tertinggi.  
🔹 **Plot error rate** bisa membantu melihat pola kesalahan dan memilih **K optimal**.

💡 **Tidak ada K terbaik yang universal, semua tergantung pada dataset!** 🚀



Algoritma Knn.fit
- Tentukan jumlah tetangga yang akan di hitung
- Hitung jarak dari data baru dengna semua data ltih yang adalah.urutkan hasilnya berdasarkan jarak mulai dari terkecil ke terbesar.



	Berikut versi yang telah disempurnakan:

---

### **Contoh Kasus:**

Misalkan ada sebuah rumah yang berada tepat di tengah perbatasan antara **Kota X** dan **Kabupaten Y**, sehingga sulit untuk menentukan apakah rumah tersebut termasuk dalam wilayah Kota X atau Kabupaten Y.

Kita dapat menentukan wilayahnya menggunakan algoritma **K-Nearest Neighbors (KNN)** dengan melibatkan jarak antara rumah tersebut dengan rumah-rumah lain di sekitarnya yang sudah diketahui wilayahnya.

---

### **Langkah-Langkah Algoritma KNN:**

1️⃣ **Menentukan jumlah tetangga (K)**

- Tentukan jumlah tetangga terdekat yang akan dipertimbangkan.
- Misalnya, kita pilih **K = 3**, artinya kita akan melihat **3 rumah terdekat** sebagai referensi.

2️⃣ **Menghitung jarak ke setiap tetangga**

- Hitung jarak rumah tersebut dengan semua rumah di sekitarnya yang sudah diketahui wilayahnya.
- Bisa menggunakan metode seperti **Euclidean Distance** atau **Manhattan Distance**.

3️⃣ **Mengurutkan hasil berdasarkan jarak**

- Urutkan rumah-rumah di sekitar berdasarkan jarak **dari yang paling dekat ke yang paling jauh**.

4️⃣ **Mengambil K tetangga terdekat**

- Pilih **3 rumah terdekat** dari hasil pengurutan tadi.
- Lihat apakah rumah-rumah tersebut termasuk dalam **Kota X** atau **Kabupaten Y**.

5️⃣ **Menentukan wilayah berdasarkan mayoritas**

- Jika mayoritas tetangga termasuk dalam **Kota X**, maka rumah tersebut dikategorikan dalam **Kota X**.
- Jika mayoritas tetangga termasuk dalam **Kabupaten Y**, maka rumah tersebut dikategorikan dalam **Kabupaten Y**.

---

### **Kesimpulan**

Dengan menggunakan algoritma **KNN**, kita dapat menentukan wilayah rumah tersebut berdasarkan **mayoritas tetangga terdekat**. Jika mayoritas rumah tetangga berada di Kota X, maka rumah tersebut kemungkinan besar termasuk **Kota X**, dan sebaliknya.

📌 **Semakin besar nilai K, semakin stabil hasilnya**, tetapi jika K terlalu besar, perhitungan bisa menjadi kurang akurat karena melibatkan rumah yang terlalu jauh. 🚀


ConrToh kasus: 

Bila dari 3 tetangga tersebut terdapat ada 2 rumah yang termasuk


Misal k = 5 class 3, haislnya bisa 2 2 1,

nilai ganjil tidak selalu ketemu nilai akhirnya berapa. 

![[Pasted image 20250213095804.png]]

![[Pasted image 20250213095818.png]]

![[Pasted image 20250213095829.png]]

Dalam K-Nearest Neighbors (KNN), Euclidean Distance digunakan untuk menghitung jarak antara data point yang ingin diklasifikasikan dengan semua data point dalam training set. Jarak ini digunakan untuk menemukan K data point terdekat (tetangga terdekat) dengan data point baru tersebut.

**Rumus (dalam KNN):**

Misalkan kita punya:

- **x:** Data point baru yang ingin diklasifikasikan.
    
- **xᵢ:** Data point ke-i dalam training set.
    

Maka, jarak Euclidean antara **x** dan **xᵢ** dihitung sebagai:

d(x, xᵢ) = √((x₁ - xᵢ₁) ² + (x₂ - xᵢ₂) ² + ... + (xₙ - xᵢₙ)²)

	**Penjelasan:**

- **d(x, xᵢ):** Jarak Euclidean antara data point baru **x** dan data point ke-i dalam training set.
    
- **x₁, x₂, ..., xₙ:** Fitur-fitur dari data point baru **x**.
    
- **xᵢ₁, xᵢ₂, ..., xᵢₙ:** Fitur-fitur dari data point ke-i dalam training set.
    
- **n:** Jumlah fitur (dimensi) dari data point.
    

**Singkatnya:**

KNN menggunakan Euclidean Distance untuk mengukur "kedekatan" antara data point baru dan data point di training set. Data point dengan jarak terpendek dianggap sebagai tetangga terdekat.



11 