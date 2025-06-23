---
title:   Pengaturan di macOS
isChild: true
anchor:  mac_setup
---

## Pengaturan di macOS {#mac_setup_title}

macOS 12 (Monterey) dan yang lebih baru tidak disertai PHP. macOS versi sebelumnya menyertakan PHP tetapi lebih 
lambat dari rilis stabil terbaru. Ada beberapa cara untuk menginstal versi PHP terbaru di macOS.

### Instal PHP melalui Homebrew

[Homebrew] adalah pengelola paket untuk macOS yang membantu Anda menginstal PHP dan berbagai ekstensi dengan mudah. 
​​Repositori inti Homebrew menyediakan "formulae" untuk PHP 8.1, 8.2, 8.3, dan 8.4. Instal versi terbaru dengan perintah ini:

```
brew install php
```

Anda dapat beralih di antara versi PHP Homebrew dengan memodifikasi variabel `PATH` Anda. 
Atau, Anda dapat menggunakan [brew-php-switcher][brew-php-switcher] untuk beralih versi PHP secara otomatis.

Anda juga dapat beralih antar versi PHP secara manual dengan memutuskan tautan (_unlink_) dan menautkan (_link_) versi yang diinginkan:

```
brew unlink php
brew link --overwrite php@8.2
```

```
brew unlink php
brew link --overwrite php@8.3
```

### Instal PHP melalui Macports

Proyek [MacPorts] merupakan inisiatif komunitas sumber terbuka untuk merancang sistem yang mudah digunakan 
untuk mengkompilasi, menginstal, dan memutakhirkan perangkat lunak sumber terbuka (_open source_) berbasis baris perintah (_command line_), X11, atau Aqua pada sistem operasi macOS.

MacPorts mendukung biner yang telah dikompilasi sebelumnya, jadi Anda tidak perlu mengkompilasi ulang setiap
ketergantungan dari berkas tarball sumber, ini akan menyelamatkan hidup Anda jika Anda tidak
memiliki paket apa pun yang terinstal di sistem Anda.

Pada titik ini, Anda dapat menginstal `php54`, `php55`, `php56`, `php70`, `php71`, `php72`, `php73`, `php74`, `php80`, `php81`, `php82` atau `php83` menggunakan perintah `port install`, misalnya:

    sudo port install php74
    sudo port install php83

Dan Anda dapat menjalankan perintah `select` untuk mengganti PHP aktif Anda:

    sudo port select --set php php83

### Instal PHP melalui phpbrew

[phpbrew] adalah alat untuk menginstal dan mengelola beberapa versi PHP. Ini bisa sangat berguna 
jika dua aplikasi/proyek yang berbeda memerlukan versi PHP yang berbeda, dan Anda tidak menggunakan mesin virtual.

### Instal PHP melalui penginstal biner Liip

Pilihan populer lainnya adalah [php-osx.liip.ch] yang menyediakan metode instalasi satu baris untuk versi 5.3 hingga 7.3.
Ia tidak menimpa biner PHP yang diinstal oleh Apple, tetapi menginstal semuanya di lokasi terpisah (/usr/local/php5).

### Kompilasi dari Sumber

Pilihan lain yang memberi Anda kendali atas versi PHP yang Anda instal adalah [kompilasi sendiri][mac-compile].
Dalam hal ini, pastikan Anda telah menginstal [Xcode][xcode-gcc-substitution] atau pengganti Apple
["Command Line Tools for XCode"] yang dapat diunduh dari Pusat Pengembang Apple.

### All-in-One Installer

Solusi yang tercantum di atas terutama menangani PHP itu sendiri, dan tidak menyediakan hal-hal seperti 
[Apache][apache], [Nginx][nginx] atau server SQL. Solusi "all-in-one" seperti [MAMP][mamp-downloads] 
dan [XAMPP][xampp] akan menginstal perangkat lunak lain ini untuk Anda dan menggabungkan semuanya, 
tetapi kemudahan pengaturan disertai dengan fleksibilitas.

[Homebrew]: https://brew.sh/
[MacPorts]: https://www.macports.org/install.php
[phpbrew]: https://github.com/phpbrew/phpbrew
[php-osx.liip.ch]: https://web.archive.org/web/20220505163210/https://php-osx.liip.ch/
[mac-compile]: https://www.php.net/install.macosx.compile
[xcode-gcc-substitution]: https://github.com/kennethreitz/osx-gcc-installer
["Command Line Tools for XCode"]: https://developer.apple.com/downloads
[apache]: https://httpd.apache.org/
[nginx]: https://www.nginx.com/
[mamp-downloads]: https://www.mamp.info/en/downloads/
[xampp]: https://www.apachefriends.org/
[brew-php-switcher]: https://github.com/philcook/brew-php-switcher
