# Bu Novianti
![![College/Tugas Akhir/Prototype Skripsi/Tahap Pendadaran/#*Table]]
## POIN SELESAI BU NOVIANTI
POIN 1
BEFORE
![[Pasted image 20260627183331.png]]

POIN 1 
AFTER
![[{B4066142-C52C-4308-A6AC-D3019FFFFC0F}.png]]
POIN 2 
BEFORE
![[Pasted image 20260627143236.png]]
POIN 2
AFTER
![[{257BFEB2-B812-4C31-A174-FF3FEC1B6EE7}.png|697]]

POIN 3
BEFORE
![[Pasted image 20260627144653.png|424]]


AFTER
![[{16D6A9F1-0826-4E2E-84F3-B710B253C193}.png|525]]

POIN 4 
BEFORE
![[Pasted image 20260627144840.png|395]]

AFTER
![[{D7FC566C-B953-423E-B958-311296FCA3D1}.png]]


POIN 6 
BEFORE
Berdasarkan Tabel 4.2, custom classifier head yang ditambahkan terdiri atas lapisan GlobalAveragePooling2D untuk meratakan peta fitur dari blok konvolusi terakhir VGG19, dilanjutkan dengan lapisan Dense(512) dengan regularisasi L2 dan fungsi aktivasi ReLU, Dropout(0,5), lapisan Dense(256) dengan regularisasi L2  dan fungsi aktivasi ReLU, Dropout(0,3), serta lapisan output Dense(9) dengan fungsi aktivasi Softmax yang menghasilkan distribusi probabilitas terhadap sembilan kelas kerusakan jalan. Total keseluruhan parameter model adalah 20.420.681, di mana pada tahap Feature Extraction hanya 396.297 parameter (1,94% dari total) yang bersifat trainable, sedangkan 20.024.384 parameter milik VGG19 bersifat non-trainable


POIN 6
AFTER
Berdasarkan Tabel 4.2 menyajikan ringkasan arsitektur model VGG19 _transfer learning_ yang digunakan dalam penelitian ini. Kolom _No_ menunjukkan urutan lapisan, kolom _Layer_ menunjukkan nama lapisan, kolom _Tipe_ menunjukkan jenis lapisan, kolom _Output Shape_ menunjukkan dimensi keluaran, dan kolom _Parameter_ menunjukkan jumlah bobot serta bias pada setiap lapisan. Berdasarkan tabel tersebut _custom classifier head_ terdiri atas lapisan GlobalAveragePooling2D, Dense(512), Dropout(0,5), Dense(256), Dropout(0,3), dan Dense(9) dengan fungsi aktivasi _Softmax_. Lapisan-lapisan ini disusun untuk menyesuaikan fitur hasil ekstraksi VGG19 dengan sembilan kelas target penelitian. Total parameter model berjumlah 20.420.681, dengan 396.297 parameter bersifat _trainable_ pada tahap _feature extraction_, sedangkan 20.024.384 parameter lainnya dibekukan sebagai bagian dari _base_ model VGG19.



POIN 7 
BEFORE

Kompleksitas tugas klasifikasi 9 kelas secara simultan dengan dataset lokal berskala terbatas (1.731 citra) dan distribusi yang sangat tidak seimbang (rasio kelas terbanyak : terkecil = 524 : 24 = 21,8:1) menjadi faktor utama yang memengaruhi performa model. Semakin banyak jumlah kelas dan semakin ekstrem ketidakseimbangan data, semakin sulit model mencapai akurasi tinggi secara merata pada semua kelas. Dengan mempertimbangkan kompleksitas tersebut, akurasi 66,54% dengan _macro-average F1-score_ 0,5970 merupakan hasil awal yang layak sebagai _proof-of-concept_ penerapan VGG19 pada kondisi lokal Kota Samarinda. Untuk konteks operasional, model ini lebih tepat difungsikan sebagai alat bantu pra-seleksi (_decision support_) yang membantu petugas memprioritaskan pemeriksaan khususnya pada laporan dengan confidence score tinggi, daripada sebagai validator tunggal yang otonom.

POIN 7
AFTER
Kompleksitas tugas klasifikasi 9 kelas secara simultan dengan dataset lokal berskala terbatas (1.731 citra) dan distribusi yang sangat tidak seimbang (rasio kelas terbanyak : terkecil = 524 : 24 = 21,8:1) menjadi faktor utama yang memengaruhi performa model. Semakin banyak jumlah kelas dan semakin ekstrem ketidakseimbangan data, semakin sulit model mencapai akurasi tinggi secara merata pada semua kelas. Dengan mempertimbangkan kompleksitas tersebut, akurasi 66,54% dengan _macro-average F1-score_ 0,5970 merupakan hasil awal yang layak sebagai _proof-of-concept_ penerapan VGG19 pada kondisi lokal Kota Samarinda. Untuk konteks operasional, model ini lebih tepat difungsikan sebagai alat bantu pra-seleksi (_decision support_) yang membantu petugas memprioritaskan pemeriksaan khususnya pada laporan dengan confidence score tinggi, daripada sebagai validator tunggal yang otonom.

POIN 5
BEFORE
![[{8BD9DC1B-EAB9-4D31-89DE-86099623C226}.png]]

POIN 8 
BEFORE
Tidak ada.

POIN 8
AFTER
![[{73191E45-0744-476D-BE24-1EB8B1BF6510}.png]]


POIN 9 
BEFORE
![[{36540A3D-5948-4A87-B2D2-FEB04F6114EC}.png]]

POIN 9
AFTER
![[Pasted image 20260701205618.png|697]]
# Bu Joan Angelina
![![College/Tugas Akhir/Prototype Skripsi/Tahap Pendadaran/#*Table1]]
## POIN SELESAI BU JOAN 

Poin 1 
BEFORE
![[{CA13CC42-A5FC-418A-A267-D4F5405C3DDE} 1.png]]

Poin 1
AFTER
![[{A1E0536E-3C41-467B-9B04-2115F25BEF9D}.png]]

POIN 10
BEFORE
![[{F2345AA7-16B9-48FB-8161-A1ACCD6C7CF1}.png]]

POIN 10
AFTER
![[Pasted image 20260701201706.png]]
Poin 5
BEFORE
![[{130A213B-7F5D-4B42-956E-753574D2CAF0}.png]]


POIN 5
AFTER
![[{20DD27ED-7358-443E-8120-CE26CDDF2124}.png]]

POIN 11
BEFORE
![[{4CB1FA12-A627-49B1-9DE5-CF6FFC0D046B}.png]]

POIN 11
AFTER
![[Studi Literatur Pengkajian Penelitian.jpg]]
# Prof Anindita
![![College/Tugas Akhir/Prototype Skripsi/Tahap Pendadaran/#*Table3]]

# Pak Reza

![![College/Tugas Akhir/Prototype Skripsi/Tahap Pendadaran/#*Table2]]
# Poin Selesai Pak Reza

POIN 1 
BEFORE
![[{22C3B3C6-F651-46FB-A016-A65F05DEC8B6}.png]]

POIN 1
AFTER
![[{69B9F26D-283D-4F9A-8C9E-8ECF95C3E4DE}.png]]



# Pembahasan Tambahan

1. Jika analisa komparatif pada skema membuktikan ada penambahan akurasi ini perlu dibahas apa alasannya, dan juga kenapa masih ada indikasi hasil akurasi yg jelek  seperti tentang keterbatasan data, distribusi data yang tidak balance masing-masing kelas, visual yang mirip antar tingkat pada jenis

# Note

- Jalankan 2 program skema 1 dan 2
> Skema 1 : Pembagian Data 70:15:15, Epoch 100
> Skema 2 : Pembagian Data 80:10:10, Epoch 100
> GPU : T4 