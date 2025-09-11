---
aliases:
  - "Persiapan Workshop 101 Github : ......"
---
# Teknis 
- Persiapan Instalasi
- Teori -> Praktek diawali dengan materi dasar hingga semi advance (30 Menit)
- Terdapat Ice Breaking Challenge (setelah per materi yang disampaikan) hadiahnya beng-beng.
- Kelompok Challenge (diakhir)
- Materi basic usage.
- Kapasitas Maksimal 30 Orang
- Pembagian Kelompok 5 orang per kelompok
- posttest atau pekerjaan rumah soal dari kami setelah selesai kegiatan
- https://docs.google.com/document/d/1yItTeFhrqS30al1i4c2Psw_eAEvh2nltZnAteiu-FpQ/edit?usp=sharing

# Outline Materi
- **Pengenalan Github** ( Alif  & Ahmad )
	- Pengantar ( alif )
	- Bedanya Git dan Github (alif )
	- Sejarah Github (ahmad)
	- Ekosistem Github : Pull Request, Organization, Repository, Push (disebut aja terus bilang  nanti akan dijelaskan) (ahmad)
	- Contoh Repo Keren (ahmad)
		- Repo 1 https://github.com/farizdotid/DAFTAR-API-LOKAL-INDONESIA (ahmad)
		- Repo 2 https://github.com/miezlearning/cheat-ais (alif)
	- Penjelasan Utama (ahmad)
		- flow dari git (ilustrasi dalam bentuk flowchart) (ahmad)
		- Kenapa menggunakan git? (ahmad)
	- 4 area
		- Istilah Gampang (git add -> git commit -> git push) (ahmad)
	
-  **Github Setup** (alif)
	- Buat Akun
	- buat repo (penjelasan bedanya public dan private)
	- konfigurasi awal
```bash 
git config --global user.name  "Nama Lengkap"
git config --global user.email "nama@email.com"
```
	- jelasin file konfigurasi :  .gitignore, README.md (mention beberapa aja yg penting cuman 2 itu seperti .env, env_example)
	- git init (inisiasi)
	- tips kalau bisa dapat pro menggunakan email kampus
- **Command Dasar/Basic** (alif)
	- git add
	- git status
	- git commit 
     - Conventional Commmits
	- git log 
	- git clone
- **Branching** (ahmad & alif)
		- git branch 
		- git branch "nama_branch"
		- git checkout "nama_branch"
		- git switch "nama_branch"
		- git merge 
- **Remoting Repo** (ahmad & alif)
		- `git remote` 
		- `git remote -v`
		- `git remote add origin "https://github.com/username/repo.git"`
		- `git push  -u origin "nama_branch"` (tips kasi tau -u itu apa dan tinggal git push aja seterusnya kalau di branch yang sama)
		- `git pull`
		- `git fetch`
- **Kolaborasi**
	- Forking Repo 
	- Review 
	- Issues
- **Github Action** (Bonus)
	- **Github Pages**'
- **Github Markdown** (bonus)

Teknis Tambahan :

- Batasin 2 pertanyaan
- tanya jawab ada di setiap materi
- soal kelompok setelah tanya jawab selesai
- penyampaiaann materi, memang ada pembagian, tapi jika ingin masuk atau menambahakan materi juga tidak apa apa.
- github action alif (jika sempat)

# Soal

https://github.com/miezlearning/workshop-github-ai/tree/master


# Alur Acara :

1. Disclaimer : kalau pemateri adalah teman yang ingin berbagi ilmu.
2. Ke slide selanjutnya yaitu boleh menggunakan chat gpt selama proses pengerjaan.
3. Alif selanjutnya pertama melakukan perkenalan, kedua bang ahmad
4. Pengantar Sebelum Ke Materi Utama 
5.  Masuk Ke materi, sedikit pengantar lagi untuk git nantinya 
6. Dilanjutkan oleh bang ahmad menjelaskan materi lanjutan sejarah github 
7. Bang ahmad ke slide **sejarah**, menjelaskan secara singkat yang ada di timeline gambar, 
8. Bang ahmad sebelum lanjut ke slide repo keren, jelasin dulu **Ekosistem Github** disebutkan dan dijelaskan sedikit.
9. Saat menjelaskan repo keren pertama jelaskan seperti biasa, untuk yang kedua bang ahmad mention/sebut bang alif untuk menjelaskan lebih detail reponya.
10. Setelah alif selesai menjelaskan repo, alif kembalikan lagi materinya untuk dilanjutkan oleh bang ahmad
11. Bang ahmad, lanjut slide berikutnya, menjelaskan flow dari gambar yang ada dislide,
12. Slide github setup dilanjutkan oleh Alif, jelaskan dari poin 1-2, saat di poin 3 kembali ke git untuk menjelaskan apa itu git config, ketika di poin 4 jelaskan saja tidak perlu membuat filenya (README.md dan semacamnya), poin 5 jelaskan apa itu git init (tanyakan ke pesrta apa fungsi dari git init?), 
13. masih melanjutkan ke slide berikutnya menjelaskan 4 area git 
14. lanjut ke slide berikutnya tentang **command dasar**, disini lgsg balik ke desktop untuk mempersiapkan contoh studi kasus dipraktekkan.
15. buat sebuah folder workshop-ai, isi satu file aja index.html.
16. git add, terus jelasin git add itu apa aja argument nya `git add <argument>.
17. lanjut sampai commit, pas di commit pakai conventional commit, sebelum itu jelaskan dlu conventional commit, contohkan beberapa tipe `feat,fix,docs,` urutan tentang conventional commit :
    1. Apa itu Conventional Commit (singkat).
	2. Kenapa penting (manfaat untuk tim & otomatisasi).
	3. Format dasarnya.
	4. Jenis-jenis yang sering dipakai (**feat, fix, docs, style, refactor, test, chore**).
	5. Contoh nyata commit.
18. lanjut menjelaskan git log setelah melakukan commit di cek terlebih dahulu id commitnya.
19. selanjutnya untuk git push untuk git pull itu nantinya aja detailnya di bagian kolaborasi
20. selanjutnya, bahas slide **branching** bahas teori dulu,  saat ini pastikan google meet masih tersambung, teus bahas urutan :
    - Jelaskan dulu apa itu branching, 
    - Contoh penggunaan
    - Tunjukan slide visual akarnya
    - Praktekkan dengan menggunakan `git branch` untuk melihat branch apa saja yang tersedia di lokal repo  (asterisk / "*"  adalah simbol dimana diberada sekarang.)
    - setelah itu jelaskan cara membuat branch baru, dengan nama `fitur`
    - baru jelaskan cara pindah branch menggunakan `git checkout` (cara lama) `git switch` (cara baru)
    - terus cek kembali untuk cek branch berada dimana sekarang menggunakan `git branch`
    - untuk praktek cepat, gunakan `fitur/nama_mereka` nama branch
    - tambah folder baru "fitur" buat sebuah file "test.html", lakukan comman dasar (add - commit) jika ingin sampai local (karean belum sampai remote jadi tidak perlu sampai git push dulu, mungkin?)
    - setelah itu lakukan merge ke main branch
21. selanjutnya ke slide **Remoting Repo** proses pemindahan dari lokala ke remote(hosting), isi pembahasan:
	-  jadi pembahasan disini teori dulu : **Remote repository** adalah copyan project yang disimpan di server (misalnya GitHub/GitLab) agar bisa diakses bersama.
	- setelah itu bahas nih, karena ini masih lokal repo, dan sebelumnya udah lakukan init kita belum tau nih mau repo apa kita push atau pindahinnya ke server.
	- kenalkan command `git remote`, seperti cek dulu menggunakan `git remote -v` apakah ada yang terkonek antara local ke remotenya?
	- contohkan command dasar `git remote add origin <link_repo_github>`
		- `origin` → nama alias bawaan untuk remote (bisa diganti, tapi biasanya dipakai default).
		- `<link_repo_github>` → URL dari repo GitHub/GitLab yang kita buat.
	- setelah itu cek apakah reponya sudah terhubung atau belum menggunakan `git remote -v` kembali. 
	- jika sudah terkoneksi, akhirnya kita bisa proses push ke remote dari local. 
	- dengan command `git push -u <alias_remote> <nama_branch>`
	- jiak berhasil, silakan cek repo nya apakah berhasil.
	- materi selesai.
22. Selanjutnya ke slide **Kolaborasi**,
	- Mulai dengan teori dulu: _"Kolaborasi berarti kerja bareng dalam satu repository. Kalau sendirian kita bisa langsung push ke main, tapi kalau tim harus pakai aturan biar gak tabrakan."_
	- Jelaskan alur besar kolaborasi:
	    1. **Clone repository** → ambil repo dari GitHub ke lokal.
	        `git clone <link_repo>`
	    2. **Buat branch baru** → supaya kerja tiap orang terpisah.
	        `git checkout -b fitur/nama_kalian`
	    3. **Kerja & commit di branch masing-masing**
	        - edit file → `git add .` → `git commit -m "feat: tambah fitur abc"`.
	        `git push origin fitur/nama_kalian`
	    4. **Pull Request (PR) / Merge Request (MR)** → gabungkan branch ke `main` lewat GitHub.
	    5. **Merge ke main** → setelah PR diterima, branch masuk ke main.
	    6. **Update lokal** → setiap anggota tim jalankan:
	        `git pull origin main`
	- Tekankan manfaat branching dalam kolaborasi: bisa kerja bareng tanpa mengganggu `main`.
	- Tunjukkan slide visual (workflow: clone → branch → push → PR → merge → pull).
	- Praktek cepat:
	    - tiap peserta buat branch `fitur/nama_mereka`.
	    - buat file baru `halo.html`.
	    - lakukan add → commit → push.
	    - lalu tunjukkan di GitHub bagaimana muncul branch baru & cara bikin Pull Request.
## PENUTUP

KESEPKATAN, MAU ALIF ATAU AHMAD.
- **Wrap Up Singkat**
    
    - Ringkas kembali alur besar yang sudah dipelajari:
        
        - setup → command dasar → commit → branching → remote → kolaborasi.
            
    - Gunakan gaya santai:  
        _“Nah, itu tadi perjalanan kita dari repo kosong sampai bisa kolaborasi bareng di GitHub. Dari yang awalnya cuma `git init`, sampai akhirnya bisa bikin Pull Request.”_
        
- **Apresiasi Peserta**
    
    - _“Kalian keren banget bisa ngikutin step by step. Walaupun Git kadang bikin pusing di awal, tapi setelah dipahami enak banget buat kerja tim.”_
        
- **Pesan Santai + Motivasi**
    
    - _“Git itu bukan ilmu sekali belajar langsung jago, tapi butuh dipakai terus biar terbiasa. Anggap aja kayak nge-gym: kalau jarang latihan, ya ototnya kaku lagi. Jadi sering-sering commit biar otot Git kalian makin kuat..”_ 😆
        
- **Ajakan Interaktif**
    
    - Bisa tutup dengan challenge kecil:
        
        - _“Oke, sebelum kita akhiri, coba semua ketik di chat: `git commit -m "terimakasih"`.”_
            
    - Atau: bikin kuis dadakan 1–2 pertanyaan ringan, kasih hadiah kecil (misalnya stiker digital / template cheat sheet Git).
        
- **Closing Statement**
    
    - _“Ingat, tools seperti Git & GitHub ini akan jadi bekal penting buat kalian kalau masuk ke dunia kerja atau bahkan kolaborasi open source. Jadi teruslah latihan dan jangan takut salah.”_
    - Akhiri dengan ucapan terima kasih & foto bareng (kalau ada).
  
# NOTE ALUR : 
- Jika ingin menambahkan materi, langsung masuk ketika hening 2-3 detik.
- Atau ada isyarat dari temannya jika "ada tambahan kh?".
- Google meet bang ahmad untuk bagian kolaborasi (https://meet.google.com/vdm-ckir-psn)
- Alif menjelaskan, bang ahmad melakukan aktivitas ( 1 ngoding 1 jelaskan )




# ALUR MATERI VISUAL 
- Materi 0 : Apa itu Git & Github ? > Kenapa Git > Sejarah GitHub 
- Materi 1 : Daftar Akun -> Install git -> Buat repository -> Inisiasi local repo git 
- Materi 2 : Cek Status > Menambahkan File ke Stage > Commit File (Opsional: Conventional Commit)  > Log Commit 
- Materi 3 : Penggunaan Branching > Cek/Lihat Branch > Buat Branch > Pindah Branch > Modifikasi Branch (tambah/hapus/edit file).
- Materi 4 : Lihat/Cek Remote Yang Terhubung > Integrasi/Hubungkan Local ke Remote > Push Perubahan ke Server 
- Materi 5 : Salin Repository Utama > Clone Hasil Salin > Tambah Remote Repo Utama > Buat Branch Baru > Sinkron Perubahan Repo Utama dengan Lokal >Lakukan Perubahan & Commit > Push ke Repo Remote Clone > Buat Pull Request > Terima Pull Request & Merge.

# PERTANYAAN PER MATERI 
1. Materi 0 : 
	- Jika Git Itu Bandara, Maka Github itu apa? 
2. Materi 1 : 
	- Jika status areanya Untracked apakah bisa di commit? 
	- Setelah install git, dan membuat repo kosong di github, apa yang harus dilakukan selanjutnya? 
3. Materi 2 : 
	- Jika kita melakukan perubahan pada file index.html, dan style.css, lalu git menjalankan `git add index.html` dan kemudian melakukan commit, apa yang terjadi pada file `style.css` ?
	- Apa nama status area setelah melakukan commit? 
4. Materi 3 : 
	- Apa yang terjadi jika kita menjalankan git push, tetapi ada perubahan baru pada github yang tidak kita miliki di local? 
	- Bagaimana cara perubahan lokal kita, bisa muncul di repo github, perintah apa yang digunakan? 
5. Materi 4 : 
	- Saya punya tim, dan saya memberikan akses ke mereka, itu jenis kolaborasi apa?
	- **Guntur** tertarik dengan sebuah project open source, di github **Bang Alip** dengan nama repository **Cheat AIS**, guntur ingin memberikan kontribusi dengan memperbaiki typo di file `README.md.` Namun tidak memiliki akses langsung untuk mengubah isi repository tersebut, apa yang harus dilakukan **Guntur**?
