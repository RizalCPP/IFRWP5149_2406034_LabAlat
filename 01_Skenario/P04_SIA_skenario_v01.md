<!-- Skenario -->
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian. 

Lankah 1 : Catat Kebutuhan dan Batas Sistem

<!-- Tabel Kebutuhan -->

| ID | Kebutuhan Tugas |
| :--- | :--- |
| **SIA-R07** | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik. |
| **SIA-R08** | Dosen dapat menginput nilai mata kuliah yang diampunya. |
| **SIA-R09** | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan. |
| **SIA-R10** | Admin Akademik dapat mengelola data mahasiswa. |
| **SIA-R11** | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| **SIA-R12** | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS. |

<!-- Batas Sistem -->

• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap mempunyai identitas berbeda. 
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran. 
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya); jangan menyamakannya dengan jadwal kuliah pada Pertemuan 2. 
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan. 
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. Ketentuan ini fiktif untuk latihan. 
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari Pertemuan 3. Pembayaran dan perancangan basis data berada di luar ugas ini.


Langkah 2 : Identifikasi Aktor dan Use Case

<!-- Identifikasi Aktor Kumulatif -->

| ID Aktor | Nama Aktor | Kategori / Hirarki | Status |
| :--- | :--- | :--- | :--- |
| **ACT-01** | Civitas Akademika | Parent Actor (Abstrak) | Baru |
| **ACT-02** | Mahasiswa | Child Actor (Spesialisasi dari Civitas Akademika) | Tetap |
| **ACT-03** | Dosen | Child Actor (Spesialisasi dari Civitas Akademika) | Tetap |
| **ACT-04** | Dosen Wali | Aktor Mandiri | Tetap |
| **ACT-05** | Admin Akademik | Aktor Mandiri | Tetap |

<!-- Identifikasi Use Case Kumulatif -->

| ID | Nama Use Case | Aktor Terkait | Sumber Kebutuhan | Status |
| :--- | :--- | :--- | :--- | :--- |
| **SIA-UC01** | Lihat Jadwal Kuliah | Mahasiswa, Dosen | SIA-R01 | Tetap |
| **SIA-UC02** | Kelola Jadwal Kuliah | Admin Akademik | SIA-R02 | Tetap |
| **SIA-UC03** | Ajukan KRS | Mahasiswa | SIA-R03 | Tetap |
| **SIA-UC04** | Validasi KRS | Dosen Wali | SIA-R04 | Tetap |
| **SIA-UC05** | Unduh Bukti Pengajuan KRS | Mahasiswa | SIA-R05 | Tetap |
| **SIA-UC06** | Proses Keputusan KRS | Dosen Wali | SIA-R06 | Tetap |
| **SIA-UC07** | Lihat Kalender Akademik | Civitas Akademika | SIA-R07 | Baru |
| **SIA-UC08** | Input Nilai Mata Kuliah | Dosen | SIA-R08 | Baru |
| **SIA-UC09** | Lihat KHS | Mahasiswa | SIA-R09 | Baru |
| **SIA-UC10** | Kelola Data Mahasiswa | Admin Akademik | SIA-R10 | Baru |
| **SIA-UC11** | Tambah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| **SIA-UC12** | Ubah Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |
| **SIA-UC13** | Hapus Data Mahasiswa | Admin Akademik | SIA-R11 | Baru |

Langkah 3 : Generalization Aktor 

<!-- Hierarki Aktor -->

| Tingkat / Posisi | Nama Aktor | Kategori | Deskripsi |
| :--- | :--- | :--- | :--- |
| **Parent (Induk)** | Civitas Akademika | Abstract Actor | Aktor tingkat atas yang mewakili peran umum entitas di lingkungan kampus. Tidak berinteraksi langsung secara mandiri, melainkan melalui turunan aktornya. |
| **Child (Anak 1)** | Mahasiswa | Concrete Actor | Aktor spesifik yang mewarisi seluruh kemampuan Civitas Akademika, serta memiliki fungsi khusus (seperti pengajuan KRS dan melihat KHS). |
| **Child (Anak 2)** | Dosen | Concrete Actor | Aktor spesifik yang mewarisi seluruh kemampuan Civitas Akademika, serta memiliki fungsi khusus (seperti input nilai mata kuliah). |

<!-- Fungsi yang Diwarisi -->

SIA-UC07 Lihat Kalender Akademik
Fungsi ini terhubung secara langsung ke induk aktor (Civitas Akademika). Karena Mahasiswa dan Dosen merupakan turunan dari Civitas Akademika, kedua aktor tersebut secara otomatis mewarisi (inherit) hak akses untuk menjalankan use case Lihat Kalender Akademik tanpa perlu dibuatkan garis asosiasi terpisah.

<!-- Alasan Pemodelan Generalisasi Aktor -->

1) Menghindari Redundansi Asosiasi: Tanpa generalisasi, kita harus menarik dua garis asosiasi terpisah dari Mahasiswa ke Lihat Kalender Akademik dan dari Dosen ke Lihat Kalender Akademik. Dengan generalisasi, garis asosiasi cukup digambar satu kali dari Civitas Akademika.

2) Prinsip Abstraksi & Reusabilitas: Mengelompokkan peran yang memiliki kesamaan fungsi ke dalam satu induk umum. Jika di kemudian hari ada fungsi baru yang berlaku untuk seluruh civitas akademika, fungsi tersebut cukup dihubungkan ke induk aktor Civitas Akademika.

3) Meningkatkan Kejelasan Diagram: Diagram Use Case menjadi lebih bersih, rapi, dan mudah dibaca karena mengurangi penumpukan garis asosiasi.

Langkah 4 : Generalization Use Case

1) Use Case Umum

    - SIA-UC10 Kelola Data Mahasiswa: Induk use case yang mendefinisikan kerangka umum proses pemeliharaan dan tata kelola data mahasiswa oleh Admin Akademik.

2) Use Case Khusus dan Perilaku Pembeda

    - SIA-UC11 Tambah Data Mahasiswa: Admin Akademik menginput data identitas dan profil mahasiswa baru ke dalam sistem untuk menerbitkan pendaftaran resmi.

    - SIA-UC12 Ubah Data Mahasiswa: Admin Akademik memperbarui atribut informasi mahasiswa yang sudah terdaftar tanpa mengubah atau memengaruhi riwayat transaksi akademik yang tersimpan.

    - SIA-UC13 Hapus Data Mahasiswa: Admin Akademik menghapus rekam data mahasiswa dari sistem khusus untuk mahasiswa yang tidak memiliki data akademik aktif.

Langkah 5 : Collaboration

| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan | Aktor Terkait |
| :--- | :--- | :--- | :--- |
| **SIA-CO01** | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah | Dosen |
| **SIA-CO02** | Lihat KHS | SIA-UC09 Lihat KHS | Mahasiswa |

Penjelasan :

1) SIA-CO01 Input Nilai Mata Kuliah

    - Use Case yang Direalisasikan: SIA-UC08 Input Nilai Mata Kuliah

    - Deskripsi Realisasi: Memodelkan kolaborasi elemen struktur (Boundary, Control, Entity) yang bekerja sama merealisasikan perilaku sistem saat Dosen memasukkan nilai mata kuliah yang diampu.

2) SIA-CO02 Lihat KHS

    - Use Case yang Direalisasikan: SIA-UC09 Lihat KHS

    - Deskripsi Realisasi: Memodelkan kolaborasi elemen struktur (Boundary, Control, Entity) yang bekerja sama merealisasikan perilaku sistem saat Mahasiswa memuat dan melihat Kartu Hasil Studi untuk semester yang sudah dipublikasikan.

Langkah 6 : Use Case Description

<!-- Deskripsi Lengkap Use Case: Input Nilai Mata Kuliah -->
| Elemen | Keterangan |
| :--- | :--- |
| **ID Use Case** | SIA-UC08 |
| **Nama Use Case** | Input Nilai Mata Kuliah |
| **Aktor Utama** | Dosen |
| **Deskripsi** | Process pengisian nilai akhir mata kuliah untuk mahasiswa pada kelas yang diampu oleh dosen setelah masa perkuliahan berakhir. |
| **Collaboration** | SIA-CO01 Input Nilai Mata Kuliah |
| **Prasyarat** | Dosen telah terautentikasi ke dalam sistem dan merupakan dosen pengampu resmi dari mata kuliah yang dipilih. |
| **Pascakondisi Berhasil** | Data nilai mata kuliah mahasiswa berhasil tersimpan ke dalam sistem dengan status siap dipublikasikan. |
| **Pascakondisi Gagal** | Data nilai tidak tersimpan ke dalam sistem dan kondisi nilai mahasiswa tetap sama seperti sebelum proses input. |

1) Alur Utama (Main Flow):

    - Dosen memilih menu Input Nilai Mata Kuliah.

    - Sistem menampilkan daftar mata kuliah dan kelas yang diampu oleh dosen tersebut.

    - Dosen memilih mata kuliah serta kelas yang ingin diisi nilainya.

    - Sistem menampilkan daftar mahasiswa beserta form pengisian nilai.

    - Dosen memasukkan nilai untuk tiap mahasiswa dan menekan tombol Simpan.

    - Sistem memvalidasi rentang nilai yang dimasukkan.

    - Sistem menyimpan data nilai dan menampilkan notifikasi bahwa data berhasil disimpan.

2) Alur Alternatif (Alternative Flow):

    - 6a. Nilai Di Luar Rentang yang Sah:

        - Apabila sistem mendeteksi nilai yang dimasukkan berada di luar rentang yang sah (misalnya nilai kurang dari 0, lebih dari 100, atau format tidak sesuai), sistem menolak masukan nilai tersebut.

        - Sistem menampilkan pesan kesalahan/peringatan bahwa nilai di luar rentang yang diizinkan.

        - Dosen mengoreksi dan menginput ulang nilai yang valid.

        - Alur kembali ke langkah 5 pada Alur Utama.

<!-- Deskripsi Ringkas Use Case: Lihat KHS -->

| Elemen | Keterangan |
| :--- | :--- |
| **ID Use Case** | SIA-UC09 |
| **Nama Use Case** | Lihat KHS |
| **Aktor Utama** | Mahasiswa |
| **Collaboration** | SIA-CO02 Lihat KHS |
| **Deskripsi Ringkas** | Mahasiswa memilih semester aktif atau semester sebelumnya untuk menampilkan Kartu Hasil Studi (KHS). Sistem hanya memuat dan menampilkan nilai mata kuliah yang sudah dinyatakan resmi dipublikasikan oleh pihak institusi/dosen pengampu. |

Langkah 8 : Uji Konsistensi 

1) Situasi A: Mahasiswa melihat kalender akademik tanpa garis asosiasi langsung dari Mahasiswa

    Penjelasan: Hal tersebut tetap benar karena menerapkan konsep generalisasi aktor. Mahasiswa merupakan aktor anak dari Civitas Akademika. Mahasiswa secara otomatis mewarisi seluruh hak akses dan asosiasi milik Civitas Akademika, termasuk akses ke use case SIA-UC07 Lihat Kalender Akademik. Penggambaran garis asosiasi cukup ditarik satu kali dari aktor induk Civitas Akademika untuk mencegah penumpukan garis pada diagram.

2) Situasi B: Dosen yang bukan pengampu mencoba menginput nilai

    Hasil yang Terjadi: Sistem menolak tindakan tersebut. Berdasarkan prasyarat dan alur use case SIA-UC08 Input Nilai Mata Kuliah, sistem memvalidasi hak akses dan hanya menampilkan kelas yang resmi diampu oleh dosen yang login. Dosen yang bukan pengampu tidak akan diberikan akses ke form input nilai mata kuliah tersebut, sehingga proses input dihentikan dan pascakondisi gagal berlaku.

3) Situasi C: Admin Akademik menghapus data mahasiswa yang masih memiliki data akademik aktif

    Hasil yang Terjadi: Sistem memblokir proses penghapusan. Berdasarkan aturan batas sistem dan deskripsi SIA-UC13 Hapus Data Mahasiswa, tindakan hapus data hanya diizinkan untuk mahasiswa yang tidak lagi memiliki rekam data akademik aktif. Sistem akan menampilkan pesan peringatan bahwa data tidak dapat dihapus karena status mahasiswa masih terikat dengan data akademik aktif.