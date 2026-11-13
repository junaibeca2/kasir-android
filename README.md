# Kasir Toko Offline untuk Android

APK kasir mandiri untuk tablet Android. Aplikasi ini tidak membuka website, tidak memerlukan XAMPP atau koneksi internet, dan menyimpan data di database SQLite privat pada perangkat. Data di versi Android terpisah dari database PHP `web_kasir` di PC; perubahan di satu versi tidak otomatis muncul di versi lain.

## Fitur

- Setup akun super admin pertama kali tanpa kata sandi bawaan.
- Login super admin dan karyawan dengan kata sandi yang di-hash PBKDF2-HMAC-SHA256.
- Super admin mengelola menu, karyawan, laporan, identitas toko, logo, alamat, nomor HP, dan catatan struk.
- Karyawan membuat/mengedit pesanan dan mencetak struk; endpoint lokal tetap memeriksa peran, jadi akses laporan/pengelolaan bukan sekadar disembunyikan dari menu.
- Pesanan menyimpan snapshot nama dan harga menu.
- Logo JPG/PNG/WebP disimpan lokal dan tampil di bagian atas struk.
- Database SQLite berada di ruang privat aplikasi Android. Aplikasi tidak meminta izin internet.

## APK

APK debug yang dapat dipasang di tablet akan dibuat di:

```text
app\build\outputs\apk\debug\app-debug.apk
```

Salin APK ke tablet, buka berkasnya, lalu izinkan pemasangan dari sumber yang dipilih jika Android memintanya. APK debug ditandatangani dengan kunci pengembangan Gradle, bukan kunci rilis Google Play.

## Build ulang di Windows

Toolchain yang digunakan: Android Studio JBR, Android SDK Platform 36, Build Tools 36.0.0, dan Gradle 9.1.0.

```bat
gradlew.bat testDebugUnitTest

gradlew.bat assembleDebug
```

Minimum Android: API 23 (Android 6.0). Untuk melihat versi Android tablet, buka Settings → About tablet.

## Mulai di tablet

1. Pasang dan buka APK.
2. Buat super admin lokal dengan kata sandi pilihan sendiri.
3. Dari menu **Pengaturan**, isi nama toko, alamat, nomor HP, logo, dan catatan struk.
4. Tambahkan menu, lalu buat akun karyawan bila dibutuhkan.
5. Buat pesanan dan tekan **Cetak struk**. Pilih printer thermal/Bluetooth yang sudah dipasangkan dengan tablet.

Uninstall aplikasi Android akan menghapus database lokalnya. Buat salinan data secara teratur sebelum mengganti atau menghapus aplikasi.
