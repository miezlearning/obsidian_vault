# CATATAN

---

Udah lumayan oke sih kerangkanya, tapi ada beberapa yg perlu dibenerin biar makin mantep 👍:

# 1. **Tanda + / - (Visibility):**

- Atribut (id_admin, nama, harga_parfum, dll) itu sebaiknya dibikin private (-) semua biar datanya aman (enkapsulasi).
    
- Terus method di Pelanggan kayak BuatPesanan, lihatKatalog itu kan aksi yg bisa dilakuin user, jadi harusnya public (+), bukan -. Sama juga buat method lain yg emang buat dipanggil dari luar kelas.
    

# 2.  **hitungSubtotal() di detailPesanan:**

- Method ini harusnya **balikin nilai** (return double), bukan void. Kan dia ngitung, jadi harus ada hasilnya dongg. Gimana cara dia dapet harga barangnya juga perlu dipikirin (perlu akses ke harga Parfum atau CustomParfum).
    

# 3.  **Relasi detailPesanan ke Parfum & CustomParfum:**

- Nah, ini yg agak tricky: relasi detailPesanan ke Parfum (1) dan ke CustomParfum (0..1). Kayaknya ga gitu deh . Masa 1 detail pesanan harus ada parfum biasa DAN boleh ada custom? Kan harusnya milih **salah satu** ya? 
    
- Saran: Bikin kelas baru misal Produk (abstrak), nanti Parfum & CustomParfum jadi 'anaknya' (inheritance). Terus detailPesanan cukup link ke Produk aja (1). Lebih rapi gitu. Atau ada cara lain, tapi intinya 1 detail itu buat 1 jenis produk (biasa ATAU custom).
    

# 4.  **Relasi CustomParfum ke detailPesanan:**

- Ini kebalik kayaknya. Dari CustomParfum ke detailPesanan masa 0..1? Berarti 1 parfum custom cuma bisa dipesen sekali doang dong?  Harusnya 0..* (satu custom parfum bisa dipesan berkali-kali / ada di banyak detail pesanan).
    

# 5.  **Tipe Data notes_parfum:**

- Di CustomParfum, tipe data notes_parfum kok double?  Notes kan biasanya teks deskripsi aroma (kayak "Top: Citrus, Middle: Floral"), jadi harusnya string yaa.
    

# 6. **Typo Kecil:**

- Di Pelanggan ada buatCutomParfum, harusnya buatCustomParfum.
    

---