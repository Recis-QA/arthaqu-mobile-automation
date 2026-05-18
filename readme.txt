arthaqu-mobile-automation
=========================

Project ini berisi script automation mobile Android untuk aplikasi Arthaqu menggunakan Maestro Studio versi 0.9.1.


Struktur Folder
---------------

arthaqu-mobile-automation/
|
|-- data/
|   |-- env/
|       |-- devel.yaml
|       |-- prod.yaml
|
|-- flows/
|   |-- 01_halaman_login/
|   |   |-- daftar/
|   |   |   |-- daftar.yaml
|   |   |-- login/
|   |       |-- login.yaml
|   |
|   |-- 05_profil/
|   |   |-- akun/
|   |   |-- keamanan/
|   |   |-- tentang/
|   |   |-- keluar.yaml
|   |
|   |-- support/
|       |-- pendukung_login/
|       |-- pendukung_start_aplikasi/
|
|-- subflows/
|   |-- auth/
|   |-- daftar/
|   |-- keamanan/
|   |-- start_aplikasi.yaml
|
|-- landing_page/
|-- .maestro/
|-- .gitignore
|-- readme.txt


Fungsi Folder
-------------

data/env/
Berisi konfigurasi environment yang dipakai saat menjalankan test, seperti APP_ID, akun testing, PIN, data registrasi, dan pilihan OTP.


flows/
Berisi test case utama atau skenario end-to-end yang dijalankan langsung dari Maestro Studio.

Contoh:
- flows/01_halaman_login/login/login.yaml
- flows/01_halaman_login/daftar/daftar.yaml
- flows/05_profil/keluar.yaml


flows/01_halaman_login/
Berisi skenario untuk halaman login dan daftar.

- daftar/ untuk flow registrasi akun.
- login/ untuk flow masuk ke aplikasi.


flows/05_profil/
Berisi skenario yang berhubungan dengan menu profil.

- akun/ untuk flow data akun, referral, spanduk, dan ubah profil.
- keamanan/ untuk flow pengaturan keamanan, ubah PIN, dan ubah password.
- tentang/ untuk flow informasi aplikasi, kebijakan privasi, syarat dan ketentuan, dan hapus akun.
- keluar.yaml untuk flow logout.


flows/support/
Berisi script pendukung atau handler yang dipanggil oleh flow utama.

Contoh penggunaan:
- handle landing page saat pertama membuka aplikasi.
- handle permission Android.
- handle product tour.
- handle kondisi wajib ubah PIN atau password.


subflows/
Berisi reusable action atau keyword yang dapat dipakai berulang oleh beberapa flow.

Contoh:
- subflows/start_aplikasi.yaml untuk membuka aplikasi dan menjalankan handler awal.
- subflows/auth/do_login.yaml untuk proses input username dan password.
- subflows/auth/do_logout.yaml untuk proses logout.
- subflows/daftar/ untuk action reusable pada proses registrasi.
- subflows/keamanan/ untuk action reusable terkait PIN dan keamanan.


landing_page/
Berisi aset gambar landing page sebagai referensi dokumentasi atau pembanding visual.


.maestro/
Berisi hasil runtime Maestro, seperti screenshot hasil test. Folder ini tidak perlu diupload ke repository.


Catatan Penempatan Script
-------------------------

- Jika membuat skenario test utama, simpan di folder flows sesuai fitur.
- Jika membuat action yang akan dipakai berulang, simpan di folder subflows.
- Jika membuat handler kondisi khusus, simpan di folder flows/support.
- Jika membuat data konfigurasi environment, simpan di data/env.
