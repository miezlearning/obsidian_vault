# Tahapan Proses Pengolahan Citra dan Visi Komputer
Data inputa ataupun pengolahan cita adalah sama, datanya video, disajikan searaa cepat dalam tiap detiknya.

Dapat berupa digital dan analog, mengapa cita menjadi salah satu objeek atau data input yang sering digunakan belakangan ini, karena citra itu dapa dimuat beberapa informasi.

Kata kata panjang bisa secara singkat atau dalam satu citra, atau dalam kegiatan klien seperti foto orang,  tersedia dalam suatu citra

- Citra Diam, 
- - Citra Bergerak, 
- - Citra Digital, 
- Pengolahan Citra

proses yang menerima data input berupa citra dan inputnya berupa citra juga.

Tahapan pengolahan citra sehinga computer vision, 

Dalam blok diagram sampai segmentation, proses ekstrak pada reprsentation nilai parameter pada suatu angka,  

Segmentation berupa citra biner data dimana objek adalah backgroudnyna, citra linier.

Struktur atau bentuk tepi dalam citra, topologi

Memotret objek output dari aimage acquitition, 

Setiap melakukan tahapan 


Apakah semua proses harus dilakuakn? ga harus, sesuaikan dengan problem domainnya.

Image restoration perlu dilakukan?  


Image Enhancement

Jika kamera cukup jauh objek mangga tidak akan dominan relatif kecil, perlu namanya segmentasi untuk megurangi area background karena yang diproses adalah fkosuyna di area mangga.

Kamera dan objek dekat, sehingga batas pinggir mangganya di tepi citranya tidak perlu segmentasi.

Jika citra didalam area batiknya tidak perlu segmentasi.

Represantion, gimana komputernya ini memberikan output kalau buah ini matang atau ga, bagaiman caranya? tentu saja ekstrak, bisa diliat dari tekstur buah warna. 


Teknik pengambilan gambar kurang sesuai maka model tersebut perlu melakukan namanya pengolahan citra seperti perbaikan kualitas citra, atau membuat area backgroudn  terlalu dominan.

Pengolahan citra belum tentu memperbagus kualitas bisa juga dilakukan ada tulisan, bisa diolah menjadi lebih samar atau kabur. dengan referensi menggunakan piksel.

Elemen dalam citra adalah piksel, kotak kotak.

Misal :
A

Menonjolkan ciri ciri utama pada citra.



Opreasi operasi yang uumnya ditreapkan pada pengolahan Citra : 




Contoh penerapan citra

- Increasing Brightness
- Bluring
- Enhancement
- Sharpness


Bidang studi yang berkaitan:

- Iamge Processing
- Pattern Recognition
- ARtifical Intelligent

Yang dibutuhkan pada pengolahan citra digital:
- Unsur unsur warna
- Sedikit matematika
- logika 
- komputer


Akuisisi Citra
proses untuk menghasilkan citra atau mengadakan suatu citra dimana keunggunlan citra digunakan untuk membuat atau membentuk dataset.

Peralatan Akuisisi Citra:
- Kamera
- Ponsel
- Printer/Foto Kopi  
- CT scan
- Laptop
- xray
- cctv


Scene element -> imgaing system -> internal 

![[Pasted image 20250210131001.png]]

Representasi citra hitam putih
Representasi citra 
Represntasi gray scale


Sampling dan Quantization
Sampling adalah proses mapping fungsi kontinyu ke diskrit
Quantiziotin


Ukuran spatial (hasil sampling) resolusi
Color depth  (hasil quztization) warna piksel

Representasi matriks



Bisa pakai rata rata atau bobot channel lama, umumnya untuk megnubah citra warna pake rata rata

Matriks warna itu seperti matriks 2d, jika punya 2 atau 3 warna itu 3 dimensi setiap layer beda beda di rate angkanya 99, bisa aja di grid nya bukan 99 tapi 0, bisa aja nilainya 200

jenis jensi warna pada komputer Default rgb, cmyk, lab, 

digitalisasi, terdaapat ukuran tertentu jika tambah zoom maksimal awalnya halus akan menjadi kotak kotak atau piksel atau terlihat pecah.


Same piexl size, different size
Piksel sama, ukurannya beda.

Ukuran sama, piksel beda 

quantization  😀proses kuantiasi membagi skala keabuan (0,L) menjadi G buah level ynag dinyakan dengan suatu harga bilangan bulat (integer), G diambil perpangkatan dari 2
G = 2m
dimana, G = derajat keabuan

skala keabuan 
2'1 (2 nilai)
2'2 (4nilai)
2'3(16 nilai)

rentang nilai kauabuan:
0,1
0 sampai 4