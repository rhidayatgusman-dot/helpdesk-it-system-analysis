# Software Requirements Specification (SRS)

## Sistem Helpdesk IT Perusahaan

**Versi:** 1.0  
**Status:** Draft – Memerlukan Validasi Stakeholder  
**Tahap:** Requirements Analysis  
**Dokumen Acuan:** Business Requirements Document (BRD) v1.0

---

## 1. Pendahuluan

### 1.1 Tujuan Dokumen

Dokumen Software Requirements Specification (SRS) menjelaskan kebutuhan sistem secara terperinci sebagai dasar perancangan, pengembangan, dan pengujian Sistem Helpdesk IT Perusahaan.

Dokumen ini bertujuan untuk:

1. Menjabarkan kebutuhan bisnis menjadi kebutuhan fungsional dan nonfungsional.
2. Menentukan fungsi yang harus tersedia dalam sistem.
3. Menjelaskan hak akses setiap jenis pengguna.
4. Mendefinisikan aturan dan alur kerja sistem.
5. Menentukan kebutuhan data dan integrasi.
6. Menjadi acuan dalam penyusunan desain sistem dan pengujian.

### 1.2 Ruang Lingkup Sistem

Sistem Helpdesk IT Perusahaan merupakan aplikasi berbasis web untuk mengelola laporan kendala teknologi informasi di lingkungan perusahaan.

Sistem mendukung proses:

- Autentikasi dan pengelolaan hak akses.
- Pelaporan kendala IT oleh karyawan.
- Pengelolaan kategori laporan.
- Klasifikasi dampak dan urgensi.
- Rekomendasi prioritas dan penugasan staf IT.
- Konfirmasi penugasan oleh staf IT.
- Penanganan dan pemantauan status tiket.
- Pencatatan riwayat aktivitas.
- Konfirmasi penyelesaian oleh karyawan.
- Persetujuan penutupan tiket kritis oleh Manajer IT.
- Monitoring dan laporan evaluasi layanan.

### 1.3 Definisi dan Istilah

| Istilah | Definisi |
|---|---|
| Helpdesk | Layanan untuk menerima dan menangani kendala IT. |
| Ticket | Catatan laporan kendala IT yang dibuat pengguna. |
| Reporter | Pengguna yang membuat laporan kendala. |
| Impact | Tingkat pengaruh kendala terhadap operasional. |
| Urgency | Tingkat kebutuhan penanganan berdasarkan waktu. |
| Priority | Tingkat prioritas penanganan tiket. |
| Assignment | Proses penugasan tiket kepada staf IT. |
| Escalation | Proses meneruskan kendala kepada pihak yang memiliki kewenangan lebih tinggi. |
| Ticket History | Catatan aktivitas dan perubahan pada tiket. |
| SLA | Target waktu layanan yang disepakati. |

### 1.4 Referensi

Dokumen ini disusun berdasarkan:

1. Problem Statement.
2. Business Process Analysis.
3. Stakeholder Analysis.
4. Business Requirements Document (BRD) v1.0.

---

## 2. Deskripsi Umum Sistem

### 2.1 Perspektif Produk

Sistem merupakan aplikasi berbasis web yang digunakan secara internal oleh karyawan, staf IT, Manajer IT, dan administrator.

Sistem berfungsi sebagai pusat pengelolaan laporan kendala IT, mulai dari laporan dibuat hingga tiket dinyatakan selesai.

### 2.2 Jenis Pengguna

Sistem memiliki empat jenis pengguna.

**1. Administrator**

Bertanggung jawab mengelola administrasi sistem, meliputi:

- Mengelola akun pengguna.
- Mengelola role dan hak akses.
- Mengelola departemen.
- Mengelola kategori kendala IT.
- Memastikan data master tersedia dan sesuai.

**2. Karyawan**

Bertindak sebagai pelapor kendala IT, dengan kemampuan:

- Membuat laporan kendala.
- Mengunggah lampiran.
- Melihat nomor dan status tiket.
- Melihat riwayat laporan miliknya.
- Memberikan konfirmasi penyelesaian.

**3. Staf IT**

Bertanggung jawab melakukan penanganan kendala, dengan kemampuan:

- Melihat laporan yang masuk sesuai kewenangan.
- Memeriksa rekomendasi prioritas.
- Memeriksa dan mengonfirmasi penugasan.
- Menolak rekomendasi penugasan dengan alasan.
- Memperbarui status tiket.
- Menambahkan catatan penanganan.
- Mengajukan penyelesaian tiket.

**4. Manajer IT**

Bertanggung jawab melakukan pengawasan layanan IT, dengan kemampuan:

- Melihat dashboard seluruh tiket.
- Memantau tiket berdasarkan status dan prioritas.
- Memantau pekerjaan staf IT.
- Menerima informasi tiket kritis.
- Menyetujui atau menolak penutupan tiket kritis.
- Melihat laporan evaluasi layanan.

### 2.3 Lingkungan Operasional

Lingkungan operasional yang direncanakan:

- Aplikasi berbasis web.
- Dapat diakses melalui browser modern.
- Server aplikasi mendukung PHP dan framework Laravel.
- Database menggunakan MySQL.
- Sistem dapat digunakan melalui jaringan yang tersedia bagi pengguna perusahaan.

Detail infrastruktur produksi masih memerlukan penetapan lebih lanjut.

### 2.4 Batasan Sistem

1. Sistem berfokus pada pengelolaan kendala IT.
2. Pengguna harus memiliki akun yang terdaftar.
3. Hak akses ditentukan berdasarkan role.
4. Rekomendasi prioritas tidak menggantikan pemeriksaan staf IT.
5. Rekomendasi penugasan harus dikonfirmasi oleh staf IT.
6. Tiket kritis memerlukan persetujuan Manajer IT sebelum ditutup.
7. Sistem tidak menggunakan AI sebagai pengambil keputusan penugasan otomatis.
8. Integrasi WhatsApp dan sistem eksternal belum termasuk ruang lingkup awal.

### 2.5 Asumsi dan Ketergantungan

1. Perusahaan memiliki tim IT internal.
2. Pengguna memiliki akun aktif.
3. Tersedia koneksi jaringan untuk mengakses aplikasi.
4. Data departemen, kategori, dan pengguna dikelola administrator.
5. Kebijakan prioritas dan penutupan tiket mendapatkan persetujuan stakeholder.
6. Infrastruktur server dan database tersedia.

---

## 3. Kebutuhan Fungsional

Kebutuhan fungsional menjelaskan fungsi yang wajib disediakan sistem.

### 3.1 Modul Autentikasi dan Hak Akses

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-001 | Sistem menyediakan halaman login. | Semua pengguna | Tinggi |
| FR-002 | Sistem memvalidasi identitas dan kata sandi pengguna. | Semua pengguna | Tinggi |
| FR-003 | Sistem menampilkan fitur berdasarkan role pengguna. | Semua pengguna | Tinggi |
| FR-004 | Sistem menyediakan fungsi logout. | Semua pengguna | Tinggi |
| FR-005 | Administrator dapat mengelola akun pengguna. | Administrator | Tinggi |
| FR-006 | Administrator dapat mengelola role dan departemen. | Administrator | Tinggi |

### 3.2 Modul Pelaporan Tiket

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-007 | Karyawan dapat membuat laporan kendala IT. | Karyawan | Tinggi |
| FR-008 | Sistem memvalidasi kelengkapan data laporan. | Sistem | Tinggi |
| FR-009 | Sistem menghasilkan nomor tiket unik. | Sistem | Tinggi |
| FR-010 | Karyawan dapat memilih kategori kendala. | Karyawan | Tinggi |
| FR-011 | Karyawan dapat mengisi judul dan deskripsi kendala. | Karyawan | Tinggi |
| FR-012 | Karyawan dapat mengisi dampak dan urgensi kendala. | Karyawan | Tinggi |
| FR-013 | Karyawan dapat mengunggah lampiran laporan. | Karyawan | Sedang |
| FR-014 | Karyawan dapat melihat daftar tiket miliknya. | Karyawan | Tinggi |
| FR-015 | Karyawan dapat melihat detail dan riwayat tiket miliknya. | Karyawan | Tinggi |

### 3.3 Modul Prioritas dan Penugasan

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-016 | Sistem memberikan rekomendasi prioritas berdasarkan dampak dan urgensi. | Sistem | Tinggi |
| FR-017 | Staf IT dapat memeriksa rekomendasi prioritas. | Staf IT | Tinggi |
| FR-018 | Sistem menyediakan rekomendasi penugasan staf IT. | Sistem | Tinggi |
| FR-019 | Staf IT dapat mengonfirmasi rekomendasi penugasan. | Staf IT | Tinggi |
| FR-020 | Staf IT dapat menolak rekomendasi penugasan dengan alasan. | Staf IT | Tinggi |
| FR-021 | Sistem mencatat hasil konfirmasi atau penolakan penugasan. | Sistem | Tinggi |

### 3.4 Modul Penanganan Tiket

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-022 | Staf IT dapat melihat tiket yang menjadi tanggung jawabnya. | Staf IT | Tinggi |
| FR-023 | Staf IT dapat memperbarui status tiket. | Staf IT | Tinggi |
| FR-024 | Staf IT dapat menambahkan catatan penanganan. | Staf IT | Tinggi |
| FR-025 | Sistem mencatat setiap perubahan status tiket. | Sistem | Tinggi |
| FR-026 | Sistem menyimpan riwayat aktivitas tiket. | Sistem | Tinggi |
| FR-027 | Staf IT dapat mengajukan tiket untuk konfirmasi penyelesaian. | Staf IT | Tinggi |

### 3.5 Modul Konfirmasi dan Penutupan Tiket

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-028 | Karyawan dapat mengonfirmasi hasil penyelesaian tiket. | Karyawan | Tinggi |
| FR-029 | Sistem mencatat hasil konfirmasi karyawan. | Sistem | Tinggi |
| FR-030 | Sistem meneruskan tiket kritis untuk persetujuan Manajer IT. | Sistem | Tinggi |
| FR-031 | Manajer IT dapat menyetujui penutupan tiket kritis. | Manajer IT | Tinggi |
| FR-032 | Manajer IT dapat menolak penutupan tiket dengan alasan. | Manajer IT | Tinggi |
| FR-033 | Sistem dapat menutup tiket nonkritis secara otomatis sesuai kebijakan yang disetujui. | Sistem | Sedang |
| FR-034 | Sistem mencegah penutupan otomatis tiket kritis tanpa persetujuan Manajer IT. | Sistem | Tinggi |

### 3.6 Modul Monitoring dan Laporan

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-035 | Manajer IT dapat melihat ringkasan jumlah tiket. | Manajer IT | Tinggi |
| FR-036 | Manajer IT dapat melihat tiket berdasarkan status. | Manajer IT | Tinggi |
| FR-037 | Manajer IT dapat melihat tiket berdasarkan prioritas. | Manajer IT | Tinggi |
| FR-038 | Manajer IT dapat memantau tiket kritis. | Manajer IT | Tinggi |
| FR-039 | Sistem menyediakan laporan berdasarkan periode. | Manajer IT | Sedang |
| FR-040 | Sistem menyediakan laporan berdasarkan kategori dan status. | Manajer IT | Sedang |
| FR-041 | Sistem menyediakan informasi waktu respons dan penyelesaian tiket. | Manajer IT | Sedang |

### 3.7 Modul Notifikasi

| ID | Kebutuhan | Aktor | Prioritas |
|---|---|---|---|
| FR-042 | Sistem memberikan notifikasi ketika status tiket berubah. | Sistem | Sedang |
| FR-043 | Sistem memberikan pemberitahuan kepada Manajer IT mengenai tiket kritis. | Sistem | Tinggi |
| FR-044 | Sistem memberikan pemberitahuan ketika tiket membutuhkan konfirmasi atau persetujuan. | Sistem | Sedang |

Notifikasi pada versi awal direncanakan tersedia di dalam aplikasi. Integrasi email atau WhatsApp belum termasuk ruang lingkup awal.

---

## 4. Kebutuhan Nonfungsional

Kebutuhan nonfungsional menjelaskan standar kualitas dan batasan operasional sistem.

| ID | Kategori | Kebutuhan |
|---|---|---|
| NFR-001 | Keamanan | Kata sandi pengguna harus disimpan menggunakan metode hashing yang aman. |
| NFR-002 | Keamanan | Sistem harus menerapkan autentikasi sebelum pengguna mengakses fitur internal. |
| NFR-003 | Keamanan | Sistem harus menerapkan pembatasan akses berdasarkan role. |
| NFR-004 | Keamanan | Pengguna tidak boleh mengakses tiket di luar kewenangannya. |
| NFR-005 | Keamanan | Akses terhadap lampiran harus mengikuti hak akses tiket terkait. |
| NFR-006 | Integritas Data | Nomor tiket harus unik dan tidak boleh digunakan kembali. |
| NFR-007 | Integritas Data | Setiap perubahan penting harus dicatat dengan waktu dan identitas pengguna atau proses sistem. |
| NFR-008 | Kinerja | Halaman utama dan daftar tiket ditargetkan dapat dimuat dalam waktu maksimal 3 detik pada kondisi pengujian normal. |
| NFR-009 | Kinerja | Sistem harus mampu memproses beberapa pengguna secara bersamaan sesuai kapasitas infrastruktur. |
| NFR-010 | Ketersediaan | Sistem dirancang dapat diakses selama jam operasional perusahaan, bergantung pada ketersediaan infrastruktur. |
| NFR-011 | Kompatibilitas | Sistem dapat digunakan melalui browser modern seperti Chrome, Edge, dan Firefox. |
| NFR-012 | Usability | Formulir pelaporan harus memiliki label dan validasi yang mudah dipahami. |
| NFR-013 | Maintainability | Struktur aplikasi harus modular agar mudah dikembangkan dan dipelihara. |
| NFR-014 | Backup | Database harus memiliki mekanisme pencadangan dan pemulihan. |
| NFR-015 | Auditability | Riwayat aktivitas tiket tidak boleh diubah oleh pengguna biasa. |

Catatan: target waktu respons 3 detik merupakan target awal untuk pengujian, bukan SLA produksi yang telah disepakati. Target ini perlu dievaluasi berdasarkan infrastruktur dan beban pengguna.

---

## 5. Matriks Hak Akses Pengguna

Keterangan: ✓ = Diizinkan, — = Tidak diizinkan.

| Fitur | Admin | Karyawan | Staf IT | Manajer IT |
|---|:---:|:---:|:---:|:---:|
| Login dan logout | ✓ | ✓ | ✓ | ✓ |
| Kelola akun | ✓ | — | — | — |
| Kelola departemen | ✓ | — | — | — |
| Kelola kategori | ✓ | — | — | — |
| Membuat tiket | — | ✓ | — | — |
| Melihat tiket milik sendiri | — | ✓ | — | — |
| Melihat tiket penugasan | — | — | ✓ | ✓ |
| Mengonfirmasi penugasan | — | — | ✓ | — |
| Memperbarui penanganan | — | — | ✓ | — |
| Konfirmasi penyelesaian | — | ✓ | — | — |
| Monitoring seluruh tiket | — | — | Sesuai kewenangan | ✓ |
| Persetujuan tiket kritis | — | — | — | ✓ |
| Melihat laporan evaluasi | — | — | — | ✓ |

Hak akses detail dapat disesuaikan melalui kebijakan perusahaan. Administrator tidak otomatis memiliki kewenangan untuk mengubah hasil penanganan tiket.

---

## 6. Aturan dan Logika Sistem

### 6.1 Matriks Rekomendasi Prioritas

Sistem memberikan rekomendasi prioritas berdasarkan kombinasi dampak dan urgensi.

| Dampak | Urgensi | Rekomendasi Prioritas |
|---|---|---|
| Tinggi | Tinggi | Kritis |
| Tinggi | Rendah | Tinggi |
| Rendah | Tinggi | Sedang |
| Rendah | Rendah | Rendah |

Rekomendasi tersebut dapat diperiksa oleh staf IT. Matriks ini merupakan rancangan awal dan perlu divalidasi oleh stakeholder.

### 6.2 Status Tiket

| Status | Penjelasan |
|---|---|
| Baru | Laporan telah dibuat dan menunggu pemeriksaan atau penugasan. |
| Ditugaskan | Tiket telah ditugaskan kepada staf IT. |
| Sedang Diproses | Staf IT sedang menangani kendala. |
| Menunggu | Penanganan menunggu informasi, konfirmasi, atau tindakan pihak terkait. |
| Selesai | Tiket telah memenuhi persyaratan penutupan. |

Perubahan status harus mengikuti kewenangan dan alur yang telah ditentukan.

### 6.3 Aturan Penugasan

1. Sistem menyediakan rekomendasi staf IT berdasarkan kriteria penugasan yang ditetapkan.
2. Rekomendasi tidak langsung dianggap sebagai penugasan final.
3. Staf IT harus mengonfirmasi atau menolak rekomendasi.
4. Penolakan wajib disertai alasan.
5. Hasil konfirmasi dan penolakan disimpan dalam riwayat tiket.
6. Penugasan ulang dilakukan sesuai mekanisme yang ditetapkan.

### 6.4 Aturan Konfirmasi Penyelesaian

1. Staf IT mengajukan penyelesaian setelah kendala ditangani.
2. Karyawan mendapatkan kesempatan untuk memeriksa hasil penanganan.
3. Karyawan memberikan konfirmasi atas hasil penyelesaian.
4. Jika hasil belum sesuai, tiket dapat dikembalikan untuk penanganan lanjutan.
5. Tiket kritis tetap membutuhkan persetujuan Manajer IT sebelum ditutup.

### 6.5 Aturan Persetujuan Tiket Kritis

1. Tiket dengan prioritas Kritis harus melalui persetujuan Manajer IT.
2. Manajer IT dapat menyetujui atau menolak penutupan.
3. Penolakan wajib disertai alasan.
4. Sistem mencatat keputusan dan waktu persetujuan.
5. Tiket kritis tidak boleh ditutup otomatis.

### 6.6 Aturan Penutupan Otomatis

1. Penutupan otomatis hanya berlaku untuk tiket nonkritis yang memenuhi syarat.
2. Tiket kritis dikecualikan dari penutupan otomatis.
3. Tiket yang masih dalam proses atau menunggu tidak boleh ditutup otomatis.
4. Durasi, titik awal perhitungan, dan mekanisme penutupan otomatis harus ditentukan melalui validasi stakeholder.
5. Seluruh proses penutupan otomatis harus dicatat dalam riwayat tiket.

---

## 7. Kebutuhan Data

Sistem memerlukan data utama sebagai berikut:

| Entitas | Deskripsi |
|---|---|
| Users | Menyimpan informasi akun pengguna. |
| Roles | Menyimpan jenis peran dan hak akses. |
| Departments | Menyimpan data departemen perusahaan. |
| Ticket Categories | Menyimpan kategori kendala IT. |
| Tickets | Menyimpan data laporan kendala. |
| Ticket Attachments | Menyimpan informasi lampiran tiket. |
| Ticket History | Menyimpan riwayat aktivitas tiket. |
| Ticket Assignments | Menyimpan informasi penugasan staf IT. |
| Ticket Approvals | Menyimpan keputusan persetujuan penutupan tiket. |
| Notifications | Menyimpan informasi notifikasi pengguna. |

Struktur tabel, atribut, tipe data, relasi, dan constraint akan dijelaskan lebih lanjut dalam dokumen Database Design.

---

## 8. Kebutuhan Antarmuka

### 8.1 Antarmuka Pengguna

Sistem direncanakan memiliki halaman:

1. Login.
2. Dashboard sesuai role.
3. Daftar tiket.
4. Formulir pelaporan kendala.
5. Detail tiket.
6. Riwayat aktivitas tiket.
7. Halaman penugasan staf IT.
8. Halaman persetujuan tiket kritis.
9. Pengelolaan pengguna dan master data.
10. Laporan dan evaluasi layanan.

### 8.2 Antarmuka Perangkat Lunak

Komponen perangkat lunak yang direncanakan:

- Backend: Laravel.
- Database: MySQL.
- Frontend: HTML, CSS, JavaScript, dan teknologi pendukung Laravel.
- Browser: Chrome, Edge, dan Firefox versi modern.

### 8.3 Antarmuka Komunikasi

Pada versi awal, komunikasi antara pengguna dan sistem berlangsung melalui aplikasi web dan notifikasi dalam aplikasi.

Integrasi dengan email, WhatsApp, atau layanan eksternal memerlukan keputusan ruang lingkup tersendiri.

---

## 9. Kebutuhan Pelaporan dan Pengukuran

Sistem harus mendukung pengukuran kinerja layanan melalui indikator berikut:

| KPI | Rumus Pengukuran |
|---|---|
| Jumlah tiket | Jumlah tiket yang dibuat pada periode laporan. |
| Waktu respons awal | Waktu respons pertama staf IT dikurangi waktu pembuatan tiket. |
| Waktu penyelesaian | Waktu tiket ditutup dikurangi waktu pembuatan tiket. |
| Tingkat penyelesaian | Tiket selesai dari kelompok tiket yang dibuat pada periode tersebut dibagi total tiket dalam kelompok yang sama × 100%. |
| Jumlah tiket kritis | Jumlah tiket dengan prioritas Kritis pada periode laporan. |
| Tiket melewati SLA | Jumlah tiket yang melewati target SLA yang telah disepakati. |
| Tingkat konfirmasi | Jumlah tiket yang telah mendapat konfirmasi dibagi jumlah tiket yang telah diajukan untuk konfirmasi × 100%. |

Pengukuran KPI harus memperhatikan periode laporan dan definisi status tiket. Target SLA ditetapkan setelah validasi operasional.

---

## 10. Kebutuhan Keamanan dan Audit

1. Setiap pengguna harus melakukan login.
2. Sistem menerapkan role-based access control.
3. Pengguna hanya dapat mengakses data sesuai kewenangannya.
4. Kata sandi disimpan dalam bentuk hash yang aman.
5. Lampiran harus divalidasi berdasarkan jenis dan ukuran file.
6. Riwayat aktivitas menyimpan identitas pelaku, waktu, dan jenis aktivitas.
7. Perubahan penting pada tiket harus dapat ditelusuri.
8. Mekanisme backup dan pemulihan database harus tersedia.
9. Kebijakan retensi data dan penghapusan data perlu ditetapkan oleh perusahaan.

---

## 11. Kriteria Penerimaan Sistem

Sistem dinyatakan memenuhi kebutuhan awal apabila:

1. Pengguna dapat login sesuai akun dan role.
2. Administrator dapat mengelola akun dan data master.
3. Karyawan dapat membuat laporan kendala.
4. Sistem menghasilkan nomor tiket unik.
5. Sistem memberikan rekomendasi prioritas berdasarkan matriks.
6. Sistem menyediakan rekomendasi penugasan.
7. Staf IT dapat mengonfirmasi atau menolak penugasan dengan alasan.
8. Staf IT dapat memperbarui status dan catatan penanganan.
9. Sistem menyimpan riwayat aktivitas tiket.
10. Karyawan dapat melihat status dan memberikan konfirmasi penyelesaian.
11. Manajer IT dapat memantau tiket dan menyetujui penutupan tiket kritis.
12. Sistem membatasi akses sesuai role.
13. Sistem menyediakan laporan evaluasi layanan.
14. Mekanisme penutupan otomatis mengikuti kebijakan yang telah disetujui.

---

## 12. Asumsi, Risiko, dan Hal yang Memerlukan Validasi

### 12.1 Asumsi

1. Sistem digunakan dalam lingkungan internal perusahaan.
2. Terdapat empat jenis role utama.
3. Setiap tiket memiliki satu pelapor.
4. Setiap tiket memiliki riwayat aktivitas.
5. Staf IT bertanggung jawab atas penanganan tiket yang ditugaskan kepadanya.

### 12.2 Risiko

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Data laporan tidak lengkap | Penanganan menjadi lambat | Validasi formulir |
| Rekomendasi prioritas tidak sesuai | Salah menentukan tingkat penanganan | Pemeriksaan staf IT |
| Rekomendasi penugasan tidak sesuai | Penugasan tidak efektif | Konfirmasi staf IT |
| Pengguna tidak memahami sistem | Penggunaan sistem tidak optimal | Panduan penggunaan |
| Gangguan server | Layanan tidak dapat diakses | Backup dan prosedur pemulihan |
| Hak akses tidak tepat | Risiko kebocoran data | Pengujian akses berdasarkan role |

### 12.3 Hal yang Memerlukan Validasi

| No. | Hal yang Divalidasi | Pihak Terkait |
|---|---|---|
| 1 | Matriks dampak dan urgensi | Manajer IT, Staf IT |
| 2 | Kriteria rekomendasi penugasan | Manajer IT, Staf IT |
| 3 | Kebijakan perubahan status | Manajer IT, Staf IT |
| 4 | Durasi dan syarat penutupan otomatis | Manajer IT |
| 5 | Target SLA | Manajer IT |
| 6 | Kanal notifikasi | Manajer IT, Administrator |
| 7 | Kebijakan penyimpanan dan retensi data | Administrator, Manajer IT |
| 8 | Target kinerja aplikasi | Administrator, tim pengelola sistem |

---

## 13. Kesimpulan

Dokumen Software Requirements Specification ini menjabarkan kebutuhan fungsional, nonfungsional, hak akses, aturan sistem, kebutuhan data, antarmuka, keamanan, serta kriteria penerimaan Sistem Helpdesk IT Perusahaan.

Dokumen ini menjadi acuan untuk tahap selanjutnya, yaitu System Design yang mencakup pemodelan UML, rancangan arsitektur, dan desain database.

Seluruh kebutuhan dalam dokumen ini merupakan rancangan awal berdasarkan skenario proyek dan masih memerlukan validasi stakeholder sebelum dianggap sebagai kebutuhan operasional final.

---

**Dokumen:** Software Requirements Specification (SRS)  
**Proyek:** Sistem Helpdesk IT Perusahaan  
**Versi:** 1.0  
**Status:** Draft – Memerlukan Validasi Stakeholder  
**Tahap:** Requirements Analysis
