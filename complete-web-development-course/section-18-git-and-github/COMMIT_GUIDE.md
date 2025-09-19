# 🗂️ Commit Message Guide
Panduan penulisan commit message untuk menjaga repository tetap **rapi, profesional, dan mudah dibaca**.  
Menggunakan standar **Conventional Commits**.

---

## ✨ Struktur Commit Message
```
<type>(optional-scope): <short summary>
```

**Keterangan:**
- **`<type>`** → Jenis perubahan (misalnya: `feat`, `fix`, `docs`).
- **`(optional-scope)`** → Bagian spesifik yang diubah (opsional, tapi disarankan).
- **`<short summary>`** → Deskripsi singkat dalam bentuk perintah (*imperative*).

> ⚡ *Contoh imperative:* `add`, `fix`, `update`.  
> ❌ Jangan pakai: `added`, `fixed`, `updated`.

---

## 🌱 Jenis Commit (Type)

| Type      | Kapan Dipakai | Contoh |
|-----------|---------------|--------|
| **feat**  | Menambahkan **fitur baru** | `feat: add dark mode toggle button` |
| **fix**   | Memperbaiki **bug** | `fix: resolve file upload error on Vercel` |
| **docs**  | Update **dokumentasi** atau catatan | `docs(git): add notes for section 18 about Git basics` |
| **chore** | Hal rutin, maintenance, **bukan fitur/bug/docs** | `chore(repo): clean up unused files` |
| **style** | Perubahan **tampilan atau format** (tanpa ubah logic) | `style(css): improve button hover effect` |
| **refactor** | Mengubah **struktur kode** tanpa ubah behavior | `refactor(journal): reorganize daily notes folder` |
| **test** | Menambahkan atau memperbaiki **test code** | `test(upload): add unit tests for file upload feature` |
| **perf** | **Optimisasi performa** aplikasi | `perf: improve file upload speed by 20%` |
| **ci** | Perubahan pada **CI/CD, deployment, atau workflow** | `ci: fix Vercel deployment config` |

---

## 🌟 Tips Commit Message
1. **Bahasa Inggris** → lebih profesional dan universal.
2. **Singkat dan jelas** → max 50-72 karakter untuk deskripsi singkat.
3. **Gunakan scope bila perlu** → `(journal)`, `(navbar)`, `(auth)`, dll.
4. **Satu commit = satu perubahan besar**
   - Jangan campur-campur fitur, bug fix, dan docs dalam satu commit.

---

## 🧩 Contoh Penggunaan
### 1. Menambah catatan baru di journal:
```
docs(journal): add day-12 notes about Git basics
```

### 2. Menambahkan template folder harian:
```
feat(journal): add daily note template for September 2025
```

### 3. Memperbaiki error upload file:
```
fix(upload): resolve IPFS upload issue on Vercel
```

### 4. Merapikan struktur folder repo:
```
chore(repo): restructure journal and courses folder
```

### 5. Update tampilan UI:
```
style(navbar): adjust padding and improve hover effect
```

---

## 📜 Ringkasan
- **`feat`** → Fitur baru  
- **`fix`** → Perbaikan bug  
- **`docs`** → Dokumentasi & catatan  
- **`chore`** → Maintenance dan hal rutin  
- **`style`** → Perubahan tampilan, bukan logic  
- **`refactor`** → Bersih-bersih code tanpa fitur baru  
- **`test`** → Menambahkan atau memperbaiki test code  
- **`perf`** → Optimisasi performa  
- **`ci`** → Perubahan pipeline / deployment

---

## 🌿 Rekomendasi untuk Journal Maou-sama
Karena ini repo journal belajar, type yang **paling sering dipakai**:
- `docs` → Catatan harian dan update dokumentasi.
- `feat` → Tambah template, struktur, atau fitur baru.
- `fix` → Perbaikan error atau masalah kecil.
- `chore` → Perubahan minor atau maintenance.

---

## 💡 Tips Workflow Harian
### Step 1 — Tambah atau update catatan:
```bash
git add .
git commit -m "docs(journal): add notes for day 15 about HTTP basics"
```

### Step 2 — Push ke GitHub:
```bash
git push
```

### Step 3 — Jika ingin progress terlihat rapi di GitHub:
- Commit setiap hari setelah belajar.
- Boleh push belakangan, GitHub tetap akan menghitung tanggal commit.

---

> Dengan format ini, commit log maou-sama akan terlihat **profesional**, mudah dipahami, dan terstruktur rapi. 🌟
