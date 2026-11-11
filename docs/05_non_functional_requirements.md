# 05 Non-Functional Requirements

Tabel berikut mencantumkan kebutuhan non-fungsional untuk aplikasi SALATIFY:

| Kode | Kategori | Penjelasan |
|------|----------|------------|
| NFR-01 | Keamanan | Aplikasi harus melindungi data pengguna dengan mekanisme enkripsi password yang baik. Password pengguna harus di-hash sebelum disimpan di database SQLite. Data sesi login harus dilindungi terhadap akses tidak authorized. |
| NFR-02 | Kemudahan Penggunaan | Antarmuka aplikasi harus intuitif dan mudah dipahami pengguna dengan berbagai level pengalaman teknologi. Alur navigasi harus konsisten throughout seluruh fitur. Terdampingan dengan bantuan/tooltip untuk fitur pertama kalinya. |
| NFR-03 | Performa | Aplikasi harus diluncurkan dalam waktu kurang dari 3 detik. Waktu respons terhadap interaksi pengguna (tapped, scroll) tidak boleh melebihi 1 detik. Penampilan jadwal sholat harus segera muncul setelah lokasi dideteksi. |
| NFR-04 | Keandalan | Aplikasi harus berfungsi dengan uptime minimal 98% selama periode 24 jam. Jadwal sholat harus selalu akurat sesuai dengan koordinat lokasi. Sistem penyeapan pengingat harus bekerja tanpa gagal sesuai waktu yang diatur. |
| NFR-05 | Kompatibilitas | Aplikasi harus kompatibel dengan Android versi 5.0 (Lollipop) dan yang lebih baru. Aplikasi harus dapat berjalan pada berbagai ukuran layar smartphone dan tablet. Tested pada minimal 3 merk smartphone berbeda (Samsung, Xiaomi, dan Sony). |
| NFR-06 | Privasi | Aplikasi harus mematuhi regulasi privasi data (seperti UU PDP). Lokasi pengguna harus tidak disimpan ke server pihak ketiga tanpa izin. Pengguna harus diberitahu tentang data yang dikoleksi melalui kebijakan privasi. Pengguna dapat menonaktifkan akses GPS kapan saja. |
| NFR-07 | Pemeliharaan Sistem | Aplikasi harus dirancang agar mempermudah pembaruan konten (wirid, dzikir, doa) tanpa perlu merilis versi aplikasi baru. Database SQLite harus didesain untuk migrasi yang mudah. Log error harus dicatat untuk mempermudah debugging tim pengembang. |
| NFR-08 | Ukuran Aplikasi | Ukuran aplikasi setelah di-build harus tidak melebihi 50 MB untuk memudahkan unduhan dan instalasi. Resource (gambar, audio) harus di-optimalkan sebelum dimasukkan ke aplikasi. |
| NFR-09 | Konsumsi Daya | Aplikasi harus minim mengonsumsi baterai perangkat. Fungsi GPS harus dinonaktifkan atau di-restrict ketika aplikasi running di background tidak aktif. Pemicu pengingat harus efisien tanpa mempertahankan proses berjalan terus-menerus. |
| NFR-10 | Kepelurusan Data | Data jadwal sholat, doa, dan wirid harus konsisten di seluruh versi aplikasi. Perubahan data konten harusiversi terbaru setelah sinkronisasi. Data lokal pengguna (favorit, riwayat) harus selamat mes aplikasi diinstal ulang. |

*Total 10 kategori kebutuhan non-fungsional teridentifikasi untuk menjamin kualitas aplikasi SALATIFY.*