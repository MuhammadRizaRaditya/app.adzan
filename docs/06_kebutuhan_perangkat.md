# 06 Kebutuhan Perangkat

## 6.1 Kebutuhan Perangkat Pengembangan

Berikut adalah spesifikasi perangkat keras dan lunak yang diperlukan untuk pengembangan aplikasi SALATIFY:

### Perangkat Keras (Hardware)
- **Processor**: Minimum 4 GB RAM dan prosesor multi-core (disarankan i5 atau equivalente)
- **Memori Disk**: Minimal 2 GB ruang kosong untuk instalasi tools dan dependensi
- **Device Target**: Smartphone Android dengan CPU sekurang-kurangnya 1.5 GHz dan Android 5.0+
- **Koneksi Internet**: Required untuk mengunduh dependensi, library, dan resources during development

### Perangkat Lunak (Software)
- **Operating System**: Windows 10/11 (64-bit), macOS 10.15+, atau Linux (Ubuntu 20.04+)
- **Python Version**: Python 3.9 atau versi terbaru (3.x)
- **Kivy**: Versi 2.1.0 atau lebih baru
- **KivyMD**: Versi terbaru yang kompatibel dengan Kivy
- **SQLite**: Tersedia secara bawaan di Python (tidak perlu install eksternal)
- **SQLAlchemy**: Versi 2.0 atau lebih baru (untuk ORM jika diperlukan)
- **Buildozer**: Untuk membundle aplikasi menjadi APK (diperlukan untuk target Android)
- **Pyjnius**: Library Python untuk mengakses kode Java dari Android (bawaan Kivy)
- **Plyer**: Library untuk mengakses fitur hardware Android (GPS, kompas, notifikasi)
- **Requests**: Library untuk menghubungi API jika diperlukan (untuk konten tambahan)

## 6.2 Kebutuhan Perangkat Pengguna (Target Device)

### Perangkat Keras (Hardware)
- **Smartphone Android** dengan spesifikasi minimum:
  - GPS receiver (wajib untuk fitur lokasi dan kiblat)
  - Kompas magnetometer (wajib untuk fitur arah kiblat)
  - Gyroscope (opsional, untuk perbaikan akurasi orientasi)
  - Minimal 1 GB RAM (disarankan 2 GB atau lebih)
  - Layar: Minimal 480 x 800 pixel, disarankan HD (720 x 1280) ke atas
  - Speaker (untuk pemutaran audio murottal)
  - Headphone jack atau Bluetooth (opsional untuk pengalaman membaca)

### Perangkat Lunak (Software)
- **Sistem Operasi**: Android 5.0 (Lollipop) atau versi terbaru
- **Versi Kivy**: Aplikasi harus bisa berjalan pada environment Kivy yang terinstall
- **Database**: SQLite sudah bawaan Android, tidak perlu instalasi terpisah
- **Akses Internet**: Required untuk unduhan pertama konten, opsional untuk konten offline

## 6.3 Teknologi yang Direncanakan

Teknologi yang digunakan dalam pengembangan SALATIFY:

| Kategori | Teknologi | Fungsi |
|----------|-----------|--------|
| Bahasa Pemrograman | Python | Logika aplikasi dan pemrosesan data |
| Framework UI | Kivy | Fondasi framework cross-platform |
| UI Components | KivyMD | Komponen UI modern sesuai desain Material |
| Database | SQLite | Penyimpanan data lokal di perangkat |
| ORM | SQLAlchemy | (Opsional) Mapping objek-relasi untuk data |
| Build Tool | Buildozer | Mengkompilasi Python menjadi APK Android |
| Android API Access | Pyjnius | Akses fitur native Android dari Python |
| Hardware Access | Plyer | GPS, kompas, notifikasi, dan sensor lain |
| HTTP Client | Requests | Kommunikasi dengan API jika diperlukan |

*Cataph: Aplikasi dirancang sebagai Android App native melalui Buildozer, bukan website atau aplikasi berbrowser.*