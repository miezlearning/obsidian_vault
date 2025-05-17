Berikut ini adalah **tutorial lengkap cara upgrade dan downgrade Laravel** dengan aman, baik secara manual maupun menggunakan `composer`, disesuaikan untuk kasus umum (misalnya upgrade Laravel 8 ke 10 atau downgrade Laravel 10 ke 9):

---

## 🔁 1. Perbedaan Upgrade vs Downgrade Laravel

|Upgrade|Downgrade|
|---|---|
|Memperbarui ke versi Laravel yang lebih baru|Mengubah ke versi Laravel yang lebih lama|
|Biasanya perlu update kode dan dependency|Bisa gagal jika ada fitur baru yang tidak tersedia di versi lama|
|Tujuan: fitur baru, performa, dukungan|Tujuan: kompatibilitas lama, stabilitas|

---

## ✅ 2. Cek Versi Laravel Sekarang

Jalankan:

```bash
php artisan --version
```

---

## 📈 3. Cara Upgrade Laravel

Misalnya kamu ingin upgrade **dari Laravel 9 ke Laravel 10**:

### ✅ Langkah Upgrade:

1. **Backup dulu project kamu**
    
2. Ubah versi Laravel di `composer.json`:
    
    ```json
    "laravel/framework": "^10.0"
    ```
    
3. Hapus file dan folder berikut:
    

```bash
rm composer.lock
rm -rf vendor/
```

4. Jalankan:
    

```bash
composer update
```

5. Jalankan migration dan clear cache:
    

```bash
php artisan migrate
php artisan config:clear
php artisan route:clear
php artisan cache:clear
```

6. Buka project, pastikan tidak ada error.
    

> **Catatan**: Untuk major upgrade (Laravel 8 → 10), kamu perlu cek [Laravel Upgrade Guide](https://laravel.com/docs/10.x/upgrade) karena bisa ada breaking changes.

---

## 📉 4. Cara Downgrade Laravel

Misalnya kamu ingin downgrade dari Laravel 10 ke Laravel 9.

### ⚠️ Downgrade itu **lebih sulit** dari upgrade karena:

- Ada fitur yang **tidak tersedia** di versi lama
    
- Mungkin perlu **ubah kode program**
    

### ✅ Langkah Downgrade:

1. Ubah versi di `composer.json`, misalnya ke Laravel 9:
    
    ```json
    "laravel/framework": "^9.0"
    ```
    
2. Hapus lock dan vendor:
    

```bash
rm composer.lock
rm -rf vendor/
```

3. Jalankan ulang install dependency:
    

```bash
composer update
```

4. Cek apakah ada kode yang error (fitur Laravel 10 mungkin tidak tersedia di Laravel 9):
    
    - Misalnya: Route group `prefix:controller::class` → belum didukung Laravel 9
        
    - Pastikan `vite`, `sanctum`, dsb juga mendukung Laravel 9
        
5. Jalankan:
    

```bash
php artisan serve
```

---

## 📌 Tips Tambahan

| Tips                   | Penjelasan                                                               |
| ---------------------- | ------------------------------------------------------------------------ |
| Gunakan Git            | Biar bisa rollback kalau gagal                                           |
| Cek Laravel Docs       | Cek [upgrade guide](https://laravel.com/docs/10.x/upgrade) resmi Laravel |
| Gunakan `composer why` | Untuk tahu kenapa versi tertentu dipasang                                |
| Gunakan Laravel Shift  | Tools berbayar untuk upgrade otomatis                                    |
