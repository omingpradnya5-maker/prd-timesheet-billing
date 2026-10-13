# Product Requirement Document (PRD)
## Sistem Timesheet & Billing Jam Kerja Proyek

---

## 📌 1. Informasi Dokumen
* **Nama Proyek:** Sistem Timesheet & Billing Jam Kerja Proyek
* **Pengembang Utama:** I Komang Pradnya Wiryatama ([@omingpradnya](https://github.com/omingpradnya))
* **Organisasi:** Central-Saga
* **Status Dokumen:** Draft / Initial Version
* **Tanggal:** 13 Oktober 2026

---

## 🎯 2. Ringkasan Eksekutif & Tujuan (Overview & Goals)

### 2.1 Ringkasan
**Sistem Timesheet & Billing Jam Kerja Proyek** adalah platform web terintegrasi yang dirancang untuk mempermudah pencatatan waktu kerja (*timesheet*) para anggota tim/freelancer serta secara otomatis mengkalkulasi total biaya tagihan (*billing*) proyek berdasarkan tarif per jam (*hourly rate*) atau tarif tetap (*fixed rate*).

### 2.2 Masalah yang Diselesaikan (Problem Statement)
* **Pencatatan Manual:** Penggunaan spreadsheet manual rentan terhadap kesalahan (*human error*) dan manipulasi data jam kerja.
* **Kalkulasi Billing Rumit:** Proses penghitungan tagihan klien yang membutuhkan waktu lama karena harus mencocokkan *hourly rate* tim yang berbeda-beda.
* **Kurangnya Transparansi:** Klien dan manajer proyek sulit melihat bukti *work breakdown* secara *real-time*.

### 2.3 Tujuan Utama (Objectives)
* Meningkatkan akurasi dan transparansi pencatatan jam kerja tim.
* Otomatisasi pembuatan draf tagihan/invoicing proyek.
* Menyediakan dasbor analitik untuk efisiensi alokasi sumber daya manusia dan pemantauan anggaran proyek.

---

## 👥 3. Pengguna Target & Peran (User Personas & Roles)

1. **Admin / Super Admin**
   * Mengelola akun pengguna, hak akses, master data klien, dan konfigurasi sistem.
2. **Project Manager (PM)**
   * Membuat dan mengelola proyek, mengalokasikan anggota tim, menetapkan *rate*, serta menyetujui (*approve/reject*) *timesheet*.
3. **Team Member / Developer**
   * Mengisi *timesheet* harian/mingguan berdasarkan proyek dan tugas yang dikerjakan.
4. **Client (Viewer)** *(Opsional/Fase Lanjutan)*
   * Melihat laporan jam kerja dan rekapitulasi billing proyek yang sedang berjalan secara transparan.

---

## 🛠️ 4. Arsitektur & Tech Stack

* **Frontend:** Next.js (React Framework, Server-Side Rendering & Client Components)
* **Backend / API:** Laravel (RESTful API, Auth, Business Logic)
* **Database:** PostgreSQL (Relational Database)
* **Caching & Queue:** Redis (Session Store, Task Queue untuk Kalkulasi & Export PDF)
* **DevOps & Infrastructure:** Podman (Containerization untuk kestabilan *environment*)

---

## 📋 5. Spesifikasi Fitur Utama (Functional Requirements)

### 5.1 Manajemen Pengguna & Proyek
* **Autentikasi & Otorisasi:** Login/Logout, Reset Password, Role-Based Access Control (RBAC).
* **Manajemen Klien & Proyek:** CRUD data klien, nama proyek, tenggat waktu, dan alokasi anggaran (*budget*).
* **Alokasi Tim & Rate:** Menentukan *member* pada proyek beserta *hourly rate* atau *role rate* masing-masing.

### 5.2 Pencatatan Jam Kerja (Timesheet)
* **Input Timesheet Manual:** Menambahkan entri waktu (Tanggal, Proyek, Task Name, Durasi Jam/Menit, Catatan Pekerjaan).
* **Timer Live (Stopwatch):** Fitur *start/stop timer* langsung dari dasbor untuk mencatat jam kerja secara otomatis.
* **Persetujuan (Approval Workflow):**
  * Status timesheet: `Draft` ➔ `Submitted` ➔ `Approved` / `Rejected`.
  * PM dapat meninjau dan memberi catatan pada entri yang ditolak.

### 5.3 Kalkulasi Billing & Tagihan
* **Kalkulator Tagihan Otomatis:** Sistem secara otomatis menghitung `Total Tagihan = Sum(Jam Kerja Approved × Hourly Rate)`.
* **Generator Invoicing:** Memilih rentang tanggal dan proyek untuk menghasilkan draf tagihan (*invoice*).
* **Status Tagihan:** `Unbilled`, `Invoiced`, `Paid`.

### 5.4 Laporan & Analytics
* **Dasbor Ringkasan:** Grafik total jam kerja per proyek, total estimasi tagihan, dan efisiensi tim.
* **Ekspor Laporan:** Ekspor data *timesheet* dan *billing* ke format PDF dan Excel (XLSX).

---

## ⚡ 6. Kebutuhan Non-Fungsional (Non-Functional Requirements)

* **Performa:** Respon API Laravel < 300ms untuk query standar; pencarian data dengan integrasi Redis Caching.
* **Keamanan:** Encrypted JWT/Sanctum Tokens, HTTPS enforced, perlindungan dari SQL Injection & CSRF.
* **Skalabilitas:** Containerization menggunakan **Podman** agar pengerjaan *deployment* dan *scaling* layanan konsisten.
* **Antarmuka (UI/UX):** Responsive Design (Mobile & Desktop friendly) menggunakan Next.js & Tailwind CSS.

---

## 🏁 7. Alur Kerja Aplikasi (Workflow Overview)

```
[Member Kerja] ──> [Input/Start Timer Timesheet] ──> [Submit Timesheet]
                                                              │
                                                              ▼
[PM / Admin]   <── [Review Timesheet Entry] ◄────────── [Persetujuan]
      │
      ├─► Disetujui (Approved) ──> [Kalkulasi Billing Auto] ──> [Generate Invoice]
      │
      └─► Ditolak (Rejected)  ──> [Kembali ke Member untuk Direvisi]
```

---

## 📅 8. Rencana Pengembangan (Roadmap)

* **Fase 1 (MVP):** Auth System, CRUD Proyek/Tim, Input Timesheet Manual, Approval Sederhana, Kalkulasi Billing Dasar.
* **Fase 2:** Live Timer Feature, Generator Invoice PDF, Redis Queue implementation.
* **Fase 3:** Dashboard Analytics Visual, Role Client Viewer, Ekspor Laporan Excel/CSV.