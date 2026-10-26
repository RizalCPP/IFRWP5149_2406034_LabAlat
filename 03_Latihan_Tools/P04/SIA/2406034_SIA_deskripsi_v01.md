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