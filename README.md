# n8n Leave Approval & Management Automation 🚀

Sistem ini dirancang untuk mendigitalisasi proses pengajuan cuti karyawan secara end-to-end menggunakan **n8n**. Workflow ini menghilangkan birokrasi manual dengan menggabungkan validasi sistemik dan keputusan manajerial dalam satu alur kerja yang terintegrasi.

## 🌟 Fitur Utama
*   **Automated Form Submission**: Pengumpulan data pengajuan (Email, Tanggal, Alasan) melalui n8n Form Trigger yang user-friendly.
*   **Smart Balance Validation**: Validasi saldo cuti secara real-time dari Google Sheets menggunakan skrip JavaScript (Luxon) untuk memastikan durasi pengajuan mencukupi.
*   **Interactive Approval System**: Sistem persetujuan satu klik untuk manajer melalui email HTML interaktif yang terhubung dengan Webhook dinamis.
*   **Dynamic Database Sync**: Pembaruan otomatis pada master data saldo karyawan dan pencatatan audit log pengajuan (Pending, Approved, Rejected).

## 🏗️ Arsitektur Workflow
Project ini terdiri dari dua workflow utama yang saling terhubung:
1.  **Workflow Pengajuan**: Menangani input form, lookup database, kalkulasi durasi, dan pengiriman email persetujuan.
2.  **Approval Handler**: Webhook listener yang memproses keputusan manajer, mengupdate saldo di Google Sheets, dan mengirimkan notifikasi final ke karyawan.

## 🛠️ Tech Stack
*   **n8n**: Workflow Automation Engine.
*   **Google Sheets**: Sebagai Master Database & Audit Log.
*   **Gmail API**: Media notifikasi dan approval interface.
*   **JavaScript (Luxon Library)**: Logika kalkulasi tanggal dan validasi saldo.

## 🚀 Cara Penggunaan
1.  Import file `Workflow Pengajuan.json` dan `Approval-Handler.json` ke instance n8n Anda.
2.  Siapkan Google Sheets dengan tab `DB_Karyawan` dan `Log Pengajuan` sesuai struktur kolom yang ditentukan.
3.  Konfigurasikan kredensial Google Sheets dan Gmail pada setiap node yang relevan.
4.  Pastikan URL pada tombol email di node "Email ke Manager" sudah mengarah ke Production URL Webhook instance n8n Anda.

---
