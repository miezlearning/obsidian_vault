---
aliases:
  - "Persiapan Workshop 101 Github : ......"
---
# Teknis 
- Persiapan Instalasi
- Teori -> Praktek diawali dengan materi dasar hingga semi advance (30 Menit)
- Terdapat Ice Breaking Challenge (setelah 1:30 jam) hadiahnya beng-beng.
- Kelompok Challenge (diakhir)
- Materi basic usage.
- Kapasitas Maksimal 30 Orang
- Pembagian Kelompok 5 orang per kelompok
- posttest atau pekerjaan rumah soal dari kami setelah selesai kegiatan

# Outline Materi
- **Pengenalan Github**
	- Penjelasan Utama ( sedikit ada sejarah saja di mention )
	- Bedanya Git dan Github
	- Ekosistem Github : Pull Request, Organization, Repository, Push (disebut aja terus bilang nanti akan dijelaskan)
	- Contoh Repo Keren
		- Repo 1
		- Repo 2
- **Pengenalan Git** 
	- Penjelasan Utama 
		- flow dari git (ilustrasi dalam bentuk flowchart)
		- local
	- Kapan dipakai git?
	- materi tentang yang dibawah (*cari istilah)
		- Istilah Gampang (git add -> git commit -> git push)
	- konfigurasi awal
```bash 
git config --global user.name  "Nama Lengkap"
git config --global user.email "nama@email.com"
```
-  **Github Setup** 
	- Buat Akun
	- buat repo (penjelasan bedanya public dan private)
	- jelasin file konfigurasi :  .gitignore, README.md (mention beberapa aja yg penting cuman 2 itu seperti .env, env_example)
	- git init (inisiasi)
	- tips kalau bisa dapat pro menggunakan email kampus
- **Command Dasar/Basic**
	- git add
	- git status
	- git commit 
	- git log 
	- git clone
- **Branching**
		- git branch 
		- git branch "nama_branch"
		- git checkout "nama_branch"
		- git switch "nama_branch"
		- git merge 
- **Remoting Repo**
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
	- **Github Pages**
	