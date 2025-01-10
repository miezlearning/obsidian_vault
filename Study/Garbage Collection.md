Garbage collection dalam ilmu komputer itu kayak pembersih otomatis buat memori. Jadi, ketika program nggak butuh data tertentu lagi, garbage collection bakal hapus itu data biar memori nggak penuh. Ini bikin aplikasi lebih lancar dan nggak ngelag. Simplenya, memori jadi rapi terus!

# Let's talk about, apa itu garbage collection..

Hai!, apakah kalian tahu apa itu *Garbage Collection atau GC?* ini adalah metode pembersihan memori yang dipakai saat membuat aplikasi dalam pemrograman.

**Garbage Collection**, sangat penting dalam dunia pemrograman karena ini bisa membuat kinerja memori kalian tetap stabil dan tidak terjadi *overload* maupun *memory leaks*. Karena jika tidak adanya GC ini, maka akan terjadi penurunan kinerja **Sistem Operasi** pada komputer kalian.

Contohnya, kita membuat sebuah program biodata seseorang menggunakan python:

### Menampilkan Data
```python
#Variabel ( variabel akan masuk kedalam memori nantinya ) 
nama = "Muhammad Yusuf Efendi" #Tipe Data : String
umur = 19 #Tipe Data : Integer

print("Biodata Yusuf Efendi")
print(20*"="') # Untuk membuat baris memanjang
print("Nama ", nama)
print("Umur ", umur)

```

### Output 
```js
Biodata Yusuf Efendi
============================
Nama : Muhammad Yusuf Efendi
Umur : 19
```

### Menghapus Isi Variabel
```python
#Variabel ( variabel akan masuk kedalam memori nantinya ) 
nama = "Muhammad Yusuf Efendi" #Tipe Data : String
umur = 19 #Tipe Data : Integer


#ini adalah bagian yang diubah, bisa dilihat perbedaan isi variabelnya
nama = None #maksud dari isi data ini adalah tidak ada atau kosong
umur = None

print("Biodata Yusuf Efendi")
print(20*"="') # Untuk membuat baris memanjang
print("Nama ", nama)
print("Umur ", umur)

```

Sehingga,

### Output 

```python
Biodata Yusuf Efendi
============================
Nama : None
Umur : None
```

## Penjelasan

Baik, saya jelaskan apa maksud dari menampilkan data dan menghapus isi variabel saat saya menambahkan isi dari variabel *nama* & *umur* otomatis akan masuk kedalam memori kalian.

Dan, setelah itu saya menghapus isi variabel menggunakan metode *Null/None* saat dikosongkan variabelnya sebenarnya jika tidak ada *Garbage Collection* data yang ada di variabel sebelumnya (*yang memiliki isi string dan integer*) itu masih tersimpan didalam memori. Tetapi saat dibersihkan menggunakan metode *Garbage Collection* itu akan menghilang dari memori.

# Kesimpulan

Metode Garbage Collection sangat bermanfaat bagi penyimpanan memori agar tetap terjaga kinerja sistem operasinya dan membuat lebih cepat dalam menjalankan program.