### ⚡ **Apa yang Harus Dilakukan Jika Ada Data Ekstrem (Outlier)?**

**Data ekstrem (outlier)** adalah data yang jauh berbeda dari mayoritas data lainnya. Data ini bisa muncul karena kesalahan input, gangguan sensor, atau memang ada kejadian khusus yang menyebabkan nilai ekstrem tersebut.

---

## 🔎 **1. Deteksi Data Ekstrem (Outlier Detection)**

Sebelum mengatasi outlier, kita harus mendeteksinya dulu. Beberapa teknik yang bisa digunakan:

### 📌 **a. Z-Score**

Menggunakan standar deviasi untuk menentukan seberapa jauh nilai dari rata-rata.

- Jika **Z-score > 3** atau **Z-score < -3**, maka bisa dianggap outlier.
- Contoh:
    
    ```python
    from scipy import stats
    import numpy as np
    
    data = np.array([10, 12, 11, 13, 100])  # Nilai 100 kemungkinan outlier
    z_scores = np.abs(stats.zscore(data))
    outliers = data[z_scores > 3]  # Deteksi outlier
    
    print(outliers)  # Output: [100]
    ```
    

---

### 📌 **b. IQR (Interquartile Range)**

Menggunakan rentang antar kuartil (Q1 dan Q3) untuk mendeteksi outlier.

- Jika nilai **lebih kecil dari Q1 - 1.5*IQR** atau **lebih besar dari Q3 + 1.5*IQR**, maka dianggap outlier.
- Contoh:
    
    ```python
    import numpy as np
    
    data = np.array([10, 12, 11, 13, 100])
    Q1 = np.percentile(data, 25)
    Q3 = np.percentile(data, 75)
    IQR = Q3 - Q1
    
    lower_bound = Q1 - 1.5 * IQR
    upper_bound = Q3 + 1.5 * IQR
    
    outliers = data[(data < lower_bound) | (data > upper_bound)]
    print(outliers)  # Output: [100]
    ```
    

---

## 🛠 **2. Cara Menangani Data Ekstrem (Outlier Handling)**

Setelah mendeteksi outlier, ada beberapa cara untuk menanganinya:

### ✅ **a. Hapus Data Outlier (Jika Tidak Relevan)**

- Jika data tersebut **terbukti salah atau hasil error**, lebih baik dihapus.
    
- Contoh: **Umur 200 tahun → Tidak masuk akal, bisa dihapus.**
    
    ```python
    clean_data = data[(data >= lower_bound) & (data <= upper_bound)]
    print(clean_data)  # Data tanpa outlier
    ```
    

---

### ✅ **b. Transformasi Data (Log Transform / Normalisasi)**

- Jika outlier terlalu besar, bisa gunakan **log transformation** atau **scaling** agar distribusinya lebih normal.
- Contoh:
    
    ```python
    import numpy as np
    
    data = np.array([10, 12, 11, 13, 100])
    log_transformed = np.log(data)
    print(log_transformed)  # Data lebih merata
    ```
    

---

### ✅ **c. Ganti Outlier dengan Mean/Median (Capping/Imputation)**

- Jika outlier tetap penting, bisa diganti dengan **mean atau median**.
    
- Contoh: Mengganti **harga rumah Rp 999 Miliar** dengan **median harga rumah lain**.
    
    ```python
    median_value = np.median(data[(data >= lower_bound) & (data <= upper_bound)])
    data = np.where((data < lower_bound) | (data > upper_bound), median_value, data)
    print(data)  # Outlier diganti median
    ```
    

---

### ✅ **d. Gunakan Model yang Tahan Outlier (Robust Methods)**

- Jika outlier tidak bisa dihapus, gunakan **algoritma machine learning yang lebih toleran** terhadap data ekstrem, seperti **Random Forest, Decision Tree, atau Robust Regression**.

---

## 🚀 **Kesimpulan**

📌 **Data ekstrem bisa berbahaya jika dibiarkan, tapi juga bisa mengandung informasi penting.**  
📌 **Langkah yang bisa diambil:**  
1️⃣ Deteksi dengan **Z-Score atau IQR**  
2️⃣ Hapus outlier jika memang error ❌  
3️⃣ Gunakan transformasi seperti **log atau normalisasi** 🔄  
4️⃣ Ganti dengan median jika masih relevan 📊  
5️⃣ Gunakan model yang lebih toleran terhadap outlier 🤖

🔍 **Tertarik coba deteksi outlier dari dataset yang kamu punya?** 😃