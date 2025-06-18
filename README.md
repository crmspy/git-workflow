# 📘 Git Workflow & Software Lifecycle Guide for Team Leads

Panduan ini dibuat untuk engineer dan team lead yang mengelola workflow Git, code review, versioning, issue, bug, dan hotfix secara profesional. Cocok untuk proyek skala kecil hingga besar, baik open-source maupun enterprise.

---

## 🔁 Strategi Branching dan Workflow

### 🔹 Pilihan Workflow

* **Git Flow**: Cocok untuk release teratur dan tim besar
* **GitHub Flow**: Cocok untuk CI/CD dan rilis cepat
* **Trunk-based**: Cocok untuk tim kecil/agile dan eksperimen cepat

### 🔹 Naming Convention

* `feature/<fitur>`
* `bugfix/<id-issue>`
* `hotfix/<patch-critical>`
* `release/<versi>`

### 🔹 Praktik

* Hindari commit langsung ke `main`
* Merge dilakukan via Pull Request (PR)
* Hapus branch setelah merge untuk menjaga kebersihan

---
## ✅ Commit Message

Commit message yang baik sangat penting untuk memudahkan tracking perubahan, kolaborasi, dan proses review. Gunakan format **Conventional Commit** agar konsisten dan mudah dipahami.

**Format dasar:**
```
<type>: <deskripsi singkat>
```
---

## ✅ Code Review & Pull Request

### 🔹 Best Practice PR

* Deskriptif dan berisi konteks perubahan
* Hubungkan ke issue dengan `Fixes #123`
* Tambahkan checklist:

  ```md
  - [ ] Sudah test lokal
  - [ ] Lolos lint dan unit test
  - [ ] Sudah di-review rekan
  ```

### 🔹 Review Efektif

* Beri komentar jelas dan actionable
* Batasi jumlah file/line dalam PR besar

### 🔹 Otomatisasi

* Gunakan `CODEOWNERS`
* Setup branch protection rule

---

## 🔖 Versioning & Release

### 🔹 Semantic Versioning

* Format: `MAJOR.MINOR.PATCH`
* Contoh: `v2.1.0`

### 🔹 Release Workflow

1. Merge PR ke `main`
2. Buat tag: `git tag v1.2.3`
3. Push tag: `git push origin v1.2.3`
4. CI/CD otomatis deploy dari tag

### 🔹 Hotfix Workflow

* Buat branch `hotfix/x.y.z`
* Fix → commit → PR ke `main` dan `develop`
* Tag dan deploy segera

---

## 🐛 Issue, Bug, dan Hotfix Management

### 🔹 Issue Workflow

1. Buat issue dengan label (`bug`, `enhancement`, `urgent`)
2. Buat branch `bugfix/<id>`
3. Commit dengan `Fixes #<id>`
4. Merge PR → otomatis menutup issue

### 🔹 Checklist Penanganan Bug

* Langkah reproduksi
* Log yang muncul
* Versi aplikasi saat bug terjadi

---

## 🧠 Advanced Git Usage

### 🔹 Tools dan Perintah Penting

* `git rebase` – linearisasi commit
* `git cherry-pick` – ambil commit spesifik
* `git bisect` – cari commit penyebab bug
* `git blame` – lihat siapa mengubah baris
* `git reset` / `revert` – undo perubahan
* Gunakan `--force-with-lease` jika perlu `force push`

---

## 🧰 Repo Maintenance

### 🔹 Monorepo

* Gunakan `git submodule` atau `subtree` untuk struktur repo modular

### 🔹 Cleanup

* Hapus branch lama secara rutin
* Gunakan `git gc` atau `git filter-repo` untuk bersih-bersih riwayat besar

### 🔹 Git Hook & Automation

* `pre-commit`: lint dan format otomatis
* `commit-msg`: enforce format commit (conventional commit)
* Tools: Husky, Commitlint

---

## 📑 Templates & Checklist

### ✅ PR Checklist Template

```md
- [ ] Sudah test fitur utama
- [ ] Tidak ada error di console
- [ ] Fix terkait issue: #___
- [ ] Reviewer sudah approve
```

### 📄 Format Commit

* `feat: menambahkan fitur baru`
* `fix: memperbaiki bug saat login`
* `docs: update dokumentasi`
* `refactor: optimasi kode tanpa mengubah behavior`

### 🐞 Simulasi Hotfix

1. Terjadi bug di production
2. Buat branch `hotfix/critical-fix`
3. Fix & PR → merge ke `main` + `develop`
4. Buat tag `vX.Y.Z`
5. Deploy

---

Panduan ini bisa kamu sesuaikan dengan kebutuhan tim dan tools (GitHub, GitLab, Bitbucket). Jika butuh versi PDF atau dokumentasi Notion, tinggal konversi markdown ini. 🚀
