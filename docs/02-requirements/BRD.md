
# Business Requirements Document (BRD)
## Sistem Helpdesk IT Perusahaan

**Versi:** 1.0  
**Status:** Draft – Memerlukan Validasi  
**Tahap:** Requirements Analysis

---

## 1. Pendahuluan

### 1.1 Latar Belakang

Dalam kegiatan operasional perusahaan, teknologi informasi memiliki peran penting dalam mendukung kelancaran pekerjaan karyawan.

Kendala seperti kerusakan perangkat komputer, gangguan jaringan internet, permasalahan aplikasi internal, printer, dan perangkat pendukung lainnya dapat menghambat aktivitas operasional perusahaan.

Pelaporan kendala yang mengandalkan komunikasi informal seperti WhatsApp berpotensi menyebabkan laporan terlewat, informasi tidak terdokumentasi, kesulitan menentukan prioritas, serta keterbatasan pemantauan perkembangan penanganan.

Untuk mengatasi permasalahan tersebut, diperlukan Sistem Helpdesk IT berbasis web yang mampu mengelola laporan kendala secara terpusat, mulai dari pelaporan hingga penyelesaian.

### 1.2 Tujuan Dokumen

Dokumen BRD ini bertujuan untuk:

1. Menjelaskan kebutuhan bisnis pengembangan Sistem Helpdesk IT.
2. Menentukan tujuan dan ruang lingkup proyek.
3. Mengidentifikasi kebutuhan utama stakeholder.
4. Menentukan aturan dan batasan bisnis.
5. Menetapkan indikator keberhasilan sistem.
6. Menjadi dasar penyusunan Software Requirements Specification (SRS).

### 1.3 Referensi Dokumen

Dokumen ini disusun berdasarkan hasil analisis sebelumnya:

1. Problem Statement.
2. Business Process Analysis.
3. Stakeholder Analysis.

---

## 2. Gambaran Umum Proyek

### 2.1 Nama Proyek

Sistem Helpdesk IT Perusahaan.

### 2.2 Deskripsi Proyek

Sistem Helpdesk IT merupakan aplikasi berbasis web yang digunakan untuk mengelola laporan kendala teknologi informasi di lingkungan perusahaan.

Sistem memungkinkan karyawan membuat laporan, staf IT melakukan penanganan, serta Manajer IT mengawasi perkembangan dan mengevaluasi layanan dukungan teknologi informasi.

### 2.3 Tujuan Bisnis

Tujuan bisnis pengembangan sistem meliputi:

- Memusatkan seluruh laporan kendala IT.
- Mengurangi risiko laporan terlewat.
- Meningkatkan konsistensi penentuan prioritas.
- Mempermudah proses penugasan staf IT.
- Meningkatkan transparansi penanganan laporan.
- Menyediakan dokumentasi riwayat aktivitas.
- Mendukung pengawasan dan evaluasi layanan IT.

### 2.4 Permasalahan Bisnis

| Kode | Permasalahan | Dampak Bisnis |
|---|---|---|
| PB-01 | Pelaporan melalui komunikasi informal. | Risiko laporan tidak tercatat. |
| PB-02 | Prioritas kendala belum terstruktur. | Kendala penting dapat terlambat ditangani. |
| PB-03 | Penugasan belum terpusat. | Pembagian pekerjaan sulit dipantau. |
| PB-04 | Status laporan tidak transparan. | Karyawan harus menanyakan perkembangan. |
| PB-05 | Riwayat penanganan belum sistematis. | Evaluasi layanan menjadi sulit. |
| PB-06 | Pengawasan tiket kritis terbatas. | Risiko keterlambatan eskalasi. |

---

## 3. Stakeholder Bisnis

### 3.1 Daftar Stakeholder

| Kode | Stakeholder | Peran |
|---|---|---|
| ST-01 | Administrator | Mengelola administrasi sistem. |
| ST-02 | Karyawan | Melaporkan kendala IT. |
| ST-03 | Staf IT | Menangani kendala IT. |
| ST-04 | Manajer IT | Mengawasi dan mengevaluasi layanan IT. |

### 3.2 Kepentingan Stakeholder

**Administrator**
- Pengelolaan akun dan hak akses.
- Pengelolaan kategori kendala.
- Pengelolaan data departemen.

**Karyawan**
- Pelaporan kendala yang mudah.
- Informasi nomor tiket.
- Pemantauan status laporan.
- Konfirmasi penyelesaian.

**Staf IT**
- Daftar laporan masuk.
- Informasi detail kendala.
- Rekomendasi penugasan.
- Pengelolaan status.
- Dokumentasi tindakan penanganan.

**Manajer IT**
- Dashboard monitoring.
- Informasi tiket kritis.
- Pengawasan pekerjaan staf.
- Persetujuan penutupan tiket kritis.
- Laporan evaluasi layanan.

---

## 4. Ruang Lingkup Proyek

### 4.1 Ruang Lingkup yang Termasuk

Sistem mencakup:

1. Autentikasi pengguna.
2. Pengelolaan role dan hak akses.
3. Pengelolaan data pengguna dan departemen.
4. Pengelolaan kategori kendala IT.
5. Pembuatan laporan kendala.
6. Pengunggahan lampiran laporan.
7. Pembuatan nomor tiket otomatis.
8. Klasifikasi dampak dan urgensi.
9. Penentuan rekomendasi prioritas.
10. Rekomendasi penugasan staf IT.
11. Konfirmasi penugasan oleh staf IT.
12. Pengelolaan status tiket.
13. Pencatatan riwayat aktivitas.
14. Konfirmasi penyelesaian oleh karyawan.
15. Persetujuan penutupan tiket kritis.
16. Dashboard monitoring Manajer IT.
17. Laporan dan evaluasi layanan IT.
18. Mekanisme penutupan otomatis sesuai aturan bisnis.

### 4.2 Ruang Lingkup yang Tidak Termasuk

Untuk menjaga fokus pengembangan, proyek ini tidak mencakup:

1. Pengelolaan aset IT secara menyeluruh.
2. Pengelolaan inventaris perangkat perusahaan.
3. Sistem penggajian atau keuangan.
4. Pengelolaan sumber daya manusia.
5. Penggantian seluruh aplikasi komunikasi perusahaan.
6. Integrasi WhatsApp sebagai kanal utama pelaporan.
7. Penggunaan AI sebagai pengambil keputusan penugasan otomatis.

---

## 5. Kebutuhan Bisnis (Business Requirements)

Kebutuhan bisnis merupakan kemampuan utama yang harus disediakan oleh sistem untuk menyelesaikan permasalahan operasional.

| ID | Kebutuhan Bisnis | Prioritas |
|---|---|---|
| BR-001 | Sistem menyediakan pelaporan kendala IT secara terpusat. | Tinggi |
| BR-002 | Sistem menyimpan setiap laporan dengan nomor tiket unik. | Tinggi |
| BR-003 | Sistem menyediakan kategori kendala IT. | Tinggi |
| BR-004 | Sistem mendukung klasifikasi dampak dan urgensi. | Tinggi |
| BR-005 | Sistem memberikan rekomendasi prioritas berdasarkan matriks. | Tinggi |
| BR-006 | Sistem menyediakan rekomendasi penugasan staf IT. | Tinggi |
| BR-007 | Sistem menyediakan konfirmasi penugasan oleh staf IT. | Tinggi |
| BR-008 | Sistem menyediakan pemantauan status laporan. | Tinggi |
| BR-009 | Sistem menyimpan riwayat aktivitas tiket. | Tinggi |
| BR-010 | Sistem mendukung konfirmasi penyelesaian oleh karyawan. | Tinggi |
| BR-011 | Sistem menyediakan persetujuan penutupan tiket kritis. | Tinggi |
| BR-012 | Sistem menyediakan dashboard Manajer IT. | Tinggi |
| BR-013 | Sistem menyediakan pengelolaan akun dan hak akses. | Tinggi |
| BR-014 | Sistem menyediakan pengelolaan lampiran laporan. | Sedang |
| BR-015 | Sistem menyediakan laporan evaluasi layanan IT. | Sedang |
| BR-016 | Sistem mendukung mekanisme penutupan otomatis sesuai kebijakan. | Sedang |

---

## 6. Aturan Bisnis (Business Rules)

| ID | Aturan |
|---|---|
| RULE-01 | Setiap pengguna harus melakukan autentikasi sebelum mengakses fitur sesuai perannya. |
| RULE-02 | Setiap laporan harus memiliki informasi wajib yang telah ditentukan. |
| RULE-03 | Setiap laporan memiliki nomor tiket unik. |
| RULE-04 | Prioritas direkomendasikan berdasarkan kombinasi dampak dan urgensi. |
| RULE-05 | Klasifikasi prioritas dapat diperiksa oleh staf IT. |
| RULE-06 | Rekomendasi penugasan harus dikonfirmasi oleh staf IT. |
| RULE-07 | Penolakan rekomendasi penugasan harus disertai alasan. |
| RULE-08 | Setiap perubahan status dicatat dalam riwayat aktivitas. |
| RULE-09 | Karyawan hanya dapat mengakses laporan sesuai kewenangannya. |
| RULE-10 | Staf IT hanya dapat menjalankan tindakan sesuai hak aksesnya. |
| RULE-11 | Karyawan memberikan konfirmasi terhadap hasil penyelesaian. |
| RULE-12 | Tiket kritis membutuhkan persetujuan Manajer IT sebelum ditutup. |
| RULE-13 | Penolakan penutupan tiket harus disertai alasan. |
| RULE-14 | Penutupan otomatis hanya berlaku sesuai syarat dan kebijakan yang disetujui. |
| RULE-15 | Tiket kritis tidak boleh ditutup otomatis tanpa persetujuan Manajer IT. |
| RULE-16 | Sistem menyimpan riwayat aktivitas tiket secara konsisten. |

---

## 7. Gambaran Proses Bisnis yang Diusulkan

Proses bisnis utama sistem adalah:

1. Karyawan masuk ke sistem.
2. Karyawan membuat laporan kendala IT.
3. Sistem memvalidasi informasi laporan.
4. Sistem membuat nomor tiket.
5. Sistem menentukan rekomendasi prioritas.
6. Sistem memberikan rekomendasi penugasan.
7. Staf IT memeriksa dan mengonfirmasi penugasan.
8. Staf IT menangani kendala.
9. Staf IT memperbarui status dan catatan penanganan.
10. Karyawan menerima informasi hasil penyelesaian.
11. Karyawan memberikan konfirmasi.
12. Manajer IT menyetujui penutupan jika tiket berkategori kritis.
13. Sistem menyelesaikan dan menyimpan riwayat tiket.

---

## 8. Indikator Keberhasilan Bisnis

Indikator berikut digunakan untuk mengevaluasi keberhasilan penerapan sistem.

| KPI | Pengukuran |
|---|---|
| Jumlah laporan tercatat | Jumlah laporan yang berhasil dibuat melalui sistem. |
| Waktu respons awal | Selisih waktu laporan dibuat dan penanganan awal. |
| Waktu penyelesaian | Selisih waktu laporan dibuat dan tiket diselesaikan. |
| Persentase penyelesaian | Jumlah tiket selesai dibandingkan jumlah tiket masuk dalam periode yang sama. |
| Tiket kritis | Jumlah tiket dengan prioritas kritis. |
| Tiket melewati SLA | Jumlah tiket yang melebihi target waktu layanan. |
| Konfirmasi penyelesaian | Persentase tiket yang mendapatkan konfirmasi karyawan. |

Target KPI akan ditentukan setelah tersedia data operasional dan kesepakatan SLA perusahaan.

---

## 9. Asumsi dan Ketergantungan

### 9.1 Asumsi

1. Perusahaan memiliki tim IT internal.
2. Pengguna memiliki akun sistem.
3. Terdapat pembagian tanggung jawab antara staf IT dan Manajer IT.
4. Perusahaan menyetujui matriks prioritas.
5. Perusahaan menetapkan kebijakan penutupan tiket.
6. Sistem dapat diakses melalui jaringan yang tersedia bagi pengguna.

### 9.2 Ketergantungan

Keberhasilan sistem bergantung pada:

- Ketersediaan infrastruktur server dan database.
- Ketersediaan koneksi jaringan.
- Ketepatan data pengguna.
- Kedisiplinan pengguna dalam membuat laporan.
- Ketersediaan staf IT.
- Persetujuan kebijakan operasional oleh Manajer IT.
- Validasi kebutuhan dari stakeholder.

---

## 10. Risiko Bisnis

| ID | Risiko | Dampak | Mitigasi |
|---|---|---|---|
| RISK-01 | Pengguna tidak terbiasa menggunakan sistem. | Pelaporan tetap dilakukan melalui jalur informal. | Sosialisasi dan panduan penggunaan. |
| RISK-02 | Informasi laporan tidak lengkap. | Penanganan menjadi lambat. | Validasi formulir laporan. |
| RISK-03 | Rekomendasi penugasan tidak sesuai. | Penanganan tidak efektif. | Konfirmasi dan penugasan ulang. |
| RISK-04 | Tidak ada staf IT yang tersedia. | Tiket tertunda. | Eskalasi dan pemantauan beban kerja. |
| RISK-05 | Sistem mengalami gangguan. | Pelaporan terganggu. | Backup dan prosedur operasional darurat. |
| RISK-06 | Kebijakan prioritas belum disepakati. | Penentuan prioritas tidak konsisten. | Validasi matriks bersama stakeholder. |

---

## 11. Kriteria Penerimaan Bisnis (Business Acceptance Criteria)

Sistem dapat dinyatakan memenuhi kebutuhan bisnis awal apabila:

1. Karyawan dapat membuat laporan kendala IT.
2. Setiap laporan mendapatkan nomor tiket unik.
3. Sistem dapat menentukan rekomendasi prioritas.
4. Staf IT dapat mengonfirmasi penugasan.
5. Staf IT dapat memperbarui status laporan.
6. Karyawan dapat memantau perkembangan tiket.
7. Sistem dapat mencatat riwayat aktivitas.
8. Karyawan dapat mengonfirmasi hasil penyelesaian.
9. Manajer IT dapat memantau laporan dan tiket kritis.
10. Tiket kritis memerlukan persetujuan Manajer IT sebelum penutupan.
11. Hak akses pengguna berjalan sesuai peran masing-masing.

---

## 12. Persetujuan dan Validasi

Dokumen BRD ini merupakan rancangan kebutuhan bisnis awal berdasarkan skenario operasional perusahaan.

Sebelum implementasi final, dokumen perlu divalidasi oleh stakeholder terkait.

| Pihak | Peran dalam Validasi | Status |
|---|---|---|
| Administrator | Validasi kebutuhan administrasi sistem | Belum divalidasi |
| Karyawan | Validasi kebutuhan pelaporan | Belum divalidasi |
| Staf IT | Validasi proses penanganan | Belum divalidasi |
| Manajer IT | Validasi kebijakan dan kebutuhan pengawasan | Belum divalidasi |

---

## 13. Kesimpulan

Business Requirements Document ini menjelaskan kebutuhan bisnis pengembangan Sistem Helpdesk IT Perusahaan sebagai solusi untuk meningkatkan keteraturan proses pelaporan dan penanganan kendala teknologi informasi.

Sistem dirancang untuk menyediakan pelaporan terpusat, klasifikasi prioritas, rekomendasi penugasan, pemantauan status, pencatatan riwayat, konfirmasi penyelesaian, serta pengawasan oleh Manajer IT.

Dokumen ini menjadi dasar untuk menyusun Software Requirements Specification (SRS), yang akan menjelaskan kebutuhan fungsional dan nonfungsional sistem secara lebih teknis.

---

**Dokumen:** Business Requirements Document  
**Proyek:** Sistem Helpdesk IT Perusahaan  
**Versi:** 1.0  
**Status:** Draft – Memerlukan Validasi Stakeholder
