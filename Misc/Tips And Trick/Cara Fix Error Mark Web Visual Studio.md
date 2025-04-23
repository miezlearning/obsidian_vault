

1. **Tutup Visual Studio:** Pastikan Visual Studio tertutup agar tidak ada proses yang mengunci file.
    
2. **Buka File Explorer:** Navigasikan ke folder proyek Anda di mana file Form1.resx, Form2.resx, dan Form3.resx berada. File-file ini biasanya ada di folder masing-masing form (misalnya, di dalam folder Form1, Form2, Form3 di dalam folder proyek Anda).
    
3. **Pilih File yang Terkena Dampak:**
    
    - Klik kanan pada Form1.resx.
        
    - Pilih **Properties**.
        
4. **Cari Opsi "Unblock":** Di jendela Properties, pada tab **General**, lihat di bagian paling bawah. Mungkin ada bagian berlabel "Security" dengan pesan seperti "This file came from another computer and might be blocked to help protect this computer."
    
    - Jika Anda melihat opsi seperti itu, **centang kotak "Unblock"** atau klik tombol **"Unblock"**.
        
5. **Klik Apply dan OK:** Klik **Apply** lalu **OK**.
    
6. **Ulangi untuk File Lain:** Ulangi langkah 3-5 untuk Form2.resx dan Form3.resx.
    
7. **Pertimbangkan File Terkait:** Meskipun error hanya menyebut .resx, kadang-kadang file .vb dan .Designer.vb yang terkait juga memiliki mark of the web dan bisa menyebabkan masalah lain. Jika error berlanjut setelah hanya .resx di-unblock, ulangi langkah 3-5 untuk Form1.vb, Form1.Designer.vb, Form2.vb, Form2.Designer.vb, Form3.vb, dan Form3.Designer.vb. Cara termudah adalah unblock file ZIP proyek sebelum mengekstraknya, atau unblock folder proyek setelah diekstrak (kadang opsi unblock muncul di properties folder utama).
    
8. **Buka Kembali Visual Studio dan Rebuild:** Buka kembali proyek Anda di Visual Studio. Pergi ke menu **Build** -> **Clean Solution**, lalu **Build** -> **Rebuild Solution**.
