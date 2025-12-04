# Telaten Apps

Monorepo untuk aplikasi Telaten (Backend, Client/Frontend, dan API Docs).

## 📂 Struktur Repository

- **telaten-backend**: Backend service (Python/FastAPI).
- **telaten-client**: Frontend application (Next.js).
- **telaten-docs-api**: Dokumentasi API (Bruno Collection).

## 🚀 Cara Clone Repository (PENTING)

Karena repository ini menggunakan **Git Submodules**, Anda harus meng-clone dengan cara khusus untuk memastikan semua folder terisi.

### Opsi 1: Clone dari awal
Gunakan flag `--recurse-submodules` saat clone:
```bash
git clone --recurse-submodules https://github.com/username/telaten-apps.git
cd telaten-apps
```

### Opsi 2: Jika sudah terlanjur clone biasa
Jika folder submodule kosong, jalankan perintah berikut di root project:
```bash
git submodule update --init --recursive
```

---

## 🛠️ Setup & Menjalankan Aplikasi

### 1. Backend (`telaten-backend`)

Backend dibangun menggunakan Python (FastAPI).

**Prerequisites:**
- Python >= 3.12
- PostgreSQL (Pastikan database sudah berjalan)

**Langkah-langkah:**

1. Masuk ke direktori backend:
   ```bash
   cd telaten-backend
   ```

2. Buat file `.env`:
   ```bash
   cp .env.example .env
   ```
   *Sesuaikan konfigurasi di dalam `.env` (terutama `DATABASE_URL` dan `SECRET_KEY`).*

3. Install dependencies:
   Disarankan menggunakan `uv` (karena ada `uv.lock`), tapi `pip` juga bisa.
   
   **Menggunakan pip:**
   ```bash
   pip install .
   # Atau jika ingin mode editable (development)
   pip install -e .
   ```

4. Jalankan aplikasi:
   ```bash
   python run.py
   ```
   Server akan berjalan di `http://localhost:8000`.

---

### 2. Frontend (`telaten-client`)

Frontend dibangun menggunakan Next.js.

**Prerequisites:**
- Node.js
- Bun (Disarankan, karena ada `bun.lock`) atau npm

**Langkah-langkah:**

1. Masuk ke direktori client:
   ```bash
   cd telaten-client
   ```

2. Buat file `.env.local`:
   ```bash
   cp .env.example .env.local
   ```
   *Isi `NEXT_PUBLIC_API_BASE_URL` dengan URL backend (default: `http://localhost:8000/api/v1`).*

3. Install dependencies:
   ```bash
   bun install
   # atau
   npm install
   ```

4. Jalankan mode development:
   ```bash
   bun dev
   # atau
   npm run dev
   ```
   Aplikasi akan berjalan di `http://localhost:3000`.

---

### 3. API Documentation (`telaten-docs-api`)

Dokumentasi API dikelola menggunakan **Bruno**.

1. Install aplikasi [Bruno](https://www.usebruno.com/).
2. Buka Bruno, pilih **Open Collection**.
3. Arahkan ke folder `telaten-docs-api`.
4. Anda bisa langsung mencoba endpoint-endpoint yang tersedia (pastikan Environment di Bruno diset ke `local`).

## 🐳 Docker (Opsional)

Untuk backend, terdapat support Docker.

```bash
cd telaten-backend
docker-compose up -d
```
