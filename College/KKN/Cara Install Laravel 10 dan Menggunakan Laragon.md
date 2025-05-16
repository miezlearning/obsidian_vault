Untuk mengunduh dan menginstal Laravel versi 10 menggunakan **Laragon** sebagai lingkungan pengembangan, berikut adalah langkah-langkah yang jelas dan singkat. Laragon adalah alternatif ringan untuk XAMPP yang mendukung PHP, Apache/Nginx, MySQL, dan Composer, serta cocok untuk pengembangan Laravel. Saya akan memastikan langkah-langkah ini sesuai dengan kebutuhan Anda, termasuk memperbaiki masalah sebelumnya terkait versi PHP.

### Persyaratan
- **Laragon** terinstal (versi terbaru disarankan).
- **PHP 8.1+** (Laravel 10 membutuhkan PHP 8.1 atau lebih tinggi).
- **Composer** terinstal.
- **Koneksi internet stabil**.

### Langkah-Langkah

#### 1. Instal dan Konfigurasi Laragon
   - **Unduh Laragon**:
     - Kunjungi [laragon.org](https://laragon.org/download/) dan unduh versi **Laragon Full** (termasuk PHP, Apache, MySQL, dll.).
     - Instal Laragon di lokasi default (misalnya, `C:\laragon`).
   - **Jalankan Laragon**:
     - Buka Laragon, dan pastikan Terminal, Apache/Nginx, dan MySQL berjalan (klik **Start All** di jendela Laragon).
   - **Perbarui PHP ke 8.1+**:
     - Laragon biasanya menyertakan PHP versi terbaru, tetapi jika versi PHP di Laragon masih di bawah 8.1:
       - Unduh PHP 8.1 atau 8.2 (Non-Thread Safe) dari [windows.php.net](https://windows.php.net/download/).
       - Ekstrak ke `C:\laragon\bin\php\php-8.1.x` (ganti `x` dengan nomor versi).
       - Di Laragon, klik **Menu > PHP > Version** dan pilih versi PHP baru.
     - Verifikasi versi PHP di Terminal Laragon:
       ```bash
       php -v
       ```
       Pastikan output menunjukkan PHP 8.1+ (misalnya, `PHP 8.1.10`).
   - **Pastikan Composer Terinstal**:
     - Laragon biasanya menyertakan Composer. Verifikasi dengan:
       ```bash
       composer --version
       ```
     - Jika tidak ada, unduh dan instal dari [getcomposer.org](https://getcomposer.org/).

#### 2. Buat Proyek Laravel 10
   - **Buka Terminal Laragon**:
     - Klik kanan di jendela Laragon, pilih **Terminal**, atau gunakan tombol **Terminal**.
     - Terminal akan terbuka di direktori root proyek Laragon (biasanya `C:\laragon\www`).
   - **Unduh Laravel 10**:
     Jalankan perintah berikut untuk membuat proyek Laravel baru:
     ```bash
     composer create-project laravel/laravel jalan-peduli "10.*"
     ```
     - `jalan-peduli` adalah nama folder proyek Anda (ganti sesuai keinginan).
     - `"10.*"` memastikan Anda menginstal versi 10 terbaru.
   - **Tunggu Proses Instalasi**:
     Composer akan mengunduh Laravel 10 dan dependensinya. Ini mungkin memakan waktu tergantung kecepatan internet.

#### 3. Konfigurasi Proyek Laravel
   - **Pindah ke Direktori Proyek**:
     ```bash
     cd jalan-peduli
     ```
   - **Salin File `.env`**:
     Salin file `.env.example` menjadi `.env`:
     ```bash
     cp .env.example .env
     ```
   - **Edit File `.env`**:
     Buka `C:\laragon\www\jalan-peduli\.env` dengan editor teks (misalnya, VS Code) dan sesuaikan pengaturan database:
     ```env
     DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=jalan_peduli
     DB_USERNAME=root
     DB_PASSWORD=
     ```
     - Laragon biasanya menggunakan `root` sebagai username MySQL dengan kata sandi kosong (`""`).
     - Ganti `jalan_peduli` dengan nama database yang akan dibuat.
   - **Buat Database**:
     - Buka **HeidiSQL** dari Laragon (klik **Database** di jendela Laragon).
     - Buat database baru bernama `jalan_peduli` (atau sesuai nama di `.env`).
   - **Generate Application Key**:
     Jalankan perintah berikut:
     ```bash
     php artisan key:generate
     ```
     Ini akan mengisi `APP_KEY` di file `.env`.

#### 4. Jalankan Proyek Laravel
   - **Akses Proyek di Browser**:
     - Laragon secara otomatis membuat virtual host untuk proyek di `C:\laragon\www`.
     - Buka browser dan kunjungi:
       ```
       http://jalan-peduli.test
       ```
       - Laragon menggunakan ekstensi `.test` untuk virtual host lokal.
       - Jika tidak bekerja, pastikan file `C:\Windows\System32\drivers\etc\hosts` memiliki entri seperti:
         ```
         127.0.0.1 jalan-peduli.test
         ```
     - Anda seharusnya melihat halaman selamat datang Laravel.
   - **Alternatif: Gunakan Server Pengembangan**:
     Jika virtual host bermasalah, jalankan server bawaan Laravel:
     ```bash
     php artisan serve
     ```
     Akses di `http://localhost:8000`.

#### 5. Verifikasi Instalasi
   - **Cek Versi Laravel**:
     Jalankan:
     ```bash
     php artisan --version
     ```
     Pastikan output menunjukkan `Laravel Framework 10.x.x`.
   - **Uji Database**:
     Jalankan migrasi untuk menguji koneksi database:
     ```bash
     php artisan migrate
     ```
     Jika berhasil, tabel default Laravel akan dibuat di database.

### Mengatasi Masalah Sebelumnya (PHP 8.0.30 dan Apache Error)
Berdasarkan percakapan sebelumnya, Anda mengalami masalah dengan PHP 8.0.30 dan Apache di XAMPP. Berikut adalah alasan mengapa Laragon lebih disarankan dan cara memastikan tidak ada masalah serupa:
- **PHP 8.1+ di Laragon**:
  - Laragon memudahkan pergantian versi PHP melalui menu. Pastikan Anda memilih PHP 8.1+ sebelum menginstal Laravel 10.
  - Jika PHP di Laragon masih 8.0, unduh PHP 8.1+ dan tambahkan ke `C:\laragon\bin\php`.
- **Apache/Nginx di Laragon**:
  - Laragon mendukung Apache dan Nginx, dan konfigurasinya lebih sederhana dibandingkan XAMPP.
  - Jika Anda mengalami error Apache seperti sebelumnya (port diblokir, SSL mismatch), periksa:
    - **Port 80/443**: Pastikan tidak ada aplikasi lain (misalnya, Skype, IIS) yang menggunakan port ini:
      ```bash
      netstat -aon | findstr :80
      ```
    - **SSL Warning**: Laragon tidak mengaktifkan SSL secara default untuk lokal, jadi Anda tidak akan melihat error seperti `www.example.com:443 certificate mismatch`.
- **Virtual Host Otomatis**:
  - Laragon secara otomatis membuat virtual host (misalnya, `jalan-peduli.test`), menghilangkan kebutuhan konfigurasi manual seperti di XAMPP.

### Catatan Tambahan
- **Ekstensi PHP**:
  Pastikan ekstensi yang dibutuhkan Laravel aktif di `C:\laragon\bin\php\php-8.1.x\php.ini`
```ini
  extension=gd
  extension=pdo_mysql
  extension=mbstring
  extension=openssl
  extension=fileinfo
```
- **Firewall**:
  Jika `jalan-peduli.test` tidak dapat diakses, pastikan firewall tidak memblokir port 80 atau Laragon.
- **Backup**:
  Jika Anda memiliki proyek lama di XAMPP (`C:\xampp\htdocs`), pindahkan ke `C:\laragon\www` untuk digunakan di Laragon.
- **Masalah Composer**:
  Jika Composer gagal saat instalasi, perbarui Composer:
  ```bash
  composer self-update
  ```
  Atau hapus cache Composer:
  ```bash
  composer clear-cache
  ```

### Jika Masalah Muncul
- **Error PHP Versi**: Jika Composer masih mendeteksi PHP 8.0, pastikan Laragon menggunakan PHP 8.1+ (cek di **Menu > PHP > Version**).
- **Apache/Nginx Gagal Start**: Periksa log di `C:\laragon\logs` atau jalankan `httpd -t` di Terminal Laragon untuk memeriksa sintaks konfigurasi.
- **Virtual Host Tidak Berfungsi**: Pastikan Laragon menambahkan entri di file `hosts` Windows. Jika tidak, tambahkan manual:
  ```
  127.0.0.1 jalan-peduli.test
  ```
- Bagikan pesan error spesifik jika Anda mengalami kendala, dan saya akan bantu lebih lanjut.

### Ringkasan
Dengan Laragon, Anda dapat menginstal Laravel 10 dengan mudah karena konfigurasi PHP, Composer, dan virtual host sudah diotomatisasi. Pastikan PHP 8.1+ digunakan, ikuti langkah-langkah di atas, dan proyek Anda akan berjalan di `http://jalan-peduli.test`. Jika Anda ingin tetap menggunakan XAMPP, beri tahu saya, dan saya akan bantu memperbaiki konfigurasi Apache/PHP di sana.

Selamat mencoba, dan beri tahu jika ada kendala!