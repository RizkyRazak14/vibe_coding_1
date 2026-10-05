# Planning: Project Setup (Bun + ElysiaJS + Drizzle ORM + MySQL)

## Overview
Dokumen perencanaan ini bertujuan untuk memandu inisialisasi dan konfigurasi proyek baru di folder ini. Dokumentasi disusun secara *high-level* agar dapat dieksekusi secara sistematis oleh developer atau LLM.

---

## 🛠️ Stack Teknologi
- **Runtime & Package Manager**: Bun
- **Web Framework**: ElysiaJS
- **ORM**: Drizzle ORM (dengan Drizzle Kit)
- **Database**: MySQL

---

## 📋 Langkah-Langkah Implementasi

### 1. Inisialisasi Proyek Bun & ElysiaJS
- Inisialisasi proyek Bun baru pada folder ini.
- Install dependency utama **ElysiaJS** (`elysia`).
- Buat file *entry point* server dasar (misal: `src/index.ts`) dengan endpoint `GET /` untuk verifikasi kesehatan server.

### 2. Instalasi & Konfigurasi Drizzle ORM + MySQL
- Install dependency **Drizzle ORM** (`drizzle-orm`) dan driver **MySQL** (`mysql2`).
- Install dev-dependencies pendukung seperti `drizzle-kit`.
- Buat konfigurasi environment variable (`.env` dan `.env.example`) untuk simpan data koneksi MySQL (host, port, user, password, database).
- Buat file konfigurasi Drizzle (`drizzle.config.ts`).

### 3. Setup Struktur Folder & Skema Database
- Susun struktur folder modul/fitur di dalam `src/`:
  - `src/db/`: Koneksi database (`index.ts`) dan definisi skema (`schema.ts`).
  - `src/routes/` atau `src/controllers/`: Endpoint & logika handler ElysiaJS.
- Buat skema tabel dasar contoh (misal: tabel `users`) menggunakan Drizzle MySQL schemabuilder.
- Integrasikan koneksi Drizzle ke server ElysiaJS.

### 4. Konfigurasi Scripts (`package.json`)
- Tambahkan script utama pada `package.json`:
  - `dev`: Menjalankan server dalam mode watch (`bun run --watch src/index.ts`).
  - `db:generate`: Generate migrasi SQL dari skema Drizzle.
  - `db:push`: Apply/push perubahan skema Drizzle langsung ke database MySQL.

### 5. Verifikasi & Pengujian
- Jalankan server lokal dan pastikan server Elysia dapat menerima request.
- Pastikan Drizzle ORM terhubung tanpa error ke database MySQL.

---

## 🎯 Definition of Done (DoD)
- [ ] Project Bun + ElysiaJS terinisialisasi dan berjalan lancar.
- [ ] Drizzle ORM terkonfigurasi dengan driver MySQL dan `drizzle-kit`.
- [ ] File `.env.example` dan `drizzle.config.ts` siap digunakan.
- [ ] Skema dasar Drizzle dan koneksi DB telah dibuat.
- [ ] Script `dev`, `db:generate`, dan `db:push` siap dieksekusi di `package.json`.
