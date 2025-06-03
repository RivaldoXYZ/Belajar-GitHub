# GitHub Command List

Dokumentasi berikut mencakup daftar perintah (command) yang sering digunakan dalam pengelolaan repository GitHub via terminal/command line, beserta penjelasannya secara detail.

---

## 1. Konfigurasi Awal

| Perintah | Deskripsi |
|----------|-----------|
| `git config --global user.name "Nama Anda"` | Mengatur nama pengguna global untuk git commit. |
| `git config --global user.email "email@domain.com"` | Mengatur email global untuk git commit. |
| `git config --list` | Menampilkan semua konfigurasi git yang sedang digunakan. |

---

## 2. Repository Management

| Perintah | Deskripsi |
|----------|-----------|
| `git init` | Menginisialisasi repository Git baru di direktori lokal. |
| `git clone <url>` | Mengkloning repository dari remote ke lokal. |
| `git remote add origin <url>` | Menambahkan remote dengan nama `origin`. |
| `git remote -v` | Melihat daftar remote pada repository. |
| `git remote remove <nama-remote>` | Menghapus remote tertentu dari repository. |

---

## 3. Status & Log

| Perintah | Deskripsi |
|----------|-----------|
| `git status` | Menampilkan status file yang berubah, staged, dan belum di-track. |
| `git log` | Menampilkan riwayat commit secara detail. |
| `git log --oneline` | Menampilkan riwayat commit secara singkat. |
| `git log --graph --oneline --all` | Menampilkan riwayat commit dalam bentuk grafik. |

---

## 4. Branching

| Perintah | Deskripsi |
|----------|-----------|
| `git branch` | Melihat daftar branch pada repository. |
| `git branch <nama-branch>` | Membuat branch baru. |
| `git checkout <nama-branch>` | Pindah ke branch tertentu. |
| `git checkout -b <nama-branch>` | Membuat branch baru dan langsung berpindah ke branch tersebut. |
| `git branch -d <nama-branch>` | Menghapus branch lokal. |
| `git push origin --delete <nama-branch>` | Menghapus branch dari remote. |

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
| `git push origin <branch>` | Mengirim (push) branch ke remote repository. |
| `git push -u origin <branch>` | Push branch baru dan set upstream. |
| `git pull` | Mengambil (fetch) dan menggabungkan (merge) perubahan terbaru dari remote ke lokal. |
| `git fetch` | Mengambil perubahan dari remote tanpa melakukan merge ke branch aktif. |
| `git fetch origin` | Mengambil perubahan dari remote `origin`. |

---

## 7. Compare & Diff

| Perintah | Deskripsi |
|----------|-----------|
| `git diff` | Melihat perbedaan/perubahan yang belum di-staging. |
| `git diff --staged` | Melihat perbedaan antara staging area dan commit terakhir. |
| `git diff <branch1>..<branch2>` | Membandingkan perbedaan antara dua branch. |
| `git diff <commit1> <commit2>` | Membandingkan perbedaan antara dua commit tertentu. |
| `git show <commit>` | Menampilkan detail perubahan pada commit tertentu. |
| `git log <branch1>..<branch2>` | Menampilkan commit yang ada di `<branch2>` tapi tidak di `<branch1>`. |

---

## 8. Merge & Rebase

| Perintah | Deskripsi |
|----------|-----------|
| `git merge <branch>` | Menggabungkan branch tertentu ke branch aktif. |
| `git rebase <branch>` | Mengaplikasikan commit branch aktif di atas branch tertentu. |
| `git merge --abort` | Membatalkan merge yang sedang berlangsung. |
| `git rebase --abort` | Membatalkan proses rebase yang sedang berlangsung. |
| `git cherry-pick <commit>` | Mengambil commit tertentu dari branch lain ke branch aktif. |

---

## 9. Membatalkan Perubahan (Undo/Reset/Revert)

| Perintah | Deskripsi |
|----------|-----------|
| `git checkout -- <file>` | Mengembalikan file ke kondisi commit terakhir. (Akan menghapus perubahan lokal yang belum di-commit) |
| `git restore <file>` | Mengembalikan file ke kondisi commit terakhir (alternatif modern dari `git checkout -- <file>`). |
| `git reset <file>` | Menghapus file dari staging area, tidak menghapus perubahan pada file. |
| `git reset HEAD~1` | Menghapus commit terakhir dan mengembalikan perubahan ke staging area. |
| `git reset --hard <commit>` | Mengembalikan repository ke state commit tertentu, semua perubahan setelah commit tersebut akan hilang. **Hati-hati!** |
| `git revert <commit>` | Membuat commit baru untuk membatalkan perubahan dari commit tertentu tanpa mengubah riwayat commit. |
| `git clean -fd` | Menghapus file yang tidak di-track pada repository. **Pastikan sudah melakukan backup jika perlu!** |

---

## 10. Tagging

| Perintah | Deskripsi |
|----------|-----------|
| `git tag` | Melihat daftar tag pada repository. |
| `git tag <nama-tag>` | Membuat tag baru pada commit terakhir. |
| `git tag -a <nama-tag> -m "deskripsi"` | Membuat tag anotasi dengan deskripsi. |
| `git push origin <nama-tag>` | Mengirim tag ke remote repository. |
| `git push origin --tags` | Mengirim semua tag ke remote repository. |
| `git tag -d <nama-tag>` | Menghapus tag lokal. |
| `git push --delete origin <nama-tag>` | Menghapus tag dari remote. |

---

## 11. Stash (Menyimpan Perubahan Sementara)

| Perintah | Deskripsi |
|----------|-----------|
| `git stash` | Menyimpan perubahan sementara yang belum di-commit. |
| `git stash list` | Melihat daftar perubahan yang di-stash. |
| `git stash pop` | Mengambil kembali perubahan terakhir yang di-stash dan menghapusnya dari daftar stash. |
| `git stash apply <stash@{n}>` | Mengambil kembali perubahan tertentu dari daftar stash tanpa menghapusnya dari daftar. |
| `git stash drop <stash@{n}>` | Menghapus stash tertentu dari daftar stash. |
| `git stash clear` | Menghapus semua stash. |

---

## 12. Lain-lain

| Perintah | Deskripsi |
|----------|-----------|
| `git blame <file>` | Melihat siapa yang terakhir mengubah setiap baris pada file. |
| `git shortlog -s -n` | Menampilkan statistik commit per kontributor. |
| `git archive --format=zip --output=repo.zip master` | Mengekspor repository ke dalam bentuk zip. |

---

## 13. GitHub CLI (gh)

GitHub CLI (`gh`) adalah command-line tool resmi dari GitHub untuk mengelola repository, issues, pull request, dan lainnya secara langsung dari terminal.

| Perintah | Deskripsi |
|----------|-----------|
| `gh auth login` | Login ke akun GitHub melalui CLI. |
| `gh repo clone <owner>/<repo>` | Mengkloning repository GitHub dengan CLI. |
| `gh pr create` | Membuat pull request dari branch aktif. |
| `gh pr list` | Melihat daftar pull request di repository. |
| `gh pr view <number/id>` | Melihat detail pull request tertentu. |
| `gh pr checkout <number/id>` | Checkout ke pull request tertentu. |
| `gh pr merge <number/id>` | Melakukan merge pull request tertentu. |
| `gh issue list` | Melihat daftar issue pada repository. |
| `gh issue view <number/id>` | Melihat detail issue tertentu. |
| `gh issue close <number/id>` | Menutup issue tertentu. |
| `gh release create <tag>` | Membuat rilis baru di GitHub. |

---

## Referensi

- [Pro Git Book](https://git-scm.com/book/id/v2)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [GitHub Docs](https://docs.github.com/)

---

*Dokumentasi ini bisa dikembangkan sesuai kebutuhan tim/proyek.*
