---
title:   Composer dan Packagist
isChild: true
anchor:  composer_and_packagist
---

## Composer dan Packagist {#composer_and_packagist_title}

Composer adalah pengelola dependensi yang direkomendasikan untuk PHP. Cantumkan dependensi proyek Anda dalam file `composer.json` dan,
dengan beberapa perintah sederhana, Composer akan secara otomatis mengunduh dependensi proyek Anda dan menyiapkan pemuatan otomatis (_autoloader_) 
untuk Anda. Composer serupa dengan NPM di dunia node.js, atau Bundler di dunia Ruby.

Ada banyak sekali pustaka PHP yang kompatibel dengan Composer dan siap digunakan dalam proyek Anda. "Paket-paket" ini tercantum di [Packagist], 
repositori resmi untuk pustaka PHP yang kompatibel dengan Composer.

### Bagaimana Cara Menginstal Composer

Cara paling aman untuk mengunduh composer adalah dengan [mengikuti petunjuk resmi](https://getcomposer.org/download/).
Ini akan memverifikasi bahwa penginstal tidak rusak atau dirusak.
Penginstal menginstal biner `composer.phar` di _direktori kerja Anda saat ini_.

Kami sarankan untuk menginstal Composer *secara global* (misalnya satu salinan di `/usr/local/bin`). Untuk melakukannya, jalankan perintah berikut:

{% highlight console %}
mv composer.phar /usr/local/bin/composer
{% endhighlight %}

**Catatan:** Jika hal di atas gagal karena izin akses, beri awalan dengan `sudo`.

Untuk menjalankan Composer yang terinstal secara lokal Anda akan menggunakan `php composer.phar`, secara global cukup `composer`.

#### Instalasi di Windows

Bagi pengguna Windows, cara termudah untuk memulai dan menjalankannya adalah dengan menggunakan penginstal [ComposerSetup], yang
melakukan instalasi global dan menyiapkan `$PATH` sehingga Anda dapat memanggil `composer` dari direktori mana pun di baris perintah Anda.

### Bagaimana Cara Mendefinisikan dan Menginstal Ketergantungan

Composer melacak dependensi proyek Anda dalam sebuah berkas bernama `composer.json`. Anda dapat mengelolanya
secara manual jika Anda suka, atau menggunakan Composer itu sendiri. Perintah `composer require` menambahkan dependensi proyek
dan jika Anda tidak memiliki berkas `composer.json`, satu berkas akan dibuat. Berikut ini contoh yang menambahkan [Twig]
sebagai dependensi proyek Anda.

{% highlight console %}
composer require twig/twig:^2.0
{% endhighlight %}

Atau, perintah `composer init` akan memandu Anda membuat file `composer.json` lengkap
untuk proyek Anda. Apa pun caranya, setelah Anda membuat file `composer.json`, Anda dapat memberi tahu Composer untuk
mengunduh dan memasang ketergantungan (_dependency_) Anda ke direktori `vendor/`. Ini juga berlaku untuk proyek
yang telah Anda unduh yang sudah menyediakan file `composer.json`:

{% highlight console %}
composer install
{% endhighlight %}

Berikutnya, tambahkan baris ini ke berkas PHP utama aplikasi Anda; 
ini akan memberi tahu PHP untuk menggunakan autoloader Composer bagi ketergantungan (_dependency_) proyek Anda.

{% highlight php %}
<?php
require 'vendor/autoload.php';
{% endhighlight %}

Now you can use your project dependencies, and they'll be autoloaded on demand.
Sekarang Anda dapat menggunakan ketergantungan (_dependency_) proyek Anda, dan ketergantungan tersebut akan dimuat otomatis sesuai permintaan.

### Memperbarui ketergantungan Anda

Composer membuat berkas bernama `composer.lock` yang menyimpan versi persis setiap paket yang diunduh 
saat Anda pertama kali menjalankan `composer install`. Jika Anda berbagi proyek dengan orang lain, 
pastikan berkas `composer.lock` disertakan, sehingga saat mereka menjalankan `composer install`, 
mereka akan mendapatkan versi yang sama dengan Anda. Untuk memperbarui dependensi, jalankan `composer update`. 
Jangan gunakan `composer update` saat melakukan deploy, cukup gunakan `composer install`, jika tidak, 
Anda mungkin akan mendapatkan versi paket yang berbeda saat produksi.

Ini sangat berguna saat Anda menentukan persyaratan versi secara fleksibel. Misalnya, persyaratan versi `~1.8` 
berarti "apa pun yang lebih baru dari `1.8.0`, tetapi kurang dari `2.0.x-dev`". 
Anda juga dapat menggunakan karakter pengganti `*` seperti pada `1.8.*`. Sekarang perintah `composer update` Composer 
akan memutakhirkan semua dependensi Anda ke versi terbaru yang sesuai dengan batasan yang Anda tetapkan.

### Pemberitahuan Pembaruan

Untuk menerima pemberitahuan tentang rilis versi baru, Anda dapat mendaftar ke [libraries.io], sebuah layanan web
yang dapat memantau dependensi dan mengirimkan peringatan tentang pembaruan.

### Memeriksa ketergantungan Anda untuk masalah keamanan

[Pemeriksa Keamanan PHP Lokal] adalah alat baris perintah yang akan memeriksa berkas `composer.lock` Anda 
dan memberi tahu Anda jika Anda perlu memperbarui salah satu dependensi.

### Menangani dependensi global dengan Composer

Composer can also handle global dependencies and their binaries. Usage is straight-forward, all you need
to do is prefix your command with `global`. If for example you wanted to install PHPUnit and have it
available globally, you'd run the following command:

Composer juga dapat menangani dependensi global dan binernya. Penggunaannya mudah, yang perlu Anda lakukan hanyalah 
mengawali perintah Anda dengan `global`. Misalnya, jika Anda ingin menginstal PHPUnit dan membuatnya tersedia secara global, Anda akan menjalankan perintah berikut:

{% highlight console %}
composer global require phpunit/phpunit
{% endhighlight %}

Ini akan membuat folder `~/.composer` tempat dependensi global Anda berada. Agar biner paket yang terinstal tersedia di mana-mana, Anda kemudian akan menambahkan folder `~/.composer/vendor/bin` ke variabel `$PATH` Anda.

* [Learn about Composer]

[Packagist]: https://packagist.org/
[Twig]: https://twig.symfony.com/
[libraries.io]: https://libraries.io/
[Local PHP Security Checker]: https://github.com/fabpot/local-php-security-checker
[Learn about Composer]: https://getcomposer.org/doc/00-intro.md
[ComposerSetup]: https://getcomposer.org/Composer-Setup.exe
