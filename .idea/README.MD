# Cara Push ke GitHub dengan Identitas Lain
Panduan langkah-demi-langkah untuk menginisialisasi ulang repositori Git dan menggunakan identitas berbeda saat push ke GitHub.
## Langkah-Langkah
### 1. Hapus Folder Git Lama
Hapus semua histori commit dan identitas user sebelumnya:
``` bash
rm -rf .git
```
> **Catatan**: Di Windows, jika menggunakan Git Bash gunakan perintah di atas. Alternatifnya, Anda dapat menghapus folder `.git` secara manual melalui File Explorer.
>

### 2. Inisialisasi Ulang Git
Buat repositori Git baru dengan identitas yang diinginkan:
``` bash
git init
git config user.name "Nama Baru"
git config user.email "email_baru@example.com"

git add .
git commit -m "Initial commit"
```
### 3. Hubungkan ke Repositori GitHub Baru
Buat repositori baru di GitHub (tanpa README), lalu hubungkan:
``` bash
git remote add origin https://github.com/username/nama-repositori.git
git branch -M main
git push -u origin main
```
## Menghapus Token GitHub yang Tersimpan
Jika perlu menghapus token GitHub yang tersimpan di Git Credential Manager di Windows:
``` bash
cmdkey /delete:git:https://github.com
```
## Hasil Akhir
- Repositori akan memiliki hanya satu commit awal
- Identitas kontributor akan menggunakan nama dan email yang baru
- Histori commit lama akan dihapus sepenuhnya

**Penting**: Gunakan panduan ini dengan bijak dan sesuai dengan kebijakan kontribusi yang berlaku.
