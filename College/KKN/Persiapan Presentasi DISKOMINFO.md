# Definition.

**Presentasi Permohonan Subdomain** adalah kegiatan penyampaian dokumen, paparan teknis, dan justifikasi kebutuhan kepada **Dinas Komunikasi dan Informatika (Diskominfo)** Kota Samarinda guna memperoleh **persetujuan penerbitan subdomain**
## Tujuan

Presentasi ini untuk mendapatkan persetujuan dari pihak Diskominfo mengenai "**Permohonan Subdomain Jalan Peduli**" dengan alamat dengan alamat **`https://jalan-peduli.pupr.samarindakota.go.id/`**.  Untuk itu, diperlukan koordinasi intensif dengan pihak Diskominfo.

## UAT | User Acceptance Test
| Area Uji             | Sub-fitur                                                | Kriteria Sukses                                           | Sukses? |
| -------------------- | -------------------------------------------------------- | --------------------------------------------------------- | ------- |
| **Akses Website**    | Akses ke halaman utama                                   | Halaman terbuka tanpa error (status 200 OK)               |         |
| **Pelaporan**        | Form upload laporan (foto + lokasi manual atau otomatis) | Data tersimpan, file JPG/PNG ≤ 5MB berhasil               |         |
| **Peta Lokasi**      | Tampilkan lokasi pelapor di peta                         | Lokasi muncul di peta (OpenStreetMap)                     |         |
| **Role Admin**       | Akses ke dashboard admin                                 | Admin bisa melihat dan kelola laporan                     |         |
| **Role Super Admin** | Kelola admin lain & akses semua fitur                    | Super Admin bisa tambah admin & kelola data               |         |
| **API Laporan**      | Mendapatkan informasi setiap laporan.                    | Dapat melihat informasi laporan yang dihasilkan dari API. |         |
| **Keamanan Dasar**   | Batasi ukuran file & input teks                          | Tidak ada crash/error dari input tidak valid              |         |
| **Performa Lokal**   | Cek waktu muat halaman utama                             | Halaman termuat ≤ 3 detik di localhost                    |         |



# 📍 Lokasi.

```
Hari / Tanggal : Jum’at, 18 Juli 2025 
Pukul : 13.30 – 15.00 WITA 
Tempat : Ruang Rapat Diskominfo Kota Samarinda 
Acara : User Acceptance Test (UAT) Permohonan Subdomain Permohonan Subdomain https://jalan-peduli.pupr.samarindakota.go.id
Google Maps : https://maps.app.goo.gl/gXxuEK1MRBhuEmwS7
```

# Tools.

> Berikut persiapan alat dan kebutuhan lainnya mengenai persiapan presentasi : 

- **Repository Github** [Klik Menuju Github](https://github.com/KKN-PUPR-51/jalanpeduli_prototype)
- 