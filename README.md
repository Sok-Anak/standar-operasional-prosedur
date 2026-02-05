# STANDAR OPERASIONAL PROSEDUR (SOP)
## PERAKITAN, KALIBRASI, DAN OPERASI SISTEM AIoT Sok!Anak

---

### **BAB I: PENDAHULUAN**
Dokumen Standar Operasional Prosedur (SOP) ini disusun untuk menetapkan standar baku dalam proses perakitan, pengujian, kalibrasi, dan operasional sistem Sok!Anak. Tujuan penerapan SOP ini adalah untuk menjamin konsistensi output, memenuhi aspek kualitas produk, keamanan operasional, dan efisiensi kerja pada seluruh tahap pengembangan dan implementasi sistem di lapangan.

### **BAB II: DESKRIPSI SISTEM DAN PERSYARATAN**
*   **Nama Sistem:** Sok!Anak – Sistem Observasi Kesehatan Anak Berbasis Internet of Things dan Kecerdasan Buatan.
*   **Tim Pengembang:** Tim Riset AIoT Sok!Anak, Telkom University.
*   **Kontak Resmi:** sokanak@duck.com
*   **Arsitektur Sistem:**
    *   **Perangkat Keras (Hardware):** Modul Sensor Load Cell (HX711), Sensor Ultrasonik, Mikrokontroler ESP32, Single-Board Computer Raspberry Pi 5.
    *   **Perangkat Lunak (Software):** Web Dashboard, Sistem Operasi, Driver, dan Kode Program (tersedia di repositori GitHub).
*   **Dokumentasi Pendukung:** Tautan lengkap tersedia pada bagian lampiran dan repositori proyek.

### **BAB III: PROSEDUR PERSIAPAN MATERIAL DAN LINGKUNGAN KERJA**
1.  Pastikan seluruh komponen utama dan pendukung telah tersedia.
    *   Sensor Load Cell dan Modul HX711.
    *   Sensor Ultrasonik (HC-SR04 atau sejenis).
    *   Raspberry Pi 5 dan Modul ESP32.
    *   Kabel jumper, konektor, serta struktur mekanik pendukung (casing, rak).
2.  Lakukan pemeriksaan visual dan fungsional sederhana terhadap setiap komponen untuk memastikan tidak ada cacat fisik atau kerusakan.
3.  Siapkan lingkungan pengembangan dengan menginstal Sistem Operasi (OS) Raspberry Pi OS Lite atau Debian, driver yang diperlukan, dan clone repository GitHub proyek Sok!Anak.

### **BAB IV: PROSEDUR PERAKITAN DAN KALIBRASI SISTEM**
#### **A. Perakitan dan Kalibrasi Modul Timbangan Digital**
1.  Pasang load cell secara tepat pada struktur timbangan, pastikan tidak ada gaya samping (side load) yang mengganggu.
2.  Hubungkan modul load cell (HX711) ke mikrokontroler ESP32 sesuai dengan diagram pengkabelan (*wiring diagram*) yang telah ditentukan.
3.  **Proses Kalibrasi:**
    *   Jalankan skrip kalibrasi yang tersedia di repositori.
    *   Ikuti prosedur kalibrasi bertahap menggunakan *weight standard* yang telah diketahui massanya.
    *   Simpan parameter kalibrasi (scale factor, offset) ke dalam memori ESP32.

#### **B. Perakitan dan Kalibrasi Modul Pengukur Tinggi Badan**
1. Pasang sensor ultrasonik pada posisi vertikal yang tetap dan stabil, dengan bidang pengukuran bebas halangan.
2. Hubungkan sensor ultrasonik ke ESP32 sesuai diagram pengkabelan.
3. Uji akurasi pengukuran jarak sensor terhadap objek referensi pada berbagai jarak. Lakukan koreksi *offset* jika diperlukan.

> **Dokumentasi Teknis Detail:**
> *   **Modul Timbangan:** [Dokumentasi Lengkap Perakitan & Kode](https://github.com/Sok-Anak/sok-anak-hw/blob/main/hx711/README.md)
> *   **Modul Tinggi Badan:** [Dokumentasi Lengkap Perakitan & Kode](https://github.com/Sok-Anak/sok-anak-hw/blob/main/ultrasonic/README.md)

### **BAB V: PROSEDUR PENGUJIAN SISTEM DAN KONTROL KUALITAS**
#### **A. Pengujian Perangkat Keras dan Komunikasi (Hardware & Firmware)**
| Fitur/Aspek yang Diuji       | Modul Timbangan | Modul Pengukur Tinggi | Status/Keterangan       |
|------------------------------|-----------------|------------------------|-------------------------|
| Kebenaran Wiring             | Ya              | Ya                     |                         |
| Akurasi dan Presisi Data     | Ya              | Ya                     | Perlu optimasi kalibrasi|
| Stabilitas Koneksi Wi-Fi     | Ya              | Ya                     |                         |
| Penerimaan Data oleh Broker MQTT | Ya           | Ya                     |                         |
| **Kesimpulan Pengujian:** | **Fungsional** | **Fungsional**         | Siap untuk integrasi    |

#### **B. Pengujian Perangkat Lunak dan Antarmuka (Web Dashboard)**
| Fitur/Modul Aplikasi Web     | Desktop Browser | Mobile Browser | Keterangan              |
|------------------------------|-----------------|----------------|-------------------------|
| Filter dan Pencarian Data    | Ya              | Ya             |                         |
| Input Data Pengukuran Manual | Ya              | Ya             |                         |
| Analisis Status Gizi (Z-Score) | Ya            | Ya             |                         |
| Fitur Konsultasi Berbasis AI | Ya              | Ya             |                         |
| **Kesimpulan Pengujian:** | **Responsif**   | **Responsif**  | Antarmuka berjalan optimal |

### **BAB VI: PROSEDUR OPERASI DAN PENANGANAN MASALAH**
1.  Lakukan pengujian end-to-end dengan mengintegrasikan seluruh modul perangkat keras dengan web dashboard.
2.  Semua data pengujian, parameter kalibrasi, dan kejadian (*events*) harus dicatat dalam log sistem untuk keperluan audit dan pemecahan masalah.
3.  **Eskalasi Error/Gangguan:** Jika ditemukan ketidaksesuaian, bug, atau kegagalan sistem:
    *   Laporkan secara detail melalui GitHub Issue pada repository terkait.
    *   Untuk pertanyaan operasional, hubungi: **sokanak@duck.com**.

### **BAB VII: PROSEDUR ADMINISTRASI DAN DOKUMENTASI**
*   Seluruh kode sumber dikelola secara terpusat di **Repository GitHub Sok!Anak**.
*   Dokumentasi pengguna akhir tersedia dalam format PDF dan video tutorial di kanal YouTube resmi.
*   Log kesalahan, laporan pengujian, dan dokumen SOP ini akan ditinjau dan diperbarui secara berkala.

### **BAB VIII: PROSEDUR KESELAMATAN DAN KESEHATAN KERJA (K3)**
1.  Pastikan lingkungan kerja bebas dari bahaya sengatan listrik. Gunakan power supply yang sesuai dan terjamin keamanannya.
2.  Gunakan APD yang relevan (seperti sarung tangan anti-static) selama proses perakitan dan perbaikan jika diperlukan.
3.  Seluruh aktivitas harus mengikuti pedoman Keselamatan dan Kesehatan Kerja (K3) yang berlaku.

### **BAB IX: PENUTUP DAN PENINJAUAN**
SOP ini merupakan dokumen hidup yang akan dievaluasi dan direvisi secara periodik menyesuaikan perkembangan sistem, umpan balik pengguna, dan temuan di lapangan.

**Tim Penanggung Jawab:**
*   **Penyusun:** Tim Teknis AIoT Sok!Anak.
*   **Peninjau:** Praktisi Kesehatan (Bidan, Ahli Gizi), Dosen Pembimbing Teknis.

**CATATAN DAN REFERENSI:**
*   Untuk panduan teknis paling mutakhir, selalu merujuk pada dokumentasi di [Repository GitHub Sok!Anak](https://github.com/sok-anak).
*   Umpan balik dari pengguna dapat disampaikan melalui [Formulir Umpan Balik](https://cloud.sokanak.id/apps/forms/s/wrLyjEq2TB9nd7pw8RwmkgJZ) yang telah disediakan.

---
**Salam Inovasi,**
**Tim AIoT Sok!Anak – Telkom University**
*Berkontribusi untuk Mewujudkan Generasi Sehat Bebas Stunting.*