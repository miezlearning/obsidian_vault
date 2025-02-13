Tugas dilaksanakan secara online presentasinya, dalam bentuk codingan ada juga.
Tugas : Buat program  computer vision berbasis machine learning
Masing masing harus punya jobdesknya masing masing tidak boleh tidak kerja
Pertemuan 6 sudah dikasi liat graphnya.
Ddeep learning digunakan 

Selesai mengajar ibunya sampai tanggal 6


Ibunya berangkat tanggal 21
# Konsep Dasar Warna


Citra berwarna menampilkan warna objek seperti warna aslinya 

Citra berwarna yang dimaksud adalah citra selain citra berwarna hitam putih dan citra grayscale

Citra warna memengaruhi cahaya.


Citra grayscale matriks 2d
Warna matriks 3d


Sinar tampak ( bisa diliat oleh mata manusia berkisar dari 400nm (biru ) sampai 700 nm (merah) )
Kurang dari 400 = tidak bisa diliat oleh manusia
Lebih dari 700 = tidak bisa diliat oleh manusia

Kelelawar bisa melihat dari hal diatas.




Berikut penjelasan singkat tentang model warna **RGB**, **CMY(K)**, **YCbCr**, dan **HSI**:

1. **RGB (Red, Green, Blue)**  
   - Model warna berbasis cahaya, digunakan di layar digital (monitor, TV, kamera).  
   - Warna dibuat dengan mencampurkan tiga warna primer: Merah, Hijau, dan Biru.  
   - Contoh: `(255, 0, 0)` = Merah murni.

2. **CMY(K) (Cyan, Magenta, Yellow, Key/Black)**  
   - Model warna berbasis tinta, digunakan untuk pencetakan.  
   - Warna dibuat dengan mengurangi cahaya dari putih (subtraktif).  
   - K (Key/Black) ditambahkan untuk meningkatkan kedalaman warna.

3. **YCbCr**  
   - Model warna yang memisahkan informasi kecerahan (Y) dan warna (Cb dan Cr).  
   - Digunakan dalam kompresi gambar/video (seperti JPEG dan MPEG).  
   - Y = Luminance (kecerahan), Cb = Chroma Blue, Cr = Chroma Red.

4. **HSI (Hue, Saturation, Intensity)**  
   - Model warna yang mendeskripsikan warna berdasarkan:  
     - **Hue (Rona)**: Jenis warna (misalnya merah, biru).  
     - **Saturation (Saturasi)**: Kemurnian warna.  
     - **Intensity (Intensitas)**: Kecerahan warna.  
   - Berguna untuk analisis gambar berbasis warna.

### Kesimpulan:
- **RGB** untuk layar digital.  
- **CMY(K)** untuk pencetakan.  
- **YCbCr** untuk kompresi gambar/video.  
- **HSI** untuk analisis warna berdasarkan rona, saturasi, dan intensitas.



**Konsep RGB dalam Visi Komputer (Versi Sederhana)**

RGB adalah singkatan dari **Red (Merah)**, **Green (Hijau)**, dan **Blue (Biru)**. Ini adalah model warna yang paling umum digunakan dalam visi komputer dan perangkat digital seperti kamera, monitor, dan layar ponsel. Konsepnya sederhana: semua warna yang kita lihat di layar atau gambar digital dibuat dengan mencampurkan tiga warna dasar ini dalam proporsi yang berbeda.

---

### **Cara Kerja RGB:**
1. **Tiga Warna Dasar**:  
   - **Merah (Red)**, **Hijau (Green)**, dan **Biru (Blue)** adalah warna primer dalam model RGB.  
   - Ketiga warna ini bisa digabungkan dengan intensitas yang berbeda untuk menghasilkan jutaan warna lainnya.

2. **Intensitas Warna**:  
   - Setiap warna (R, G, B) memiliki nilai intensitas dari **0** sampai **255**.  
     - **0** berarti warna itu tidak ada (gelap).  
     - **255** berarti warna itu pada intensitas maksimum (terang).  
   - Contoh:  
     - `(255, 0, 0)` = Merah murni.  
     - `(0, 255, 0)` = Hijau murni.  
     - `(0, 0, 255)` = Biru murni.  
     - `(255, 255, 255)` = Putih (semua warna dicampur dengan intensitas maksimum).  
     - `(0, 0, 0)` = Hitam (tidak ada warna).

3. **Mencampur Warna**:  
   - Dengan mengubah nilai R, G, dan B, kita bisa membuat warna apa pun.  
   - Contoh:  
     - `(255, 255, 0)` = Kuning (merah + hijau).  
     - `(0, 255, 255)` = Cyan (hijau + biru).  
     - `(255, 0, 255)` = Magenta (merah + biru).

---

### **Kenapa RGB Penting dalam Visi Komputer?**
4. **Mudah Diproses**:  
   - Gambar digital disimpan dalam format pixel, dan setiap pixel memiliki nilai RGB. Ini memudahkan komputer untuk memproses dan menganalisis gambar.

5. **Deteksi Warna**:  
   - Dalam visi komputer, kita bisa menggunakan nilai RGB untuk mendeteksi objek berdasarkan warnanya. Misalnya, mencari objek merah dalam gambar dengan mencari pixel yang memiliki nilai R tinggi dan G/B rendah.

6. **Manipulasi Gambar**:  
   - Dengan mengubah nilai RGB, kita bisa mengedit gambar, seperti mengubah kecerahan, kontras, atau memberi efek tertentu.

---

### **Contoh Sederhana:**
Bayangkan sebuah pixel dengan nilai RGB `(120, 80, 200)`. Artinya:  
- **Merah (R)** = 120 (cukup terang).  
- **Hijau (G)** = 80 (agak gelap).  
- **Biru (B)** = 200 (sangat terang).  

Warna ini akan terlihat seperti ungu kebiruan karena biru dominan, merah cukup terang, dan hijau gelap.

---

### **Kesimpulan:**
RGB adalah cara sederhana untuk merepresentasikan warna dalam dunia digital. Dengan hanya tiga nilai (R, G, B), kita bisa membuat semua warna yang kita lihat di layar. Dalam visi komputer, memahami RGB membantu kita memproses gambar, mendeteksi objek, dan melakukan analisis visual dengan lebih efektif.



model warna dua macam aditif dan subtraktif.

aditif : suatu warna dibentuk dengan mengkombinasikan energi cahaya dari ketiga warna perbandingan

subtraktif ; suatu warna dilakuka ndenga menyerap beberap komponen dari cahaya putih.

![[Pasted image 20250213080147.png]]






![[Pasted image 20250213080202.png]]





Citra rgb ke gray 

membagi tiga unsur dengna nilai intensitas maximal



black white
mencari dengan threshold


# Preprocessing.

Dilakukan setelah melakukan 

- pre processing -> image enhancement
- prosess awal dalam pengolahan citraproses pengolahan data citra asli menjadi citra lain yang sesuai dengan kebuuthan untuk mencapai tujuan tertentu.
- perbaikan kualtias citra.
- diperlukan akrean seringkali citra yang ddiajdikan bojek pembahasan mempunyai kualitas yang buruk / kurang baik.


Tujuan : mendapatkan citra  yang lebih mudah untuk diinterpreasikan oleh mata manusia.

Pada prosses ini ciri ciri teretnu yang terdapat di dalam citra lebih diperjelas kemunculannya atau disamarkan karena dapat menimbuklakn noise.

## Image Enhancement

Contoh citra yang blur/gambar yang buram. 
Citra yang membutuhkan pemrosesan. 
Citra yang terlalu gelap/terang,
citra yang kurang tajam.  
Citra yang kabur. ( **citra yang kabur** merujuk pada gambar atau foto yang kehilangan detail dan ketajaman, sehingga objek atau bagian-bagian dalam gambar terlihat tidak jelas atau samar-samar.)

Proses yang dilakukan sangat bergantung pad kebutuhan, dan pada keadaan citra.


JIka gambar sudah bagus tidak perlu processing, paling pre processing hanya perlu 1 tahap atau lebih tergantung citra yang diinignkan.

Lingkup pre processing:
Secaara matematis preprocessing dapat diartikan sebagia proses mengubah citra 


Contoh pre processing:
menghilagnkan noise
memperluas feature
memeprkecil / memperbesar ukura ndata (resize)
mengubah kecerahan gambar
poereganagn kontras
konversi ruang warna
	pelembutran citra (mengurangi noise)
penajaman citra
pengubahan geometrik


Jika proses lebih cepat dalam proses resize yang diambil adalah paling dikit. Karena makin kecil maka makin bagus. Tergantung hasilnya juga 


Komputer membaca nilai piksel, manusia melihat secara visual.




Resize dulu, karena untuk mengurangi jumlah piksel,  dan memudahkan dalam konversi warna dapat dilakukan lebih cepat karena jumlah piksel yang dikit.


Berikut penjelasan singkat tentang **binarisasi citra**, **cropping citra**, **resize citra**, dan **edge detection**:

---

1. **Binarisasi Citra**  
   - Mengubah gambar grayscale (hitam-putih) menjadi gambar biner (hanya dua nilai: hitam dan putih).  
   - Gunakan **thresholding** (ambang batas) untuk menentukan mana yang hitam (0) dan mana yang putih (1).  
   - Contoh: Pixel > 128 = putih, Pixel ≤ 128 = hitam.  

2. **Cropping Citra**  
   - Memotong bagian tertentu dari gambar untuk fokus pada area yang diinginkan.  
   - Contoh: Memotong wajah dari gambar yang berisi seluruh tubuh.  

3. **Resize Citra**  
   - Mengubah ukuran gambar (mengecilkan atau membesarkan) dengan menyesuaikan jumlah piksel.  
   - Contoh: Mengubah gambar 1000x1000 piksel menjadi 500x500 piksel.  

4. **Edge Detection**  
   - Mendeteksi tepi (garis batas) objek dalam gambar.  
   - Teknik populer: **Canny Edge Detection** atau **Sobel Operator**.  
   - Contoh: Menemukan tepi wajah, mobil, atau bangunan dalam gambar.  

---

**Intinya:**  
- **Binarisasi**: Hitam-putih.  
- **Cropping**: Potong gambar.  
- **Resize**: Ubah ukuran.  
- **Edge Detection**: Temukan tepi objek.  


## Image Brightness
Untuk membuat citra lebih terang atau lebih gelap.
Kecerahan gambar dapat diperbaiki dengan menambahkan aatau mengurangi sebuah konstanta pada setiap piksel di dalam citra.
Akibat dair opreasi ini histogram citra magalami pergesesran


Dalam histogram, tingkat kecerahan (brightness) umumnya bergerak dari **kiri ke kanan**:

- **Sisi kiri (low values):** Representasi bayangan (shadow), yaitu area yang lebih gelap.
- **Tengah (mid values):** Representasi nada menengah (midtones), yaitu area dengan pencahayaan sedang.
- **Sisi kanan (high values):** Representasi sorotan (highlights), yaitu area yang lebih terang.

Jadi, **jika suatu gambar semakin terang, puncak histogram akan bergeser ke kanan** karena lebih banyak piksel berada di rentang nilai yang lebih tinggi.



Secara matematis operasi ini ditulis sebagai berikut :
F(x,y)'=f(x,y)+b
jika b positif maka ....

jika b posiif maka...
histogram...??

Secara matematis, operasi **F(x,y)' = f(x,y) + b** menunjukkan bahwa setiap piksel dalam citra **f(x,y)** ditambah dengan suatu nilai **b**.

- Jika **b positif**, maka **setiap nilai piksel akan bertambah**.
- Dalam konteks histogram:
    - Histogram **akan bergeser ke kanan**, karena seluruh intensitas piksel meningkat.
    - Tidak ada perubahan bentuk histogram, hanya posisi nilainya yang berpindah ke level yang lebih tinggi.
    - Jika ada piksel yang sebelumnya berada di dekat maksimum (misalnya 250–255 pada citra 8-bit), beberapa bisa mengalami saturasi (clipping) jika melebihi batas 255.

Singkatnya, jika **b positif**, histogram gambar akan **bergeser ke kanan**, menunjukkan peningkatan kecerahan dalam citra.

**Algoritma Contrast Stretching** bertujuan untuk meningkatkan kontras gambar dengan merentangkan rentang intensitas piksel. Ini dilakukan dengan memetakan nilai piksel dari rentang aslinya ke rentang baru yang lebih luas, biasanya **0 hingga 255** (untuk gambar 8-bit).

### **Langkah-langkah singkat:**

1. **Cari nilai minimum dan maksimum** dalam gambar:
    - Imin⁡I_{\min} = nilai piksel terendah
    - Imax⁡I_{\max} = nilai piksel tertinggi
2. **Gunakan rumus transformasi linear:**
3. $$I′=(I−Imin⁡)×(Lmax⁡−Lmin⁡)Imax⁡−Imin⁡+Lmin⁡
4. 
5.  $$
6. $$
I' = \frac{(I - I_{\min}) \times (L_{\max} - L_{\min})}{I_{\max} - I_{\min}} + L_{\min}
6.
$$
    - **I** = nilai piksel asli
    - **I'** = nilai piksel baru
    - **Lmin & Lmax** = rentang baru (misalnya 0 dan 255)
7. **Terapkan transformasi ke seluruh piksel dalam gambar**.

### **Hasil:**

- Gambar memiliki **kontras lebih tinggi**.
- Histogram gambar tersebar lebih merata di seluruh rentang intensitas.



### **Image Smoothing dengan Low-Pass Filter**

**Image smoothing** menggunakan **low-pass filter (LPF)** bertujuan untuk mengurangi **noise** dan **detail tajam** dalam gambar dengan cara meratakan perubahan intensitas piksel.

### **Konsep Low-Pass Filter:**

- Menekan **frekuensi tinggi** (tepi, detail tajam, dan noise).
- Mempertahankan **frekuensi rendah** (area warna atau intensitas yang berubah perlahan).
- Menghasilkan efek **blur** atau perataan gambar.

---

### **Jenis Low-Pass Filter (LPF):**

1. **Mean Filter (Averaging Filter)**
    
    - Menghitung rata-rata intensitas piksel dalam jendela (kernel) tertentu.
    - Contoh kernel 3×3: 
    - $$\frac{1}{9} \begin{bmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \end{bmatrix}$$
    - Efek: Gambar lebih halus, tapi bisa kehilangan detail tepi.
2. **Gaussian Filter**
    
    - Mirip dengan mean filter, tetapi menggunakan bobot berdasarkan distribusi Gaussian.
    - Contoh kernel Gaussian 3×3: $$\frac{1}{16} \begin{bmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \\ 1 & 2 & 1 \end{bmatrix}$$
    - Efek: Blur lebih alami dibandingkan mean filter.
3. **Bilateral Filter**
    
    - Mempertahankan tepi sekaligus menghaluskan bagian lain dengan mempertimbangkan perbedaan intensitas antar piksel.

---

### **Aplikasi Low-Pass Filter dalam Image Processing:**

✅ **Mengurangi noise** dalam citra digital.  
✅ **Menghaluskan tekstur kasar** dalam gambar.  
✅ **Persiapan sebelum segmentasi** atau deteksi tepi untuk mengurangi gangguan kecil.

Low-pass filter sering digunakan dalam **pengolahan citra medis, pengenalan wajah, dan pengolahan video** untuk mengurangi noise atau membuat efek blur.