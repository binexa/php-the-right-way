---
title  : Pengaturan di Linux
isChild: true
anchor :  linux_setup
---

## Pengaturan di Linux {#linux_setup_title}

Sebagian besar distribusi GNU/Linux menyertakan PHP yang tersedia dari repositori resmi, tetapi paket-paket tersebut biasanya sedikit tertinggal dari versi stabil saat ini. Ada beberapa cara untuk mendapatkan versi PHP yang lebih baru pada distribusi tersebut.

### Distribusi Berbasis Ubuntu

Pada distribusi GNU/Linux berbasis Ubuntu dan Debian, misalnya, alternatif terbaik untuk paket asli disediakan dan dikelola oleh [Ondřej Surý][Ondrej Sury Blog], melalui Arsip Paket Pribadi (PPA) miliknya di Ubuntu dan DPA/bikeshed di Debian. Temukan petunjuk untuk masing-masing di bawah ini.

Untuk distribusi Ubuntu, [PPA oleh Ondřej Surý][Ondrej Sury PPA] menyediakan versi PHP yang didukung beserta banyak ekstensi PECL. Untuk menambahkan PPA ini ke sistem Anda, lakukan langkah-langkah berikut di terminal Anda:

1. Pertama, tambahkan PPA ke sumber perangkat lunak sistem Anda menggunakan perintah:

   ```bash
   sudo add-apt-repository ppa:ondrej/php
   ```

2. Setelah menambahkan PPA, perbarui daftar paket sistem Anda:

   ```bash
   sudo apt update
   ```

Ini akan memastikan bahwa sistem Anda dapat mengakses dan menginstal paket PHP terbaru yang tersedia di PPA.

### Distribusi Berbasis Debian

Untuk distribusi berbasis Debian, Ondřej Surý juga menyediakan [bikeshed][bikeshed] (padanan Debian untuk PPA). 
Untuk menambahkan bikeshed ke sistem Anda dan memperbaruinya, ikuti langkah-langkah berikut:

1. Pastikan Anda memiliki akses root. Jika tidak, Anda mungkin perlu menggunakan `sudo` untuk perintah berikut.

2. Perbarui daftar paket sistem Anda:

   ```bash
   sudo apt-get update
   ```

3. Instal `lsb-release`, `ca-certificates`, dan `curl`:

   ```bash
   sudo apt-get -y install lsb-release ca-certificates curl
   ```

4. Unduh kunci penandatanganan untuk repositori:

   ```bash
   sudo curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
   ```

5. Tambahkan repositori ke sumber perangkat lunak sistem Anda:

   ```bash
   sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'
   ```

6. Terakhir, perbarui lagi daftar paket sistem Anda:

   ```bash
   sudo apt-get update
   ```

Dengan langkah-langkah ini, sistem Anda akan dapat menginstal paket PHP terbaru dari bikeshed.

### Distribusi Berbasis RPM

Pada distribusi berbasis RPM (CentOS, Fedora, RHEL, dll.) Anda dapat menggunakan [repositori RPM Remi][remi-repo] untuk menginstal versi PHP terbaru atau menyediakan beberapa versi PHP secara bersamaan.

Tersedia [wizard konfigurasi][remi-wizard] untuk mengonfigurasi distribusi berbasis RPM Anda.

Meski begitu, Anda selalu dapat menggunakan kontainer atau mengompilasi kode sumber PHP dari awal.

[Ondrej Sury Blog]: https://deb.sury.org/
[Ondrej Sury PPA]: https://launchpad.net/~ondrej/+archive/ubuntu/php
[bikeshed]: https://packages.sury.org/php/
[remi-repo]: https://rpms.remirepo.net/
[remi-wizard]: https://rpms.remirepo.net/wizard/
