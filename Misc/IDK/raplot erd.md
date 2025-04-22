

1. **DOSEN**
    
    - `id_dosen` (Primary Key) - Contoh: D001
    - `nidn` (Unique) - Nomor Induk Dosen Nasional
    - `nama_lengkap`
    - `email_institusi` (Unique)
    - `jabatan_fungsional` (e.g., Asisten Ahli, Lektor, Guru Besar)
    - `tanggal_masuk`
    - `id_fakultas` (Foreign Key ke FAKULTAS)
    

    
2. **FAKULTAS**
    
    - `id_fakultas` (Primary Key) - Contoh: F01
    - `kode_fakultas` (Unique) - Contoh: FTIS
    - `nama_fakultas`
    - `dekan` (Nama Dekan, nullable)
    - `alamat_gedung`
    - `nomor_telepon` (nullable)
    

    
3. **PENELITIAN**
    
    - `id_penelitian` (Primary Key) - Contoh: R2024001
    - `judul`
    - `tahun_mulai`
    - `tahun_selesai` (nullable, jika masih berjalan)
    - `status` (e.g., Sedang Berjalan, Selesai, Ditolak)
    - `sumber_dana_utama` (Text, nama sumber dana utama)
    - `jumlah_dana` (nilai dana, nullable)
    

    
4. **PUBLIKASI**
    
    - `id_publikasi` (Primary Key) - Contoh: P2024001
    - `judul`
    - `tahun_publikasi`
    - `jenis_publikasi` (e.g., Jurnal, Prosiding, Buku, Paten)
    - `url_dokumen` (Link ke dokumen, nullable)
    - `nama_penerbit` (Nama Jurnal/Prosiding/Penerbit Buku)
    - `isbn_issn` (ISBN/ISSN, nullable)
    

    
5. **BIDANG_ILMU**
    
    - `id_bidang_ilmu` (Primary Key) - Contoh: BI001
    - `nama_bidang`
    - `deskripsi_singkat` (nullable)
    - `kode_bidang` (Unique)
    - `rumpun_ilmu` (e.g., Teknik, Sosial, Kesehatan)
    - `tahun_ditetapkan` (nullable)
    

    

**Entitas Lemah:**


1. **DOSEN_PENELITIAN**
    
    - `id_dosen` (Foreign Key ke DOSEN)
    - `id_penelitian` (Foreign Key ke PENELITIAN)
    - `peran` (e.g., Ketua, Anggota)
    - `kontribusi` (persentase atau deskripsi singkat, nullable)
    - `urutan_anggota` (jika perlu urutan spesifik dalam tim, nullable)
    - **Primary Key gabungan: (`id_dosen`, `id_penelitian`)**
    
2. **DOSEN_PUBLIKASI**
    
    - `id_dosen` (Foreign Key ke DOSEN)
    - `id_publikasi` (Foreign Key ke PUBLIKASI)
    - `urutan_penulis` (Nomor urut penulis, e.g., 1, 2, 3)
    - `is_corresponding_author` (Boolean/Ya/Tidak, nullable)
    - `afiliasi_saat_publikasi` (Nama afiliasi, jika berbeda, nullable)
    - **Primary Key gabungan: (`id_dosen`, `id_publikasi`)**
    

    

**Kardinalitasnya:**

1. **FAKULTAS** dan **DOSEN**: Satu FAKULTAS memiliki banyak DOSEN. Satu DOSEN bekerja di satu FAKULTAS.
    
    - Kardinalitas: 1 : Many (`FAKULTAS` 1 -- * `DOSEN`)
    - Implementasi: `id_fakultas` di `DOSEN` sebagai Foreign Key.
2. **DOSEN** dan **PENELITIAN**: Relasi Many-to-Many.
    
    - Kardinalitas: Many : Many (`DOSEN` * -- * `PENELITIAN`)
    - Implementasi: Melalui tabel penghubung **DOSEN_PENELITIAN**.
3. **DOSEN** dan **PUBLIKASI**: Relasi Many-to-Many.
    
    - Kardinalitas: Many : Many (`DOSEN` * -- * `PUBLIKASI`)
    - Implementasi: Melalui tabel penghubung **DOSEN_PUBLIKASI**.
4. **PENELITIAN** dan **BIDANG_ILMU**: Satu BIDANG_ILMU mencakup banyak PENELITIAN. Satu PENELITIAN _biasanya_ terkait dengan satu atau beberapa BIDANG_ILMU. Untuk simpel, kita buat Many PENELITIAN terkait ke satu BIDANG_ILMU (Bidang Utama).
    
    - Kardinalitas: Many : 1 (`PENELITIAN` * -- 1 `BIDANG_ILMU`)
    - Implementasi: `id_bidang_ilmu` di `PENELITIAN` sebagai Foreign Key. (Note: Jika satu penelitian bisa terkait banyak bidang, ini jadi Many-to-Many dan butuh tabel penghubung PENELITIAN_BIDANG_ILMU).

**Visualisasi:**



Catatan :

Bidang ilmu itu fokus dari seorang dosen, misal dia ini kan dosen sistem informasi, tapi fokusnya di bidang machine learning, atau pengolahan citra, atau keamanan siber.