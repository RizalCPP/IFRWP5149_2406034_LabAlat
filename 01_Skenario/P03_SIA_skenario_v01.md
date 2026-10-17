Langkah 1 : Catat Kebutuhan dan Batas

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap 
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, 
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, 
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen 
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih 
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS 
dan memberikan catatan keputusan. 

ID                      Kebutuhan tugas 
SIA-R01         Mahasiswa dapat melihat jadwal kuliah 
SIA-R02         Admin akademik dapat mengelola jadwal kuliah 
SIA-R03         Mahasiswa dapat mengajukan KRS 
SIA-R04         Sistem memvalidasi KRS sebagai bagian pengajuan 
SIA-R05         Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi Pengajuan
SIA-R06         Dosen wali dapat memproses persetujuan atau penolakan KRS

Batas dan asumsi: 
• Pengguna telah terautentikasi. 
• Data mata kuliah, prasyarat, dan jadwal tersedia. 
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan. 
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan. 
• KRS tersimpan belum berarti disetujui. 
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar 
tugas.

Langkah 2 : Identifikasi Aktor dan Use Case

Katalog Aktor :
__________________________________________________________________________________________________________________
            Aktor      |                      Tujuan terhadap sistem                                              |
__________________________________________________________________________________________________________________
Mahasiswa              | Melihat jadwal kuliah                                                                    |
Dosen Wali             | Memproses Keputusan Persetujuan atau Penolakan KRS, serta memberikan catatn keputusan    |
Admin Akademik         | Mengelola jadwal kuliah                                                                  |
__________________________________________________________________________________________________________________

Katalog Use Case :
____________________________________________________________________________________________
ID Use Case      Nama Use Case                  Aktor Terkait              Sumber Kebutuhan |
____________________________________________________________________________________________
UC-01           Mengelola jadwal kuliah jadwal  Admin Akademik              SIA-R02         |
UC-02           Melihat jadwal kuliah           Mahasiswa                   SIA-R01         |
UC-03           Mengajukan KRS                  Mahasiswa                   SIA-R03         |
UC-04           Memvalidasi KRS                 Sistem                      SIA-R04         |
UC-05           Mengunduh bukti Pengajuan KRS   Mahasiswa                   SIA-R05         |
UC-06           Memproses Keputusan KRS         Dosen Wali                  SIA-R06         |
_____________________________________________________________________________________________

Langkah 3 : Menentukan Include

1) Use Case Utama   : UC-03 (Mengajukan KRS)
2) Use Case Terikut : UC-04 (Memvalidasi KRS)
3) Arah Relasi      : UC-03 <<include>> UC-04
Alasan: Setiap pengajuan KRS secara otomatis memicu eksekusi validasi kelengkapan, prasyarat, dan benturan jadwal. Pengajuan KRS nggak bisa selesai tanpa melewati validasi ini.

Langkah 4 : Menentukan Extend

1) Use Case Dasar   : UC-03 (Mengajukan KRS)
2) Use Case Tambahan: UC-05 (Mengunduh Bukti Pengajuan KRS)
3) Arah Relasi      : UC-05 <<extend>> UC-03
4) Extension Point  : Konfirmasi Penyimpanan
5) Kondisi          : Mahasiswa memilih opsi unduh bukti pada layar konfirmasi setelah KRS berhasil tersimpan.
Alasan: Fitur unduh bukti bersifat opsional dan nggak menentukan sukses atau gagalnya proses pengajuan KRS.

