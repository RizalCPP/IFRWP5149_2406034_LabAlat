<!-- Deskripsi Skenario -->

Skenario berikut merupakan bahan latihan yang ditetapkan untuk jobsheet, bukan hasil pengumpulan kebutuhan laboratorium nyata. Skenario ini melanjutkan potongan model Pertemuan 3. Selain mahasiswa, dosen juga meminjam peralatan laboratorium untuk kegiatan praktikum dan penelitian. Mahasiswa dan dosen sama-sama dapat melihat ketersediaan peralatan dan mengajukan peminjaman. Petugas laboratorium mengelola data peralatan: menambah peralatan baru, mengubah data peralatan, dan menghapus data peralatan yang tidak lagi dipakai. Setelah peminjaman disetujui dan alat diambil, petugas mencatat pengembalian peralatan. Pada saat mencatat pengembalian, petugas memeriksa dan mencatat kondisi peralatan. Dua use case utama pada potongan model ini, Ajukan Peminjaman dan Catat Pengembalian Peralatan, ditunjukkan realisasinya oleh collaboration yang bersesuaian. Seluruh fungsi Pertemuan 3 tetap berlaku dan tetap digambar: pemeriksaan ketersediaan di dalam pengajuan, pencetakan bukti 
pengajuan oleh mahasiswa, proses keputusan peminjaman oleh petugas, dan laporan peminjaman untuk kepala laboratorium. Diagram Pertemuan 4 adalah diagram Pertemuan 3 yang ditambah, bukan diagram baru yang menggantikannya. 

<!-- Tabel Kebutuhan -->

|  ID                 |                                                   Kebutuhan                                                     |
|---------------------|---------------------------------------------------------------------------------------------------------------- |
|LAB-R01 s.d. LAB-R06 | Kebutuhan Pertemuan 3 tetap berlaku dan tidak berubah arti (lihat Jobsheet Pertemuan 3).                        |
|LAB-R07              |  Mahasiswa dan Dosen, sebagai Peminjam, dapat melihat ketersediaan peralatan dan mengajukan peminjaman.         |
|LAB-R08              | Petugas laboratorium mengelola data peralatan dalam tiga bentuk khusus: tambah, ubah, dan hapus data peralatan. |
|LAB-R09              | Petugas laboratorium dapat mencatat pengembalian peralatan untuk peminjaman yang berstatus Dipinjam.            |
|LAB-R10              | Sistem memeriksa dan mencatat kondisi peralatan sebagai bagian dari pencatatan pengembalian.                    |
|LAB-R11              | Model menunjukkan collaboration yang merealisasikan Ajukan Peminjaman dan Catat Pengembalian Peralatan.         |
----------------------------------------------------------------------------------------------------------------------------------------

<!-- Batas Sistem dan Aturan -->
Batas sistem dan aturan 
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak 
terjadi di dalam perangkat lunak (tetap dari Pertemuan 3). 
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap 
dari Pertemuan 3). 
• Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam. 
Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat 
dicatat pengembaliannya. 
• Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik, 
Rusak Ringan, atau Rusak Berat. 
• Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam 
dan tidak memiliki pengajuan aktif. 
• Keterlambatan dan denda belum dimodelkan pada pertemuan ini. Tuliskan 
sebagai pertanyaan terbuka pada berkas kebutuhan, jangan mengarang 
aturan denda. 
• Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11 
mempunyai representasi pada diagram kumulatif, arah generalization dan 
realization benar, dan diagram konsisten dengan deskripsinya. 

<!-- Aktor Umum dan Aktor Khusus -->

Aktor                   : Peminjaman 
Kedudukan               : Umum (generasi baru pada Pertemuan 4)
Tujuan terhadap sistem  : Peran umum bagi peminjam peralatan. Mewariskan fungsinya kepada Mahasiswa dan Dosen. 

Aktor                   : Mahasiswa
Kedudukan               : Khusus dari Peminjam, tetap dari Pertemuan 3 
Tujuan terhadap sistem  : Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam), ditambah mencetak bukti pengajuan sebagai asosiasi khususnya sendiri. 

Aktor                   : Dosen 
Kedudukan               : Khusus dari Peminjam, baru pada Pertemuan 4
Tujuan terhadap sistem  : Melihat ketersediaan dan mengajukan peminjaman (diwarisi dari Peminjam). 

Aktor                   : Petugas Laboratorium 
Kedudukan               : Tetap dari Pertemuan 3
Tujuan terhadap sistem  : Mengelola data peralatan, memproses keputusan peminjaman, dan mencatat pengembalian peralatan. 

Aktor                   : Kepala Laboratorium 
Kedudukan               : Tetap dari Pertemuan 3
Tujuan terhadap sistem  : Melihat laporan peminjaman. 

<!-- Katalog Use Case -->

| ID | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
|---|---|---|---|
| LAB-UC01 | Lihat Ketersediaan Peralatan | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam | LAB-R01, LAB-R07 |
| LAB-UC02 | Kelola Data Peralatan | Tetap dari Pertemuan 3; use case umum bagi LAB-UC08, LAB-UC09, dan LAB-UC10 | LAB-R02, LAB-R08 |
| LAB-UC03 | Ajukan Peminjaman | Tetap dari Pertemuan 3; fungsi aktor umum Peminjam; menyertakan LAB-UC04 dan direalisasikan LAB-CO01 | LAB-R03, LAB-R07 |
| LAB-UC04 | Periksa Ketersediaan | Tetap dari Pertemuan 3; perilaku yang disertakan LAB-UC03 | LAB-R03 |
| LAB-UC05 | Cetak Bukti Pengajuan | Tetap dari Pertemuan 3; tambahan bersyarat pada LAB-UC03 melalui relasi `«extend»` | LAB-R04 |
| LAB-UC06 | Proses Keputusan Peminjaman | Tetap dari Pertemuan 3; fungsi utama petugas | LAB-R05 |
| LAB-UC07 | Lihat Laporan Peminjaman | Tetap dari Pertemuan 3; fungsi utama kepala laboratorium | LAB-R06 |
| LAB-UC08 | Tambah Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02 | LAB-R08 |
| LAB-UC09 | Ubah Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02 | LAB-R08 |
| LAB-UC10 | Hapus Data Peralatan | Baru pada Pertemuan 4; use case khusus dari LAB-UC02 | LAB-R08 |
| LAB-UC11 | Catat Pengembalian Peralatan | Baru pada Pertemuan 4; fungsi utama petugas; direalisasikan LAB-CO02 | LAB-R09 |
| LAB-UC12 | Periksa Kondisi Peralatan | Baru pada Pertemuan 4; perilaku yang disertakan LAB-UC11 | LAB-R10 |

<!-- Generalization Aktor -->

1) Generalisasi Aktor (Actor Generalization)

    - Hierarki Aktor:

        - Parent Actor (Induk / Abstrak): Peminjam

        - Child Actors (Anak / Konkret): Mahasiswa dan Dosen

        - Fungsi yang Diwarisi (Inherited Functions):

        - LAB-UC01 Lihat Ketersediaan Peralatan

        - LAB-UC03 Ajukan Peminjaman

    - Catatan: Asosiasi ke kedua use case ini cukup ditarik satu kali dari aktor induk Peminjam.

    - Fungsi Spesifik Aktor Anak:

        - LAB-UC05 Cetak Bukti Pengajuan: Tetap dihubungkan secara khusus ke aktor Mahasiswa dan tidak diwariskan atau dipindahkan ke Peminjam.

    - Keputusan & Alasan Pemodelan:

        - Hubungan Spesialisasi: Mahasiswa dan Dosen merupakan bentuk khusus dari Peminjam karena keduanya berbagi fungsi dasar yang sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman.

        - Penyederhanaan Diagram: Garis asosiasi ke LAB-UC01 dan LAB-UC03 tidak digambar terpisah dari Mahasiswa dan Dosen untuk mencegah redundansi garis.

        - Pemisahan Hak Akses Spesifik: Asosiasi Mahasiswa ke LAB-UC05 dipertahankan secara khusus pada aktor anak karena fungsi cetak bukti pengajuan hanya berlaku untuk mahasiswa.

    - Aturan Visual Penggambaran Diagram:

        - Gunakan garis generalisasi (garis lurus berujung segitiga berongga/putih ▲).

        - Ujung segitiga berongga harus menempel pada aktor induk (Peminjam).

        - Panah dari Mahasiswa mengarah ke Peminjam, dan panah dari Dosen juga mengarah ke Peminjam.

<!-- Generalization Use Case -->

2) Generalisasi Use Case (Use Case Generalization)

    - Induk (Parent Use Case): LAB-UC02 Kelola Data Peralatan

    - Anak (Child Use Cases):

        - LAB-UC08 Tambah Data Peralatan

        - LAB-UC09 Ubah Data Peralatan

        - LAB-UC10 Hapus Data Peralatan

    - Aturan Visual Penggambaran Diagram:

        - Panah generalisasi (segitiga berongga ▲) ditarik dari masing-masing use case khusus (LAB-UC08, LAB-UC09, LAB-UC10) mengarah ke use case induk (LAB-UC02).



