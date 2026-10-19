# Sistem Timesheet & Billing Jam Kerja Proyek

Sistem pengelolaan jam kerja (*timesheet*) dan kalkulasi tagihan (*billing*) proyek untuk meningkatkan efisiensi pencatatan aktivitas tim serta transparansi pembiayaan proyek.

---

## 👤 Informasi Pengembang

* **Nama Lengkap:** I Komang Pradnya Wiryatama
* **Username GitHub:** [@omingpradnya](https://github.com/omingpradnya)
* **Organisasi:** [Central-Saga](https://github.com/Central-Saga)

---

## 🔗 Link Repository

* **Repository GitHub:** [https://github.com/Central-Saga/sistem-timesheet-billing](https://github.com/Central-Saga/sistem-timesheet-billing)

---

## 🛠️ Tech Stack

### **Backend & API**
* **Laravel** – Framework PHP untuk membangun RESTful API, otentikasi, dan logika bisnis.

### **Frontend**
* **Next.js** – Framework React untuk membangun antarmuka pengguna (UI) yang interaktif, cepat, dan responsif.

### **Database & Caching**
* **PostgreSQL** – Relational Database Management System (RDBMS) utama untuk penyimpanan data terstruktur.
* **Redis** – *In-memory data store* untuk manajemen *session*, *queue*, dan *caching*.

### **DevOps & Containerization**
* **Podman** – *Engine containerization* untuk mengelola lingkungan isolasi aplikasi secara aman dan efisien.

---

## ✨ Fitur Utama

1. **Pencatatan Jam Kerja (Timesheet Tracking)**
   * Input dan *monitoring* durasi pengerjaan tugas atau proyek harian anggota tim.
2. **Kalkulasi Billing Otomatis**
   * Perhitungan otomatis total tagihan berdasarkan *hourly rate*, peran, atau jenis pekerjaan yang diselesaikan.
3. **Manajemen Proyek & Klien**
   * Pengelolaan data proyek, pemantauan status pengerjaan, dan alokasi tim.
4. **Laporan & Analytics**
   * Rekapitulasi jam kerja serta visualisasi ringkasan tagihan proyek untuk pelaporan ke klien.

---

## 🚀 Panduan Penggunaan Singkat

### Prerequisites
* Podman / Container runtime
* Node.js & npm / yarn
* PHP 8.x & Composer

### Menjalankan Container (Development Environment)
```bash
# Menjalankan database PostgreSQL dan Redis menggunakan Podman
podman compose up -d
```

---

## 📜 Lisensi & Penggunaan
Dikembangkan oleh **I Komang Pradnya Wiryatama** di bawah organisasi **Central-Saga**. Hak cipta dilindungi.