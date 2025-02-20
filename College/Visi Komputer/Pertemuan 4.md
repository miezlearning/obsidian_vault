Dalam **Computer Vision**, segmentasi gambar memiliki beberapa pendekatan utama. Selain **Region-Based Segmentation**, dua metode lainnya yang populer adalah:

1. **Edge-Based Segmentation** (Segmentasi Berbasis Tepi)
    
    - Fokus pada deteksi batas antara objek menggunakan metode seperti **Canny Edge Detection, Sobel Filter, atau Laplacian Filter**.
    - Berguna ketika objek memiliki kontras tinggi dibandingkan dengan latar belakangnya.
    - Contoh: Mendeteksi kontur wajah atau teks dalam gambar.
2. **Pixel-Based Segmentation (Clustering-Based)**
    
    - Setiap piksel dianalisis secara individual berdasarkan warna atau intensitasnya, kemudian dikelompokkan.
    - Teknik populer: **K-Means Clustering, Mean-Shift, Gaussian Mixture Models (GMM)**.
    - Contoh: Memisahkan langit, air, dan daratan dalam citra satelit.

Jadi, tiga jenis utama segmentasi dalam **Computer Vision** adalah:

- **Region-Based Segmentation** (berdasarkan area atau kesamaan warna/tekstur).
- **Edge-Based Segmentation** (berdasarkan deteksi tepi atau perubahan kontras).
- **Pixel-Based Segmentation** (berdasarkan klasterisasi atau distribusi warna/intensitas).


Binerisasi :  Memisahkan pbjek dari latar yang tidak dibutuhkan.

Citra defaultnya :RGB

[Panah ke box untuk knowledge box.](<Metode iterasi untuk menemukan **nilai threshold \( T \)** sering digunakan dalam **Thresholding Adaptive** dalam segmentasi gambar. Metode ini mencari nilai \( T \) optimal untuk membagi gambar menjadi **foreground** (objek) dan **background** (latar belakang).

---

[### **Langkah-langkah Iterasi Nilai Threshold \( T \)**
1. **Inisialisasi \( T \) awal**  
   - Bisa dimulai dengan nilai **rata-rata** intensitas piksel dalam gambar:  
   - $$
     [
     T = \frac{1}{N} \sum I(x, y)
     ]
   $$
   - Atau bisa dimulai dari nilai tengah antara piksel terang dan gelap.

2. **Pisahkan gambar menjadi dua grup berdasarkan \( T \)**  
   - **Grup 1 (\( G_1 \))**: Piksel dengan intensitas **lebih kecil** dari \( T \) → (Background).  
   - **Grup 2 (\( G_2 \))**: Piksel dengan intensitas **lebih besar atau sama** dengan \( T \) → (Foreground).  

3. **Hitung rata-rata intensitas untuk setiap grup**  
   - Rata-rata intensitas **\( \mu_1 \)** untuk \( G_1 \):  
$$
     \[
     \mu_1 = \frac{1}{|G_1|} \sum_{I(x,y) \in G_1} I(x, y)
     \]
   - Rata-rata intensitas \( \mu_2 \) untuk \( G_2 \):  
     \[
     \mu_2 = \frac{1}{|G_2|} \sum_{I(x,y) \in G_2} I(x, y)
     \]
   $$

4. **Hitung threshold baru \( T_{\text{baru}} \)**  
   - Dengan rata-rata kedua grup:  
   $$
     \[
     T_{\text{baru}} = \frac{\mu_1 + \mu_2}{2}
     \]
$$
1. **Periksa konvergensi**  
   - Jika perbedaan antara \( T_{\text{baru}} \) dan \( T_{\text{lama}} \) lebih kecil dari ambang batas tertentu $$(\( \epsilon \))$$$$
     \[
     |T_{\text{baru}} - T_{\text{lama}}| %3C \epsilon
     \]
   $$
     maka iterasi dihentikan.

   - Jika belum, ulangi dari langkah 2 dengan **\( T_{\text{lama}} = T_{\text{baru}} \)**.

---

### **Implementasi dalam Python (OpenCV + NumPy)**
Kamu bisa coba koding berikut untuk menerapkan metode iterasi threshold:

```python
import cv2
import numpy as np

def iterative_threshold(image, epsilon=1e-3):
    T = np.mean(image)  # Inisialisasi T awal
    while True:
        # Pisahkan piksel berdasarkan threshold T
        G1 = image[image < T]
        G2 = image[image %3E= T]

        # Hitung rata-rata intensitas setiap grup
        mu1 = np.mean(G1) if len(G1) > 0 else 0
        mu2 = np.mean(G2) if len(G2) > 0 else 0

        # Update nilai threshold
        T_new = (mu1 + mu2) / 2

        # Cek konvergensi
        if abs(T_new - T) < epsilon:
            break

        T = T_new

    return T

# Baca gambar grayscale
image = cv2.imread("image.jpg", cv2.IMREAD_GRAYSCALE)

# Cari threshold optimal
optimal_T = iterative_threshold(image)
print("Threshold optimal:", optimal_T)

# Terapkan thresholding
_, binary_image = cv2.threshold(image, optimal_T, 255, cv2.THRESH_BINARY)

# Tampilkan hasil
cv2.imshow("Binary Image", binary_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### **Keunggulan Metode Ini**
✅ **Otomatis** menyesuaikan threshold tanpa harus memilih nilai secara manual.  
✅ **Cocok untuk gambar binerisasi sederhana** dengan kontras yang cukup tinggi.  
✅ **Lebih cepat daripada metode Otsu** jika hanya mencari threshold dasar.

Kamu mau coba eksperimen dengan dataset tertentu? 🚀>)](<Mari kita lakukan iterasi threshold \( T \) pada citra **5x5** yang kamu berikan.

---

### **Data Citra (Grayscale) 5x5**

$$
\begin{bmatrix}
200 & 170 & 150 & 150 & 120 \\
190 & 50  & 70  & 230 & 100 \\
\end{bmatrix}
$$

$$

Kita akan menggunakan **metode iterasi nilai threshold** seperti yang sudah dijelaskan.

---

### **Langkah-Langkah Perhitungan Iteratif \( T \)**

#### **1. Inisialisasi \( T \) awal**  
Kita mulai dengan nilai rata-rata intensitas:


T = \frac{200 + 170 + 150 + 150 + 120 + 190 + 50 + 70 + 230 + 100}{10}
$$

\[
T = \frac{1430}{10} = 143
\]

---

#### **2. Pisahkan menjadi dua grup berdasarkan \( T \)**
- **Grup 1 (\( G_1 \)):** Piksel \( %3C 143 \) → **{50, 70, 100, 120}**  
- **Grup 2 (\( G_2 \)):** Piksel \( \geq 143 \) → **{150, 150, 170, 190, 200, 230}**

---

#### **3. Hitung rata-rata setiap grup**
- **Rata-rata \( \mu_1 \) untuk \( G_1 \)**  
  \[
  \mu_1 = \frac{50 + 70 + 100 + 120}{4} = \frac{340}{4} = 85
  \]

- **Rata-rata \( \mu_2 \) untuk \( G_2 \)**  
  \[
  \mu_2 = \frac{150 + 150 + 170 + 190 + 200 + 230}{6} = \frac{1090}{6} \approx 181.67
  \]

---

#### **4. Hitung \( T \) baru**
$$

T_{\text{baru}} = \frac{\mu_1 + \mu_2}{2} = \frac{85 + 181.67}{2} = \frac{266.67}{2} = 133.33



$$
---

#### **5. Periksa konvergensi**  
$$

|143 - 133.33| = 9.67
$$
Kita bandingkan nilai $$( T_{\text{lama}} x\)$$dengan $$\( T_{\text{baru}} \):$$


Karena perbedaan masih cukup besar, kita lanjutkan iterasi dengan \( T = 133.33 \).

---

#### **6. Iterasi Kedua**
- **Grup 1 (\( G_1 \)):** Piksel \( < 133.33 \) → **{50, 70, 100, 120}**  
- **Grup 2 (\( G_2 \)):** Piksel \( \geq 133.33 \) → **{150, 150, 170, 190, 200, 230}**

*Grup tetap sama seperti iterasi pertama, sehingga \( \mu_1 \) dan \( \mu_2 \) juga sama, dan \( T \) tidak berubah signifikan.*

---

### **Kesimpulan**
Karena \( T \) sudah hampir konvergen, kita anggap **Threshold optimal** untuk citra ini adalah **133**.  
Jika diterapkan thresholding binerisasi:
- Piksel \( \geq 133 \) → **Putih (255)**
- Piksel \( < 133 \) → **Hitam (0)**

Citra hasil thresholding:

\[
\begin{bmatrix}
255 & 255 & 255 & 255 & 0 \\
255 & 0  & 0  & 255 & 0 \\
\end{bmatrix}
\]

Itu contoh perhitungan manualnya! Kalau mau eksperimen dengan dataset lebih besar, bisa coba pakai Python + OpenCV. 🚀>)
