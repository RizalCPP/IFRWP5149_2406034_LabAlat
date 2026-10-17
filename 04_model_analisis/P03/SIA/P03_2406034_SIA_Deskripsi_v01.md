Langakah 5 : Susun Deskripsi

1) SIA-UC03 - Ajukan KRS
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC03 - Ajukan KRS
|Tujuan                 | Menghasilkan pengajuan KRS yang tersimpan dan berstatus menunggu
|Aktor Utama            | Mahasiswa
|Sumber Kebutuhan       | SIA-R03 dan SIA-R04
|Pemicu                 | Mahasiswa memilih fungsi/menu pengajuan KRS
|Prasyarat              | Mahasiswa telah terautentikasi data mata kuliah, prasyarat, jadwal kuliah
|Pasca Kondisi Berhasil | Pengajuan KRS tersimpan dengan status Menunggu persetujuan dosen wali
|Pasca Kondisi Gagal    | Tidak ada pengajuan KRS baru yang berhasil tersimpan
|Include                | SIA-UC05 - Validasi KRS
|Extension Point        | Bukti pengajuan tersedia, pada konfirmasi penyimpanan
|Extend                 | SIA-UC05 jika (mahasiswa memilih mengunduh bukti)
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah     Tindakan Mahasiswa                                 Respon Sistem
_________________________________________________________________________________________________________________________
|1          Membuka pengajuan KRS               Menampilkan formulir pengajuan KRS
|2          Memilih mata kulaih yang diambil    Menampung isian
|3          Mengirim Pengajuan KRS              Memeriksa kelengkapan data
|4          -                                   Menjalankan SIA-UC04
|5          -                                   Jika valid, menyimpan pengajuan berstatus Menunggu persetujuan dosen wali
|6          Melihat Konfirmasi                  Menampilkan konfirmasi penyimpanan; mencapai extension point
|7          Mengahkhiri Pengajuan               Menutup proses pengajuan
_________________________________________________________________________________________________________________________

2) SIA-UC04 - Validasi KRS
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC04 - Validasi KRS
|Tujuan               |Memeriksa kelengkapan,prasyarat matkul,dan benturan jadwal pada draf pengajuan KRS
|Aktor Utama            | Sistem
|Sumber Kebutuhan       | SIA-R04
|Pemicu                 | Pengajuan KRS dijalankan oleh Mahasiswa melalui SIA-UC03
|Prasyarat              | Data draf pengajuan KRS dikirimkan oleh SIA-UC03
|Pasca Kondisi Berhasil | Pengajuan KRS dinyatakan valid dan dapat disimpan ke sistam
|Pasca Kondisi Gagal    | Pengajuan KRS dinyatakan tidak valid (ditemukan benturan/ketidaklengkapan)
|Include                | -
|Extension Point        | -
|Extend                 | -
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah     Tindakan Aktor                                Respon Sistem
_________________________________________________________________________________________________________________________
|1          -                           Menerima data draf pengajuan KRS dari SIA-UC03
|2          -                           Memeriksa kelengkapan isi pengajuan
|3          -                           Memeriksa kualifikasi prasyarat mata kuliah
|4          -                           Memeriksa ada atau tidkanya benturan jadwal
|5          -                           Mengembalikan status validasi berhasil ke SIA-UC03
_________________________________________________________________________________________________________________________

3) SIA-UC05 -Unduh Bukti Pengajuan KRS
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC05 - Unduh bukti pengajuan KRS
|Tujuan                 | Menghasilkan berkas bukti pengajuan KRS yang diunduh ke perangakat Mahasiswa
|Aktor Utama            | Mahasiswa 
|Sumber Kebutuhan       | SIA-R05
|Pemicu                 | Mahasiswa memilih opsi unduh bukti pada layar konfirmasi penyimpanan pengajuan
|Prasyarat              | Pengajuan KRS telah berhasil tersimpan (SIA-UC03 berhasil dieksekusi)
|Pasca Kondisi Berhasil | Berkas bukti pengajuan KRS berhasill diunduh
|Pasca Kondisi Gagal    | Berkas bukti pengajuan KRS gagal diunduh
|Include                | -
|Extension Point        | -
|Extend                 | -
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah     Tindakan Mahasiswa                                Respon Sistem
_________________________________________________________________________________________________________________________
|1          Memilih opsi unduh bukti pengajuan     Menerima permintaan unduh berkas
|2          -                                      Membuat dokumen bukti pengajuan KRS
|3          Menerima berkas dokumen                Mengalirkan berkas bukti pengajuan untuk diunduh
_________________________________________________________________________________________________________________________

4) SIA-UC06 - Memproses Keputusan KRS
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC06 - Memproses keputusan KRS
|Tujuan                 | Menetapkan persetujuan atau penolakan pangajuan KRS mahasiswa beserta catatan keputusan
|Aktor Utama            | Dosen Wali 
|Sumber Kebutuhan       | SIA-R06
|Pemicu                 | Dosen Wali memilih pengajuan KRS mahasiswa yang membutuhkan keputusan
|Prasyarat              |Dosen Wali telah terautentikasi terdapat pengajuan KRS berstatus Menunggu persetujuan dosen wali
|Pasca Kondisi Berhasil | Status pengajuan KRS diperbarui menjadi Disetujui atau Ditolak beserta catatn keputusan
|Pasca Kondisi Gagal    | Status pengajuan KRS tidak mengalami perubahan
|Include                | -
|Extension Point        | -
|Extend                 | -
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah     Tindakan Dosen Wali                                        Respon Sistem
_________________________________________________________________________________________________________________________
|1       Membuka daftar pengajuan KRS mahasiswa                  Menampilakn daftar pengajuan KRS
|2       Memilih salah satu draft pengajuan KRS                  Menampilkan rincian pengajuan KRS
|3       Memilih keputusan (Setuju/Tolak) dan mengsisi catatan   Menampung pilihan keputusan dan catatan
|4       Menyimpan Keputusan                                     Memperbarui status pengajuan dan menyimpan catatan
|5       Melihat Konfirmasi                                      Menampilkan pesan konfirmasi keputusan tersimpan
_________________________________________________________________________________________________________________________

5) SIA-UC01 - Mengelola Jadwal
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC01 - Mengelola jadwal kuliah
|Tujuan                 | Menambah, mengubah, atau menghapus data jadwal kuliah
|Aktor Utama            | Admin Akademik
|Sumber Kebutuhan       | SIA-R02
|Pemicu                 | Admin Akademik memilih fungsi pengelolaan jadwal kuliah
|Prasyarat              | Admin Akademik telah terautentikasi data mata kuliah tersedia
|Pasca Kondisi Berhasil | Data jadwal kuliah berhasil diperbarui dan tersimpan
|Pasca Kondisi Gagal    | Data jadwal kuiah tidak mengalami perubahan
|Include                | -
|Extension Point        | -
|Extend                 | -
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah  Tindakan Admin Akademik                               Respon Sistem
_________________________________________________________________________________________________________________________
|1       Membuka menu pengelolaan jadwal kuliah                  Menampilkan halaman daftar dan kelola jadwal
|2       Memilih Aksi(tambah, ubah, atau hapus jadwal)           Menampilkan formulir data jadwal kuliah
|3       Mengisi/memperbarui data jadwal                         Menampung isian data jadwal
|4       Menyimpan data jadwal                                   Memeriksa kelengkapan dan menyimpan perubahan jadwal
|5       Melihat konfirmasi                                  Menampilkan pesan konfirmasi data jadwal berhasil diperbarui
_________________________________________________________________________________________________________________________


6) SIA-UC02 - Melihat Jadwal Kuliah
_________________________________________________________________________________________________________________________
|Element                |                           Keterangan
_________________________________________________________________________________________________________________________
|Element                | SIA-UC02 - Melihat jadwal kuliah
|Tujuan                 | Menampilkan daftar jadwal kuliah yang tersedia untuk semester aktif
|Aktor Utama            | Mahasiswa
|Sumber Kebutuhan       | SIA-R01
|Pemicu                 | Mahasiswa membuka fungsi/menu melihat jadwal kuliah
|Prasyarat              | Mahasiswa telah terautentikasi data jadwal kuliah telah diinput oleh Admin Akademik
|Pasca Kondisi Berhasil | Daftar jadwal kuliah berhasil ditampilkan
|Pasca Kondisi Gagal    | Daftar jadwal kuliah gagal ditampilkan
|Include                | -
|Extension Point        | -
|Extend                 | -
_________________________________________________________________________________________________________________________

Alur Utama :
_________________________________________________________________________________________________________________________
|Langkah     Tindakan Mahasiswa                                Respon Sistem
_________________________________________________________________________________________________________________________
|1          Membuka menu/halaman lihat jadwal kuliah        Menerima permintaan tampilkan jadwal
|2          -                                               Mengambil data jadwal kuliah semester aktif
|3          Melihat daftar jadwal kuliah yang ditampilkan   Menampilkan rincian daftar jadwal kuliah
_________________________________________________________________________________________________________________________

Langkah 7 : Uji Konsistensi

1) Situasi A: Validasi berhasil dan mahasiswa tidak mengunduh bukti :
    Alur Skenario: Mahasiswa menjalankan SIA-UC03 (Ajukan KRS). Sistem secara otomatis memanggil SIA-UC04 (Validasi KRS) melalui relasi <<include>>. Validasi berhasil, sistem menyimpan data KRS dengan status "Menunggu persetujuan dosen wali", dan layar konfirmasi muncul. Mahasiswa tidak mengklik tombol unduh, sehingga SIA-UC05 (Unduh Bukti Pengajuan KRS) tidak dieksekusi.

    Hasil Evaluasi: Diagram dan deskripsi memberikan hasil yang konsisten. Pengajuan KRS tetap sah dan berhasil tersimpan tanpa bergantung pada pelaksanaan SIA-UC05.

2) Situasi B: Validasi gagal :
    Alur Skenario: Mahasiswa menjalankan SIA-UC03. Sistem memanggil SIA-UC04. Ditemukan pelanggaran aturan (misalnya jadwal bentrok atau prasyarat belum terpenuhi). Sistem membatalkan penyimpanan KRS dan menampilkan pesan kesalahan melalui alur alternatif. Extension point tidak pernah tercapai, sehingga SIA-UC05 tidak dipicu.

    Hasil Evaluasi: Diagram dan deskripsi memberikan hasil yang konsisten. Pengajuan KRS belum berhasil tersimpan dan alur berhenti sesuai batasan sistem.

3) Situasi C: Validasi berhasil dan mahasiswa memilih mengunduh bukti :
    Alur Skenario: Mahasiswa menjalankan SIA-UC03. Sistem memanggil SIA-UC04 dan validasi dinyatakan berhasil. Data KRS tersimpan. Pada layar konfirmasi (extension point), mahasiswa memilih opsi unduh bukti. Relasi <<extend>> memicu SIA-UC05 sehingga berkas bukti pengajuan berhasil diunduh.

    Hasil Evaluasi: Diagram dan deskripsi memberikan hasil yang konsisten. Pengajuan KRS tersimpan dan berkas bukti pengajuan berhasil terunduh.

Pernyataan Konsistensi :
Diagram dan deskripsi memberikan hasil yang 100% konsisten untuk ketiga situasi di atas. Relasi <<include>> memastikan validasi selalu berjalan pada setiap pengajuan, sedangkan relasi <<extend>> memastikan pengunduhan bukti bersifat opsional dan tidak memengaruhi keberhasilan penyimpanan KRS.
