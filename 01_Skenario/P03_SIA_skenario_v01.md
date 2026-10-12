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

____________________________________________________________________________________________
            Aktor      |                      Tujuan terhadap sistem                        |
____________________________________________________________________________________________
Mahasiswa              | Melihat jadwal kuliah                                                              |
Dosen Wali             | Memproses Keputusan Persetujuan atau Penolakan KRS, serta memberikan catatn keputusan
Admin Akademik         | Mengelola jadwal kuliah                                                            |
____________________________________________________________________________________________

ID Use Case      Nama Use Case                  Aktor Terkait              Sumber Kebutuhan
UC-01           Melihat jadwal kuliah           Mahasiswa                   SIA-R01
UC-02           Mengelola jadwal kuliah         Admin Akademik              SIA-R02
UC-03           Mengajukan KRS                  Mahasiswa                   SIA-R03
UC-04           Memvalidasi KRS                 - di include oleh UC-03     SIA-R04
UC-05           Mengunduh bukti Pengajuan KRS   Mahasiswa                   SIA-R05
UC-06           Memproses Keputusan KRS         Dosen Wali                  SIA-R06
