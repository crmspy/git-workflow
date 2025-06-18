# 📘 Git Workflow & Software Lifecycle Guide

Repository ini berisi panduan lengkap dan praktis mengenai workflow Git, konvensi penamaan branch, commit message, code review, serta otomatisasi pengembangan perangkat lunak untuk tim pengembang.  
Dokumentasi ini dirancang agar mudah diikuti oleh seluruh anggota tim, baik untuk onboarding maupun menjaga konsistensi proses pengembangan.

## Fitur Utama

- Penjelasan berbagai workflow Git (Git Flow, GitHub Flow, Trunk-based)
- Konvensi penamaan branch yang konsisten dan mudah dilacak
- Standar penulisan commit message dengan Conventional Commit
- Best practice Pull Request & code review
- Otomatisasi linting, unit test, dan code review di CI/CD
- Tips penggunaan tools seperti CODEOWNERS, commitlint, dan integrasi dengan VS Code
## Tujuan

- Membantu tim menjaga kualitas, keamanan, dan keterlacakan kode
- Memudahkan kolaborasi dan review antar anggota tim
- Mendukung otomatisasi proses release dan dokumentasi perubahan

## Untuk Siapa

Panduan ini cocok untuk:
- Team lead, developer, dan QA di perusahaan software
- Tim yang ingin meningkatkan standar kolaborasi dan kualitas kode
- Siapa saja yang ingin mengadopsi workflow modern dan best practice dalam pengembangan perangkat lunak
---
## 📑 Daftar Isi

- [🔁 Strategi Branching dan Workflow](1.%20workflow.md)
- [🔹 Naming Convention](2.%20naming%20convention.md)
- [✅ Commit Message](3.%20commit.md)
- [✅ Code Review & Pull Request](4.%20code%20review.md)
- [🔖 Versioning & Release](5.%20version%20release.md)
- [🐛 Issue, Bug, dan Hotfix Management](6.%20management%20issue.md)
- [🧠 Advanced Git Usage](7.%20advanced%20git%20usage.md)

---

**Silakan fork, gunakan, dan modifikasi sesuai kebutuhan tim Anda!**

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


Panduan ini bisa kamu sesuaikan dengan kebutuhan tim dan tools (GitHub, GitLab, Bitbucket). Jika butuh versi PDF atau dokumentasi Notion, tinggal konversi markdown ini. 🚀
