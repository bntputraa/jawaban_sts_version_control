# sts_version_control

## 1. Keuntungan pembatasan branch `main`

Keuntungan utamanya yaitu **mengurangi risiko website error atau rusak**. Jadi, anggota tim tidak bisa langsung mengubah kode yang ada di `main`.

Setiap fitur baru dibuat di branch sendiri, lalu dicek dan ditinjau terlebih dahulu sebelum digabung ke `main`.

Dengan cara ini, kalau fitur MFA ternyata masih ada error, branch `main` tetap aman dan website yang sedang digunakan tidak ikut bermasalah.

## 2. Perintah Git yang digunakan

Misalnya nama branch untuk fitur MFA adalah `feature/mfa`.

```bash
# 1. Pindah ke branch main
git checkout main

# 2. Ambil update terbaru dari GitHub
git pull origin main

# 3. Buat branch baru untuk fitur MFA
git checkout -b feature/mfa

# 4. Cek branch yang sedang digunakan
git branch

# 5. Setelah mengerjakan fitur MFA, cek perubahan
git status

# 6. Menambahkan semua perubahan ke staging
git add .

# 7. Menyimpan perubahan dengan commit
git commit -m "Menambahkan fitur autentikasi MFA"

# 8. Mengirim branch ke GitHub
git push -u origin feature/mfa
```

Setelah itu, buka GitHub, pilih branch `feature/mfa`, lalu buat **Pull Request** menuju branch `main`.

Kalau masih ada perubahan setelah ditinjau, bisa menggunakan:

```bash
git add .
git commit -m "Memperbaiki fitur MFA"
git push
```
