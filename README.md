---
title: Dashboard Analitik Big Data
emoji: 📊
colorFrom: blue
colorTo: green
sdk: docker
app_port: 8501
pinned: false
---

> **Catatan:** Blok YAML di atas adalah konfigurasi HuggingFace Spaces (Docker, port 8501). Biarkan tetap berada di baris paling atas README; ubah `title` sesuai nama produk data tim.

# Tugas 2: Data Product — Dashboard Analitik Interaktif

Template repositori tim untuk **Tugas 2** mata kuliah **Analisis Big Data** (S1 Teknik Informatika / Sistem Informasi).

---

## Informasi Umum

| Parameter | Keterangan |
|-----------|------------|
| **Tipe Tugas** | Kelompok (2–3 Mahasiswa) |
| **Diumumkan** | Pertemuan 8 (Phase 1); repositori dibagikan Pertemuan 9 |
| **Platform Pengumpulan** | GitHub (fork dari [`UMM-GURU/tugas2-abd-2026`](https://github.com/UMM-GURU/tugas2-abd-2026)) & HuggingFace Spaces |
| **Bobot Penilaian** | 35% dari Nilai Akhir Mata Kuliah |
| **Deadline Final** | Minggu 14 |

---

## Tahapan Milestone Pengerjaan (Incremental Milestones)

| Fase | Diberikan | Target Check-in | Deliverable Utama |
|------|:---------:|:---------------:|-------------------|
| **Phase 1: Pitch dan Architecture** | Pertemuan 8 | Pertemuan 10 | Pembentukan tim, fork repositori dan pengisian `identitas.md`, pengajuan proposal topik dan skema arsitektur data di `docs/architecture.md`. |
| **Phase 2: Data Pipeline dan Query Engine** | Pertemuan 10 | Pertemuan 11 | Integrasi DuckDB/Polars backend, skrip ekstraksi data dan caching efisien siap dihubungkan ke Streamlit. |
| **Phase 3: Streamlit UI dan Staging Space** | Pertemuan 11 | Pertemuan 12 | Prototype dashboard live di HuggingFace Spaces (staging), pengujian interaktivitas widget dan chart Plotly. |
| **Final Release dan Presentasi** | Pertemuan 12 | Minggu 14 | Final deployment production, video demo 3–5 menit, penyelesaian laporan `README.md`. Presentasi tim bergiliran mulai Minggu 12/13, selesai paling lambat Minggu 14. |

---

## Persiapan GitHub

### 1. Fork Repositori Tugas (oleh satu anggota)

Salah satu anggota (ketua kelompok) melakukan fork repositori berikut ke akun GitHub-nya:

https://github.com/UMM-GURU/tugas2-abd-2026

1. Login ke GitHub dan buka repositori di atas.
2. Klik tombol **Fork** di pojok kanan atas.
3. Hasil fork akan berada di `https://github.com/USERNAME-KETUA/tugas2-abd-2026`.

### 2. Tambahkan Anggota Lain sebagai Collaborator

Pada repositori hasil fork, buka **Settings → Collaborators → Add people**, lalu undang akun GitHub anggota lain. Setiap anggota wajib menerima undangan tersebut agar dapat melakukan push.

### 3. Clone Repositori

Setiap anggota melakukan clone repositori hasil fork milik ketua:

```bash
git clone https://github.com/USERNAME-KETUA/tugas2-abd-2026.git
cd tugas2-abd-2026
```

### 4. Isi `identitas.md`

Isi nama, NIM, dan akun GitHub seluruh anggota pada file [`identitas.md`](identitas.md), lalu commit dan push sebagai commit pertama kelompok:

```bash
git add identitas.md
git commit -m "Isi identitas kelompok"
git push origin main
```

Kontribusi setiap anggota dinilai dari riwayat commit, jadi pastikan akun GitHub yang dicantumkan sama dengan akun yang digunakan untuk commit.

---

## Anggota Kelompok dan Peran

Identitas lengkap (nama, NIM, akun GitHub) dicantumkan di [`identitas.md`](identitas.md). Tabel berikut menjelaskan pembagian peran:

| No | Nama | Peran / Kontribusi Utama |
|:--:|------|--------------------------|
| 1 | Richa Cinta Sari | Lead Architect / Data Pipeline |
| 2 | Wulan Dharma Putri | Backend Query / DuckDB Engine |
| 3 | Selma Kadir Pelu | Frontend Streamlit / Visualisasi |

---

## Tautan Produk Data

- **Live Dashboard (HuggingFace Spaces):** `https://huggingface.co/spaces/[username_hf]/[nama_app]`
- **Video Demo (3–5 Menit):** `https://youtu.be/[video_id]` atau Google Drive Link

---

## Prasyarat dan Menjalankan Dashboard Secara Lokal

### 1. Menjalankan Langsung dengan Python (Lokal)
```bash
pip install -r requirements.txt
streamlit run app.py
```
Akses dashboard di browser melalui: `http://localhost:8501`

### 2. Menjalankan di Lingkungan Docker
```bash
docker build -t bigdata-dashboard .
docker run -p 8501:8501 bigdata-dashboard
```

---

## Struktur Folder Repositori

```text
.
├── .github/
│   └── workflows/
│       └── lint_check.yml       # Pemeriksaan otomatis GitHub Actions
├── data/
│   └── README.md                # Petunjuk pengunduhan dataset besar
├── docs/
│   └── architecture.md          # Dokumen Pitch & Arsitektur Data Product (Phase 1)
├── src/
│   └── queries.py               # Modul kueri DuckDB dan transformasi Polars
├── app.py                       # Skrip utama aplikasi Streamlit
├── Dockerfile                   # Konfigurasi container
├── identitas.md                 # Nama, NIM, dan akun GitHub anggota
├── requirements.txt             # Daftar pustaka Python
└── README.md                    # Laporan utama proyek tim
```

---

## Pernyataan Penggunaan AI (AI Disclosure Statement)

Wajib diisi oleh seluruh kelompok:
- **Apakah menggunakan AI (ChatGPT / Claude / GitHub Copilot / LLM lain)?** [Ya / Tidak]
- **Jika Ya, sebutkan alat yang digunakan:** [Sebutkan alat]
- **Komponen mana yang dibantu AI:** [Misal: saran kueri SQL window function, perbaikan CSS layout]
- **Komitmen Tim:** Seluruh anggota tim memahami sepenuhnya kode yang diserahkan dan bertanggung jawab penuh atas integritas serta fungsionalitas aplikasi saat evaluasi/presentasi.
