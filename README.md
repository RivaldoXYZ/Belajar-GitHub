# GitHub Command List & Argument Options

Dokumentasi berikut mencakup daftar perintah Git yang sering digunakan pada pengelolaan repository GitHub via terminal/command line, dilengkapi penjelasan dan opsi argumen (argument options) pada masing-masing perintah.

---

## 1. Konfigurasi Awal

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git config --global user.name "<nama>"` | Mengatur nama pengguna global untuk commit. |
| `git config --global user.email "<email>"` | Mengatur email global untuk commit. |
| `git config --list` | Menampilkan semua konfigurasi git yang sedang digunakan. |

---

## 2. Repository Management

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git init` | Membuat repository Git baru di direktori lokal. |
| `git clone <url-repo>` | Mengkloning repository dari remote ke lokal. |
| `git remote add <nama-remote> <url-repo>` | Menambahkan remote baru. Biasanya `origin`. |
| `git remote -v` | Menampilkan daftar remote pada repo. |
| `git remote remove <nama-remote>` | Menghapus remote tertentu dari repository. |

---

## 3. Status & Log

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git status` | Menampilkan status file yang berubah, staged, dan belum di-track. |
| `git log` | Menampilkan riwayat commit secara detail. |
| `git log --oneline` | Menampilkan riwayat commit secara ringkas. |
| `git log --graph --oneline --all` | Menampilkan riwayat commit dalam bentuk grafik. |

---

## 4. Branching

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git branch` | Melihat daftar branch pada repository. |
| `git branch <nama-branch>` | Membuat branch baru. |
| `git checkout <nama-branch>` | Pindah ke branch tertentu. |
| `git checkout -b <nama-branch>` | Membuat branch baru dan langsung pindah ke branch tersebut. |
| `git branch -d <nama-branch>` | Menghapus branch lokal. |
| `git push origin --delete <nama-branch>` | Menghapus branch dari remote. |

---

## 5. Staging & Commit

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git add <file>` | Menambahkan file ke staging area. |
| `git add .` | Menambahkan seluruh file yang berubah ke staging area. |
| `git commit -m "<pesan>"` | Menyimpan perubahan ke repository dengan pesan tertentu. |
| `git commit -am "<pesan>"` | Menambahkan dan commit file yang sudah pernah di-track sekaligus. |

---

## 6. Push & Pull

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git push <remote> <branch>` | Mengirim (push) branch ke remote repository. |
| `git push -u <remote> <branch>` | Push branch baru dan set upstream. |
| `git pull <remote> <branch>` | Mengambil (fetch) dan menggabungkan (merge) perubahan dari remote ke lokal. |
| `git fetch <remote>` | Mengambil perubahan dari remote tanpa merge. |

---

## 7. Compare & Diff

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git diff` | Melihat perbedaan/perubahan yang belum di-staging. |
| `git diff --staged` | Melihat perbedaan antara staging area dan commit terakhir. |
| `git diff <branch1>..<branch2>` | Membandingkan perbedaan antara dua branch. |
| `git diff <commit1> <commit2>` | Membandingkan perbedaan antara dua commit tertentu. |
| `git show <commit>` | Menampilkan detail perubahan pada commit tertentu. |
| `git log <branch1>..<branch2>` | Menampilkan commit yang ada di `<branch2>` tapi tidak di `<branch1>`. |

---

## 8. Merge & Rebase

| Perintah & Argumen | Deskripsi |
|--------------------|-----------|
| `git merge <branch>` | Menggabungkan branch tertentu ke branch aktif. |
| `git merge --no-ff <branch>` | Merge dengan forced merge commit (tanpa fast-forward). |
| `git merge --squash <branch>` | Menggabungkan semua commit dari branch menjadi satu commit. |
| `git rebase <branch>` | Mengaplikasikan commit branch aktif di atas branch tertentu. |
| `git rebase -i <branch>` | Interaktif rebase (untuk mengedit, menggabung, menghapus commit). |
| `git merge --abort` | Membatalkan merge yang sedang berlangsung. |
| `git rebase --abort` | Membatalkan proses rebase yang sedang berlangsung. |
| `git cherry-pick <commit>` | Mengambil commit tertentu dari branch lain ke branch aktif. |

---

## 9. Membatalkan Perubahan (Undo/Reset/Revert)

| Perintah & Argumen | Opsi/Argument | Deskripsi |
|--------------------|---------------|-----------|
| `git checkout -- <file>` |  | Mengembalikan file ke kondisi commit terakhir. |
| `git restore <file>` |  | Mengembalikan file ke kondisi commit terakhir (alternatif modern). |
| `git reset <file>` |  | Menghapus file dari staging area, tidak menghapus perubahan pada file. |
| `git reset HEAD~1` |  | Menghapus commit terakhir dan mengembalikan perubahan ke staging area. |
| `git reset` | `--soft`, `--mixed`, `--hard` | Mengatur posisi HEAD dan status file:<br>- `--soft`: HEAD pindah, file tetap staged.<br>- `--mixed` (default): HEAD pindah, file unstaged.<br>- `--hard`: HEAD pindah, file lokal diubah sesuai commit, perubahan hilang. **Hati-hati!** |
| `git revert <commit>` |  | Membuat commit baru untuk membatalkan perubahan dari commit tertentu tanpa mengubah riwayat commit. |
| `git clean -fd` | `-f`, `-d`, `-n` | Membersihkan file yang tidak di-track:<br>- `-f`: force, harus digunakan.<br>- `-d`: termasuk direktori.<br>- `-n`: dry run, hanya menampilkan file yang akan dihapus. |

---

## 10. Tagging

| Perintah & Argumen | Opsi/Argument | Deskripsi |
|--------------------|---------------|-----------|
| `git tag` |  | Melihat daftar tag pada repository. |
| `git tag <nama-tag>` |  | Membuat tag baru pada commit terakhir. |
| `git tag -a <nama-tag> -m "<deskripsi>"` | `-a`, `-m` | Membuat tag anotasi dengan deskripsi.<br>- `-a`: annotated.<br>- `-m`: pesan deskripsi. |
| `git push <remote> <nama-tag>` |  | Mengirim tag ke remote repository. |
| `git push <remote> --tags` | `--tags` | Mengirim semua tag ke remote repository. |
| `git tag -d <nama-tag>` |  | Menghapus tag lokal. |
| `git push <remote> --delete <nama-tag>` | `--delete` | Menghapus tag dari remote. |

---

## 11. Stash (Menyimpan Perubahan Sementara)

| Perintah & Argumen | Opsi/Argument | Deskripsi |
|--------------------|---------------|-----------|
| `git stash` |  | Menyimpan perubahan sementara yang belum di-commit. |
| `git stash save "<pesan>"` | `save` | Menyimpan stash dengan pesan tertentu (deprecated, gunakan `push`). |
| `git stash push -m "<pesan>"` | `-m` | Menyimpan stash dengan pesan (modern). |
| `git stash list` |  | Melihat daftar perubahan yang di-stash. |
| `git stash pop` |  | Mengambil kembali perubahan terakhir yang di-stash dan menghapusnya dari daftar stash. |
| `git stash apply <stash@{n}>` |  | Mengambil kembali perubahan tertentu dari daftar stash tanpa menghapusnya dari daftar. |
| `git stash drop <stash@{n}>` |  | Menghapus stash tertentu dari daftar stash. |
| `git stash clear` |  | Menghapus semua stash. |

---

## 12. Lain-lain

| Perintah & Argumen | Opsi/Argument | Deskripsi |
|--------------------|---------------|-----------|
| `git blame <file>` |  | Menampilkan siapa yang terakhir mengubah setiap baris pada file. |
| `git shortlog -s -n` | `-s`, `-n` | Statistik commit per kontributor:<br>- `-s`: hanya jumlah commit.<br>- `-n`: urutkan berdasarkan jumlah. |
| `git archive --format=zip --output=<nama-file>.zip <branch>` | `--format`, `--output` | Mengekspor repository ke bentuk zip atau tar. |

---

## 13. GitHub CLI (`gh`)

| Perintah & Argumen | Opsi/Argument | Deskripsi |
|--------------------|---------------|-----------|
| `gh auth login` |  | Login ke akun GitHub melalui CLI. |
| `gh repo clone <owner>/<repo>` |  | Mengkloning repository GitHub dengan CLI. |
| `gh pr create` | `--base`, `--head`, `--title`, `--body` | Membuat pull request.<br>- `--base`: branch tujuan.<br>- `--head`: branch sumber.<br>- `--title`: judul PR.<br>- `--body`: deskripsi PR. |
| `gh pr list` | `--state`, `--author`, `--assignee` | Melihat daftar pull request.<br>- `--state`: open/closed/merged.<br>- `--author`: filter penulis.<br>- `--assignee`: filter penugas. |
| `gh pr view <number/id>` | `--web` | Melihat detail PR (opsi buka di web). |
| `gh pr checkout <number/id>` |  | Checkout ke pull request tertentu. |
| `gh pr merge <number/id>` | `--merge`, `--squash`, `--rebase` | Merge PR dengan opsi:<br>- `--merge`: merge biasa.<br>- `--squash`: gabung semua commit.<br>- `--rebase`: rebase commit. |
| `gh issue list` | `--state`, `--label` | Melihat daftar issue.<br>- `--state`: open/closed/all.<br>- `--label`: filter label. |
| `gh issue view <number/id>` |  | Melihat detail issue tertentu. |
| `gh issue close <number/id>` |  | Menutup issue tertentu. |
| `gh release create <tag>` | `--title`, `--notes` | Membuat rilis baru di GitHub.<br>- `--title`: judul rilis.<br>- `--notes`: catatan/changelog. |

---

## Referensi

- [Pro Git Book](https://git-scm.com/book/id/v2)
- [GitHub CLI Documentation](https://cli.github.com/manual/)
- [GitHub Docs](https://docs.github.com/)

---

*Dokumentasi ini bisa dikembangkan sesuai kebutuhan tim/proyek.*
