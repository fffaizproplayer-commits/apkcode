# Izz Code APK

Aplikasi Android berbasis WebView yang memuat website langsung dari server. Semua perubahan di web otomatis tampil di aplikasi tanpa perlu build atau update APK lagi. APK hanya perlu dibuat ulang kalau mengubah kode aplikasinya (ikon, nama, URL).

## Build lewat GitHub

1. Push folder ini ke repo GitHub.
2. Buka tab Actions, jalankan workflow `Build APK` (atau otomatis jalan saat push).
3. Unduh `izz-code-apk` dari bagian Artifacts.

Tanpa keystore sendiri, APK ditandatangani dengan debug key sehingga tetap bisa dipasang. Untuk tanda tangan sendiri, isi secrets `KEYSTORE_BASE64`, `KEYSTORE_PASSWORD`, `KEY_ALIAS`, dan `KEY_PASSWORD`.

## Ganti URL website

Ubah `SITE_URL` di `gradle.properties`, dan host pada `intent-filter` di `app/src/main/AndroidManifest.xml`. Bisa juga lewat input `site_url` saat menjalankan workflow manual.

## Fitur

- Memuat website penuh, cookie login admin tersimpan
- Tarik ke bawah untuk refresh, tombol kembali mengikuti riwayat halaman
- Upload gambar (thumbnail, avatar) lewat pemilih file
- Unduhan file lewat Download Manager
- Link luar (WhatsApp, Telegram, TikTok) dibuka di aplikasi masing-masing
- Halaman offline dengan tombol coba lagi

## Build lokal

Butuh JDK 17 dan Android SDK, lalu jalankan `gradle assembleRelease`.
