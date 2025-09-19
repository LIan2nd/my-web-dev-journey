# Section 18: Git and Github

---

Git and Github, yaps, section yang mendasari journaling ini dibuat. Ntah kenapa, langsung kepikiran aja untuk journaling di sini, ketika mempelajari section ini.

---
<!-- jelasin apa itu git dan github di sini -->
## Git
Git adalah sistem kontrol. Anggap saja Git seperti "mesin waktu" untuk sebuah project. Git berjalan di local dan berfungsi untuk melacak setiap perubahan yang terjadi pada file-file dari waktu ke waktu.

## Github
GitHub adalah platform hosting berbasis web untuk proyek-proyek yang menggunakan Git. Jadi, setelah menggunakan Git untuk melacak perubahan di local, Kita bisa "mengambil" (pull) atau "menyimpan" (push) seluruh riwayat proyek local ke github.

---
<!-- jelasin juga soal syntax-syntax(?) nya, e.g. git add, git commit, git push, git remote, git branch, git checkout, dll -->
Di Section ini, ga terlalu yang gimana banget, karena command-command dari git versi CLI pun, dasarnya sudah "di luar" kepala☕ Jadi terdapat command dasar dari git untuk staging(?), commit, remote ke repository di github, dan push code Kita ke Github.

Untuk command dasarnya itu seperti berikut
```bash
git init
git add [nama file/bisa menggunakan . (titik) untuk add semua file yang baru/berubah ke staging] 
git commit -m "pesan commitnya"
```
Lalu jika ingin menghubungkan project local Kita ke repository (remote) di Github atau Gitlab, bisa dengan 

##### Inisialisasi Git di folder lokal
```bash
git init
```
##### Tambahkan file ke *staging area*
Menambahkan semua file ke *staging* :
```bash
git add .
```
Atau jika hanya file tertentu : 
```bash
git add nama_file.html
```
##### Buat commit pertama
```bash
git commit -m "Initial Commit"
```
##### Ubah branch master menjadi main (boleh ganti jadi yang lain juga xD)
Ubah menjadi main
```bash
git branch -M main
```
Ubah jadi superman
```bash
git branch -M superman
```
jangan, yaaa.
##### Hubungkan ke repository remote
biasanya dari Github, url terlihat `https://github.com/username/repo-name.git`
Perintahnya : 
```bash
git remote add origin <URL_REPO>
```
**Fun Fact, baru tau ternyata "origin" adalah nama dari remote nya itu.* Jadi *basicaly* Kita bisa ganti origin itu dengan nama yang Kita inginkan.
Contoh lengkap remote : 
```bash
git remote add origin https://github.com/LIan2nd/my-web-dev-journey.git
```
Cek apakah sudah terhubung : 
```bash
git remote -v
```
##### Push commit pertama ke branch utama (main)
```bash
git push -u origin main
```
After nambahin upstream(?) dengan *flag* u, Kita bisa push hanya dengan mengetikkan perintah `git push` saja.

##### Alur Lengkap
Jika dari awal project belum di-track oleh Git:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/LIan2nd/my-web-dev-journey.git
git push -u origin main
```

Adapun untuk *Commit Guide*, Aku sudah tanyakan ke gemini untukku di masa depan, bisa dilihat [di sini](./COMMIT_GUIDE.md)