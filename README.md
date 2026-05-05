# n8n Leave Approval & Management Automation 🚀

Sistem ini dirancang untuk mendigitalisasi proses pengajuan cuti karyawan secara end-to-end menggunakan **n8n**. Workflow ini menghilangkan birokrasi manual dengan menggabungkan validasi sistemik dan keputusan manajerial dalam satu alur kerja yang terintegrasi[cite: 5].

## 🌟 Fitur Utama
*   **Automated Form Submission**: Pengumpulan data pengajuan (Email, Tanggal, Alasan) melalui n8n Form Trigger yang user-friendly[cite: 5].
*   **Smart Balance Validation**: Validasi saldo cuti secara real-time dari Google Sheets menggunakan skrip JavaScript (Luxon) untuk memastikan durasi pengajuan mencukupi[cite: 4, 5].
*   **Interactive Approval System**: Sistem persetujuan satu klik untuk manajer melalui email HTML interaktif yang terhubung dengan Webhook dinamis.
*   **Dynamic Database Sync**: Pembaruan otomatis pada master data saldo karyawan dan pencatatan audit log pengajuan (Pending, Approved, Rejected)[cite: 3, 4].

## 🏗️ Arsitektur Workflow
Project ini terdiri dari dua workflow utama yang saling terhubung:
1.  **Workflow Pengajuan**: Menangani input form, lookup database, kalkulasi durasi, dan pengiriman email persetujuan.
2.  **Approval Handler**: Webhook listener yang memproses keputusan manajer, mengupdate saldo di Google Sheets, dan mengirimkan notifikasi final ke karyawan[cite: 3].

## 🛠️ Tech Stack
*   **n8n**: Workflow Automation Engine[cite: 5].
*   **Google Sheets**: Sebagai Master Database & Audit Log[cite: 3, 4].
*   **Gmail API**: Media notifikasi dan approval interface[cite: 3].
*   **JavaScript (Luxon Library)**: Logika kalkulasi tanggal dan validasi saldo[cite: 5].

## 🚀 Cara Penggunaan
1.  Import file `Workflow Pengajuan.json` dan `Approval-Handler.json` ke instance n8n Anda[cite: 3, 4].
2.  Siapkan Google Sheets dengan tab `DB_Karyawan` dan `Log Pengajuan` sesuai struktur yang ada di dokumentasi[cite: 5].
3.  Konfigurasikan kredensial Google Sheets dan Gmail pada setiap node yang relevan[cite: 5].
4.  Pastikan URL pada tombol email di node "Email ke Manager" sudah mengarah ke Production URL Webhook instance n8n Anda[cite: 5].

---
*Project ini dikembangkan sebagai bagian dari modul Implementasi AI untuk Manajemen SDM di Nurul Fikri Academy.*
