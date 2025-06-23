---
title:   Struktur Direktori Umum
isChild: true
anchor:  common_directory_structure
---

## Struktur Direktori Umum {#common_directory_structure_title}

Pertanyaan umum di antara mereka yang baru mulai menulis program untuk web adalah, "di mana saya meletakkan barang-barang saya?" Selama bertahun-tahun, jawaban ini secara konsisten adalah "di mana `DocumentRoot` berada." Meskipun jawaban ini tidak lengkap, ini adalah tempat yang bagus untuk memulai.

Demi alasan keamanan, berkas konfigurasi tidak boleh diakses oleh pengunjung situs; oleh karena itu, skrip publik disimpan dalam direktori publik dan konfigurasi serta data pribadi disimpan di luar direktori tersebut.

Untuk setiap tim, CMS, atau kerangka kerja tempat seseorang bekerja, struktur direktori standar digunakan oleh masing-masing entitas tersebut. Namun, jika seseorang memulai proyek sendirian, mengetahui struktur sistem berkas mana yang akan digunakan bisa jadi sulit.

[Paul M. Jones] telah melakukan beberapa penelitian fantastis tentang praktik umum puluhan ribu proyek github di ranah PHP. Ia telah menyusun struktur berkas dan direktori standar, [Standard PHP Package Skeleton], berdasarkan penelitian ini. Dalam struktur direktori ini, `DocumentRoot` harus mengarah ke `public/`, pengujian unit harus berada di direktori `tests/`, dan pustaka pihak ketiga, sebagaimana diinstal oleh [composer], berada di direktori `vendor/`. Untuk berkas dan direktori lain, mematuhi [Standard PHP Package Skeleton] akan lebih masuk akal bagi kontributor proyek.

[Paul M. Jones]: https://paul-m-jones.com/
[Standard PHP Package Skeleton]: https://github.com/php-pds/skeleton
[Composer]: /#composer_and_packagist
