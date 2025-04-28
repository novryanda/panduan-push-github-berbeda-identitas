# 🚀 Panduan Push ke GitHub dengan Identitas Berbeda

[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/)

Panduan lengkap untuk menginisialisasi ulang repositori Git dan menggunakan identitas berbeda saat push ke GitHub.

## 📋 Daftar Isi

- [Pengantar](#pengantar)
- [Langkah-Langkah](#langkah-langkah)
- [Mengatasi Masalah Umum](#mengatasi-masalah-umum)
- [Catatan Penting](#catatan-penting)

## Pengantar

Panduan ini membantu Anda mengatur ulang repositori Git lokal untuk menggunakan identitas kontributor yang berbeda. Berguna untuk situasi seperti:

- Menggunakan akun GitHub yang berbeda untuk proyek tertentu
- Memisahkan identitas personal dan profesional
- Memulai dengan histori commit yang bersih

## Langkah-Langkah

### 1. Hapus Folder Git Lama

```bash
rm -rf .git
```

> **Catatan**: Di Windows, gunakan perintah di atas dengan Git Bash atau hapus folder `.git` secara manual melalui File Explorer.

### 2. Inisialisasi Ulang Git

```bash
git init
git config user.name "Nama Baru"
git config user.email "email_baru@example.com"

git add .
git commit -m "Initial commit"
```

### 3. Hubungkan ke Repositori GitHub Baru

Buat repositori baru di GitHub (tanpa README), lalu hubungkan:

```bash
git remote add origin https://github.com/username/nama-repositori.git
git branch -M main
git push -u origin main
```

## Mengatasi Masalah Umum

### Menghapus Token GitHub yang Tersimpan

Jika perlu menghapus token GitHub yang tersimpan di Git Credential Manager:

**Windows:**
```bash
cmdkey /delete:git:https://github.com
```

**macOS:**
```bash
git credential-osxkeychain erase
host=github.com
protocol=https
```

**Linux:**
```bash
git config --global --unset credential.helper
```

## Catatan Penting

- Proses ini akan **menghapus seluruh histori commit** dari repositori lokal.
- Repositori akan memiliki hanya satu commit awal dengan identitas baru.
- Jika repositori sudah ada di GitHub, Anda mungkin perlu melakukan force push (`git push -f`).
  
> ⚠️ **Perhatian**: Force push dapat menimpa histori remote. Gunakan dengan hati-hati terutama pada repositori bersama.

---

**Selamat!** Repositori Anda sekarang menggunakan identitas kontributor yang baru.
