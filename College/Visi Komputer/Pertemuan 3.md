Tugas dilaksanakan secara online presentasinya, dalam bentuk codingan ada juga.
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

