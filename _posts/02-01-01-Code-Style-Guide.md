---
title : Panduan Gaya Penulisan Kode
anchor: code_style_guide
---

# Panduan Gaya Penulisan Kode {#code_style_guide_title}

Komunitas PHP sangat besar dan beragam, terdiri dari pustaka (_libraries_), kerangka kerja (_frameworks_), 
dan komponen (_compinents_) yang tak terhitung banyaknya. Pengembang PHP biasanya memilih beberapa di antaranya 
dan menggabungkannya menjadi satu proyek. Penting agar kode PHP mengikuti (sedekat mungkin) gaya penulisan kode umum (_common code style_)
agar pengembang dapat dengan mudah mencampur dan mencocokkan berbagai pustaka untuk proyek mereka.

[Framework Interop Group][fig] telah mengusulkan dan menyetujui serangkaian rekomendasi gaya. 
Tidak semuanya terkait dengan gaya penulisan kode, tetapi yang terkait adalah [PSR-1][psr1], [PSR-12][psr12], [PSR-4][psr4] 
dan [PER Coding Style][per-cs]. Rekomendasi ini hanyalah seperangkat aturan yang diadopsi oleh banyak proyek 
seperti Drupal, Zend, Symfony, Laravel, CakePHP, phpBB, AWS SDK, FuelPHP, Lithium, dll. 
Anda dapat menggunakannya untuk proyek Anda sendiri, atau terus menggunakan gaya pribadi Anda sendiri.

Ideally, you should write PHP code that adheres to a known standard. This could be any combination of PSRs, or one
of the coding standards made by PEAR or Zend. This means other developers can easily read and work with your code, and
applications that implement the components can have consistency even when working with lots of third-party code.

Idealnya, Anda harus menulis kode PHP yang mematuhi standar yang diketahui. Ini bisa berupa kombinasi PSR, 
atau salah satu standar pengodean yang dibuat oleh PEAR atau Zend. Ini berarti pengembang lain dapat dengan mudah 
membaca dan bekerja dengan kode Anda, dan aplikasi yang mengimplementasikan komponen dapat memiliki konsistensi 
bahkan saat bekerja dengan banyak kode pihak ketiga.

* [Baca tentang PSR-1][psr1]
* [Baca tentang PSR-12][psr12]
* [Baca tentang PSR-4][psr4]
* [Baca tentang PER Coding Style][per-cs]
* [Baca tentang PEAR Coding Standards][pear-cs]
* [Baca tentang Symfony Coding Standards][symfony-cs]

You can use [PHP_CodeSniffer][phpcs] to check code against any one of these recommendations, and plugins for text
editors like [Sublime Text][st-cs] to be given real-time feedback.

Anda dapat menggunakan [PHP_CodeSniffer][phpcs] untuk memeriksa kode terhadap salah satu rekomendasi ini, 
dan plugin untuk penyunting teks seperti [Sublime Text][st-cs] untuk mendapatkan umpan balik waktu nyata (_real-time feedback_).

Anda dapat memperbaiki tata letak kode secara otomatis dengan menggunakan salah satu alat berikut:

- Salah satunya adalah [PHP Coding Standards Fixer][phpcsfixer] yang memiliki basis kode yang telah teruji dengan sangat baik.
- Selain itu, alat [PHP Code Beautifier and Fixer][phpcbf] yang disertakan dengan PHP_CodeSniffer dapat digunakan untuk menyesuaikan kode Anda.

Dan Anda dapat menjalankan phpcs secara manual dari shell:

    phpcs -sw --standard=PSR1 file.php

It will show errors and describe how to fix them.
It can also be helpful to include the `phpcs` command in a git pre-commit hook with the `--filter=GitStaged` CLI argument.
That way, code which contain violations against the chosen standard cannot enter the repository until those
violations have been fixed.

Ini akan menunjukkan kesalahan dan menjelaskan cara memperbaikinya.
Menyertakan perintah `phpcs` dalam kait pra-komit git (_git pre-commit hook_) dengan argumen CLI `--filter=GitStaged` juga dapat membantu.
Dengan demikian, kode yang berisi pelanggaran terhadap standar yang dipilih tidak dapat masuk ke repositori hingga pelanggaran tersebut telah diperbaiki.

Jika Anda memiliki PHP_CodeSniffer, maka Anda dapat memperbaiki masalah tata letak kode yang dilaporkan olehnya, secara otomatis, dengan
[PHP Code Beautifier and Fixer][phpcbf].

    phpcbf -w --standard=PSR1 file.php

Pilihan lainnya adalah menggunakan [PHP Coding Standards Fixer][phpcsfixer].
Alat ini akan menunjukkan jenis kesalahan yang terjadi pada struktur kode sebelum memperbaikinya.

    php-cs-fixer fix -v --rules=@PSR1 file.php

Bahasa Inggris lebih disukai untuk semua nama simbol dan infrastruktur kode. Komentar dapat ditulis dalam bahasa apa pun yang mudah dibaca oleh semua pihak saat ini dan masa mendatang yang mungkin bekerja pada basis kode.

Terakhir, sumber tambahan yang bagus untuk menulis kode PHP yang bersih adalah [Clean Code PHP][cleancode].

[fig]: https://www.php-fig.org/
[psr1]: https://www.php-fig.org/psr/psr-1/
[psr12]: https://www.php-fig.org/psr/psr-12/
[psr4]: https://www.php-fig.org/psr/psr-4/
[per-cs]: https://www.php-fig.org/per/coding-style/
[pear-cs]: https://pear.php.net/manual/en/standards.php
[symfony-cs]: https://symfony.com/doc/current/contributing/code/standards.html
[phpcs]: https://github.com/PHPCSStandards/PHP_CodeSniffer
[phpcbf]: https://github.com/PHPCSStandards/PHP_CodeSniffer/wiki/Fixing-Errors-Automatically
[st-cs]: https://github.com/benmatselby/sublime-phpcs
[phpcsfixer]: https://cs.symfony.com/
[cleancode]: https://github.com/jupeter/clean-code-php
