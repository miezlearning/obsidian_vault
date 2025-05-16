
1. **app/ Direktori**
    
    - Ini adalah jantung dari aplikasi Anda. Hampir semua logika inti aplikasi Anda akan berada di sini.
        
    - **Console/**: Berisi perintah Artisan kustom yang Anda buat. Kernel.php di sini adalah tempat Anda mendaftarkan perintah kustom dan menjadwalkan tugas (cron jobs).
        
    - **Exceptions/**: Berisi Handler.php, kelas yang menangani semua pengecualian (exceptions) yang dilempar oleh aplikasi Anda. Anda bisa menyesuaikan bagaimana pengecualian dicatat atau ditampilkan kepada pengguna.
        
    - **Http/**: Berisi Controllers, Middleware, dan Form Requests.
        
        - **Controllers/**: Bertanggung jawab untuk menangani permintaan HTTP yang masuk, mengambil data (biasanya melalui Models), dan mengirimkan respons (biasanya melalui Views).
            
        - **Middleware/**: Menyediakan mekanisme untuk memfilter permintaan HTTP yang masuk ke aplikasi Anda. Misalnya, middleware untuk otentikasi, CSRF protection, dll.
            
    - **Models/**: (Secara default, model diletakkan langsung di app/, tapi banyak pengembang membuat direktori Models/ untuk organisasi). Berisi kelas-kelas Model Eloquent Anda, yang mewakili tabel database dan menyediakan cara mudah untuk berinteraksi dengan data tersebut.
        
    - **Providers/**: Berisi semua Service Provider untuk aplikasi Anda. Service provider adalah pusat dari bootstrapping semua komponen Laravel, seperti mendaftarkan service container bindings, event listeners, middleware, dan bahkan rute.
        
2. **bootstrap/ Direktori**
    
    - Berisi file app.php yang mem-bootstrap framework.
        
    - Juga berisi direktori cache/ yang menyimpan file yang di-generate framework untuk optimasi performa, seperti file cache konfigurasi dan rute.
        
3. **config/ Direktori**
    
    - Berisi semua file konfigurasi aplikasi Anda, seperti app.php (konfigurasi umum), database.php (koneksi database), mail.php (konfigurasi email), services.php (konfigurasi layanan pihak ketiga), dll. Nilai-nilai dalam file ini seringkali mengambil dari file .env.
        
4. **database/ Direktori**
    
    - Berisi migrasi database, model factories, dan seeders.
        
    - **factories/**: Digunakan untuk menghasilkan data dummy untuk testing atau seeding database.
        
    - **migrations/**: Memungkinkan Anda mendefinisikan skema database Anda dalam kode PHP dan menjaga versi skema database Anda.
        
    - **seeders/**: Digunakan untuk mengisi database Anda dengan data awal atau data uji.
        
5. **node_modules/ Direktori**
    
    - Direktori ini muncul setelah Anda menjalankan npm install atau yarn install. Berisi semua dependensi JavaScript/Node.js yang dibutuhkan oleh proyek Anda (misalnya, untuk Laravel Mix atau Vite). Direktori ini biasanya tidak dimasukkan ke dalam version control (Git).
        
6. **public/ Direktori**
    
    - Ini adalah document root untuk aplikasi Anda. Semua permintaan masuk melalui direktori ini.
        
    - **index.php**: File entri utama yang menangani semua permintaan ke aplikasi Anda.
        
    - **assets/** (atau **build/assets/** seperti di gambar Anda, jika menggunakan Vite): Direktori tempat aset yang telah dikompilasi (seperti CSS dan JavaScript) disimpan oleh Laravel Mix atau Vite.
        
    - **.htaccess**: File konfigurasi untuk server Apache (jika Anda menggunakannya) untuk mengarahkan semua permintaan ke index.php.
        
    - **favicon.ico**: Ikon situs Anda.
        
    - **robots.txt**: Memberi instruksi kepada web crawler.
        
    - **manifest.json** (dalam public/build/): File manifest yang dihasilkan oleh Vite, memetakan nama aset asli ke versi hashnya untuk cache-busting.
        
7. **resources/ Direktori**
    
    - Berisi aset mentah (uncompiled) dan views Anda.
        
    - **css/** (atau **sass/**, **less/**): Berisi file CSS mentah, Sass, atau Less Anda sebelum dikompilasi.
        
    - **js/**: Berisi file JavaScript mentah Anda sebelum dikompilasi. Di sini juga biasanya ada app.js dan bootstrap.js.
        
    - **lang/**: Berisi file bahasa untuk lokalisasi aplikasi Anda.
        
    - **views/**: Berisi template Blade Anda. welcome.blade.php (seperti di gambar) adalah halaman selamat datang default Laravel.
        
8. **routes/ Direktori**
    
    - Berisi semua definisi rute untuk aplikasi Anda.
        
    - **web.php**: Rute untuk antarmuka web Anda. Rute ini memiliki state (session, cookies) dan proteksi CSRF.
        
    - **api.php**: Rute untuk API Anda. Rute ini stateless dan biasanya menggunakan token untuk otentikasi. Middleware api diterapkan secara otomatis.
        
    - **channels.php**: Tempat Anda mendaftarkan semua event broadcasting channel yang didukung aplikasi Anda.
        
    - **console.php**: Tempat Anda mendefinisikan perintah Artisan berbasis closure.
        
9. **storage/ Direktori**
    
    - Berisi Blade template yang telah dikompilasi, sesi berbasis file, cache file, dan file lain yang dihasilkan oleh framework.
        
    - **app/**: Digunakan untuk menyimpan file yang diunggah oleh pengguna atau dihasilkan oleh aplikasi.
        
        - **app/public/**: File di sini bisa dibuat dapat diakses publik dengan menjalankan php artisan storage:link.
            
    - **framework/**: Berisi file dan cache yang dihasilkan framework (sessions, views yang dikompilasi, cache).
        
    - **logs/**: Berisi file log aplikasi Anda (laravel.log).
        
10. **tests/ Direktori**
    
    - Berisi tes otomatis Anda.
        
    - **Feature/**: Tes yang menguji fungsionalitas aplikasi secara lebih luas, seperti bagaimana beberapa objek berinteraksi atau bahkan permintaan HTTP penuh.
        
    - **Unit/**: Tes yang menguji bagian yang sangat kecil dan terisolasi dari kode Anda (misalnya, satu metode dalam sebuah kelas).
        
    - TestCase.php adalah kelas dasar untuk semua tes.
        
11. **vendor/ Direktori**
    
    - Berisi semua dependensi Composer (paket PHP) yang dibutuhkan aplikasi Anda, termasuk Laravel framework itu sendiri. Direktori ini dikelola oleh Composer dan Anda tidak boleh mengubah file di dalamnya secara langsung.
        
12. **File di Root Direktori Proyek:**
    
    - **.editorconfig**: Membantu menjaga gaya koding yang konsisten untuk beberapa editor dan IDE.
        
    - **.env**: File konfigurasi lingkungan (environment). Berisi variabel spesifik untuk lingkungan tempat aplikasi berjalan (misalnya, kredensial database, kunci API). **File ini tidak boleh dimasukkan ke version control.**
        
    - **.env.example**: File contoh untuk .env. Salin file ini menjadi .env dan sesuaikan nilainya.
        
    - **.gitattributes**: File konfigurasi Git.
        
    - **.gitignore**: Menentukan file dan direktori mana yang harus diabaikan oleh Git.
        
    - **artisan**: Command-line interface (CLI) yang disertakan dengan Laravel. Menyediakan banyak perintah berguna untuk pengembangan.
        
    - **composer.json**: Mendefinisikan dependensi PHP proyek Anda untuk Composer.
        
    - **composer.lock**: Mencatat versi pasti dari setiap paket yang diinstal.
        
    - **package.json**: Mendefinisikan dependensi JavaScript proyek Anda untuk npm atau yarn.
        
    - **phpunit.xml**: File konfigurasi untuk PHPUnit (framework testing).
        
    - **vite.config.js** (atau **webpack.mix.js** pada Laravel versi lama): File konfigurasi untuk Vite (atau Laravel Mix) yang digunakan untuk mengkompilasi aset front-end (CSS, JS).
        

