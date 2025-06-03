# GitHub Command List

Dokumentasi berikut mencakup daftar perintah (command) yang sering digunakan dalam pengelolaan repository GitHub via terminal/command line, beserta penjelasannya.

---

## 1. Konfigurasi Awal

| Perintah | Deskripsi |
|----------|-----------|
| `git config --global user.name "Nama Anda"` | Mengatur nama user yang akan digunakan pada setiap commit. |
| `git config --global user.email "email@domain.com"` | Mengatur email user yang akan digunakan pada setiap commit. |
| `git config --list` | Melihat konfigurasi git yang sedang aktif. |

---

## 2. Repository Management

| Perintah | Deskripsi |
|----------|-----------|
| `git init` | Membuat repository Git baru di direktori saat ini. |
| `git clone <url>` | Mengkloning repository dari GitHub ke lokal. |
| `git remote add origin <url>` | Menambahkan remote repository yang bernama `origin`. |

---

## 3. Status & Log

| Perintah | Deskripsi |
|----------|-----------|
| `git status` | Melihat status perubahan file di repository. |
| `git log` | Melihat riwayat commit pada branch saat ini. |
| `git log --oneline` | Melihat riwayat commit secara ringkas. |

---

## 4. Branching

| Perintah | Deskripsi |
|----------|-----------|
| `git branch` | Melihat daftar branch yang ada di repository. |
| `git branch <nama-branch>` | Membuat branch baru. |
| `git checkout <nama-branch>` | Berpindah ke branch tertentu. |
| `git checkout -b <nama-branch>` | Membuat branch baru dan langsung berpindah ke branch tersebut. |

---

## 5. Staging & Commit

| Perintah | Deskripsi |
|----------|-----------|
| `git add <file>` | Menambahkan file ke staging area. |
| `git add .` | Menambahkan seluruh file yang berubah ke staging area. |
| `git commit -m "Pesan commit"` | Menyimpan perubahan ke repository dengan pesan tertentu. |
| `git commit -am "Pesan commit"` | Menambahkan dan commit file yang sudah pernah di-track sekaligus. |

---

## 6. Push & Pull

| Perintah | Deskripsi |
|----------|-----------|
| `git push origin <branch>` | Mengirim perubahan branch lokal ke remote. |
| `git push -u origin <branch>` | Push branch baru sekaligus set upstream. |
| `git pull` | Mengambil perubahan terbaru dari remote dan menggabungkannya dengan lokal. |

---

## 7. Merge & Rebase

| Perintah | Deskripsi |
|----------|-----------|
| `git merge <branch>` | Menggabungkan branch tertentu ke branch aktif. |
| `git rebase <branch>` | Mengaplikasikan commit branch aktif di atas branch tertentu. |

---

## 8. Undo & Reset

| Perintah | Deskripsi |
|----------|-----------|
| `git checkout -- <file>` | Mengembalikan file ke kondisi commit terakhir. |
| `git reset <file>` | Menghapus file dari staging area. |
| `git reset --hard <commit>` | Mengembalikan repository ke state commit tertentu, menghapus perubahan setelahnya. |

---

## 9. Tagging

| Perintah | Deskripsi |
|----------|-----------|
| `git tag` | Melihat daftar tag pada repository. |
| `git tag <nama-tag>` | Membuat tag baru pada commit terakhir. |
| `git push origin <nama-tag>` | Mengirim tag ke remote repository. |

---

## 10. Lain-lain

| Perintah | Deskripsi |
|----------|-----------|
| `git fetch` | Mengambil perubahan terbaru dari remote tanpa merge. |
| `git stash` | Menyimpan sementara perubahan yang belum di-commit. |
| `git stash pop` | Mengembalikan perubahan yang disimpan dengan stash. |

---

## 11. GitHub CLI (gh)

GitHub CLI (`gh`) adalah command-line tool resmi dari GitHub.

| Perintah | Deskripsi |
|----------|-----------|
| `gh auth login` | Login ke akun GitHub melalui CLI. |
| `gh repo clone <owner>/<repo>` | Mengkloning repository GitHub dengan CLI. |
| `gh pr create` | Membuat pull request dari branch aktif. |
| `gh issue list` | Melihat daftar issue pada repository. |
| `gh pr merge <number/id>` | Melakukan merge pull request tertentu. |

---

## Referensi

- [Pro Git Book](https://git-scm.com/book/id/v2)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [GitHub Docs](https://docs.github.com/)

---

*Dokumentasi ini bisa dikembangkan sesuai kebutuhan tim/proyek.*
