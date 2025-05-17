## 🚀 Setup Proyek Laravel dengan Laravel Herd (Setelah Clone dari GitHub)


---

### ✅ Tahapan Lengkap

#### 1. Clone Repository

```bash
git clone <url-repo> jalanpeduli_prototype
cd jalanpeduli_prototype
```

#### 2. Install Dependensi PHP (Composer)

```bash
composer install
```

> Menghasilkan folder `vendor` dan file `autoload.php`.

#### 3. Install Dependensi Node.js (jika pakai Tailwind CSS)

```bash
npm install
npm run dev
```

#### 4. Konfigurasi File `.env`

```bash
cp .env.example .env
php artisan key:generate
```

Edit `.env` (contoh):

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nama_database
DB_USERNAME=root
DB_PASSWORD=
```

#### 5. Tambahkan Proyek ke Laravel Herd

- Buka aplikasi **Laravel Herd**
    
- Tambahkan folder proyek:  
    `C:\Users\<Username>\Herd\jalanpeduli_prototype`
    
- Herd otomatis menjalankan server dan memberi domain `.test`, contoh:  
    `http://jalanpeduli-prototype.test`
    

#### 6. Jalankan Migrasi Database

```bash
php artisan migrate
php artisan db:seed   # (opsional, jika tersedia)
```

#### 7. Periksa File `index.php`

Pastikan baris berikut di `public/index.php` tidak error:

```php
require __DIR__.'/../vendor/autoload.php';
```

Jika `vendor` belum ada, ulangi langkah `composer install`.

---

### ❗ Penyebab Error Umum

|Masalah|Solusi|
|---|---|
|`vendor/autoload.php` not found|Jalankan `composer install`|
|Composer belum terinstal|Cek dengan `composer --version` atau gunakan `herd composer`|
|File `composer.json` bermasalah|Hapus `composer.lock`, lalu jalankan ulang `composer install`|

```bash
rm composer.lock
composer install
```

---

### 🎨 Khusus Tailwind CSS

- Konfigurasi `tailwind.config.js` dan `resources/css/app.css`
    
- Pastikan pemanggilan di Blade:
    

```blade
@vite(['resources/css/app.css', 'resources/js/app.js'])
```

---

### 📝 Catatan Tambahan

- **Laravel Herd** menggantikan `php artisan serve`, jadi cukup akses domain `.test`.
    
- Jika browser menandai situs sebagai "Not Secure", itu karena SSL lokal tidak aktif — aman untuk development.
    
- Cek error lebih lanjut di:
    
    ```
    storage/logs/laravel.log
    ```
    

---

### ✅ Langkah Terakhir

Buka browser dan akses:

```
http://jalanpeduli-prototype.test
```

Jika masih error, cek kembali log atau hubungi tim.

---

Jika kamu butuh versi **Markdown** atau ingin aku bantu export jadi PDF untuk dokumentasi tim, tinggal bilang!