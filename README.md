# 📋 prd-timesheet-billing

**Product Requirement Document — Sistem Timesheet & Billing Jam Kerja Proyek**

> Dokumen kebutuhan produk untuk sistem pencatatan jam kerja (*timesheet*) per proyek,
> persetujuan (*approval*), dan pembuatan tagihan (*billing/invoice*) otomatis berdasarkan rate card.

### 👤 Informasi Pengembang

| | |
|---|---|
| **Nama** | I Komang Pradnya Wiryatama |
| **GitHub** | [@omingpradnya5-maker](https://github.com/omingpradnya5-maker) |
| **Komunitas** | [Central Saga](https://github.com/Central-Saga) |
| **Tanggal** | Oktober 2026 |

---

### 📂 Daftar Dokumen

| Dokumen | Isi | Kapan dipakai |
|---|---|---|
| [**PRD-Timesheet-Billing-Lengkap.md**](./PRD-Timesheet-Billing-Lengkap.md) | PRD lengkap v1.0 — OKR, persona, 7 modul fitur + acceptance criteria, alur, model data 11 entitas, 9 NFR, Definition of Done, milestone 8 minggu, risiko | Rujukan utama saat development & review stakeholder |
| [**product_requirement_document_prd.md**](./product_requirement_document_prd.md) | PRD ringkas versi awal (13 Okt 2026) — ringkasan eksekutif, problem statement, tujuan | Rujukan singkat / overview |
| [**readme_md.md**](./readme_md.md) | Deskripsi produk, tech stack (Laravel, Next.js, PostgreSQL, Redis, Podman), daftar fitur utama | Gambaran umum produk |

---

### 🎯 Tech Stack (rencana implementasi)

- **Backend & API:** Laravel (PHP) — RESTful API, autentikasi, logika bisnis
- **Frontend:** Next.js (React/TypeScript) — antarmuka pengguna
- **Database & Caching:** PostgreSQL, Redis
- **DevOps:** Podman (containerization)

### ✅ Lingkup MVP

1. Manajemen klien & proyek + budget jam
2. Rate card (tarif/jam, multiplier lembur & hari libur)
3. Timesheet harian/mingguan — timer & input manual
4. Workflow approval: Staf → PM → Finance (reject dengan catatan)
5. Generator invoice otomatis dari jam yang disetujui (diskon, PPN, nomor urut, PDF)
6. Laporan utilisasi/jam billable + export CSV
7. RBAC 5 peran + audit log + notifikasi email

### 🔗 Link Terkait

- **Aplikasi (rencana):** https://github.com/Central-Saga/sistem-timesheet-billing
- **Portfolio pengembang:** https://omingpradnya5-maker.github.io/portfolio/
