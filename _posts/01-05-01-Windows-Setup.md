---
title  : Pengaturan Windows
isChild: true
anchor : windows_setup
---

## Pengaturan Windows {#windows_setup_title}

Anda dapat mengunduh biner dari [windows.php.net/download][php-downloads]. Setelah mengekstrak PHP, disarankan 
untuk menyetel [PATH][windows-path] ke akar folder PHP Anda (tempat php.exe berada) sehingga Anda dapat 
menjalankan PHP dari mana saja.

Untuk pembelajaran dan pengembangan lokal, Anda dapat menggunakan webserver bawaan dengan PHP 5.4+ 
sehingga Anda tidak perlu khawatir tentang konfigurasinya. Jika Anda menginginkan "all-in-one" yang mencakup 
webserver lengkap dan MySQL, maka alat seperti [XAMPP][xampp], [EasyPHP][easyphp], [OpenServer][openserver] 
dan [WAMP][wamp] akan membantu menyiapkan dan menjalankan lingkungan pengembangan Windows dengan cepat. 
Meskipun demikian, alat-alat ini akan sedikit berbeda dari produksi, jadi berhati-hatilah dengan perbedaan 
lingkungan jika Anda bekerja di Windows dan menerapkannya di Linux.

Jika Anda perlu menjalankan sistem produksi di Windows, maka IIS7 akan memberi Anda kinerja yang paling stabil 
dan terbaik. Anda dapat menggunakan [phpmanager][phpmanager] (plugin GUI untuk IIS7) untuk mempermudah konfigurasi 
dan pengelolaan PHP. IIS7 dilengkapi dengan FastCGI bawaan dan siap digunakan, Anda hanya perlu mengonfigurasi PHP 
sebagai pengendali. Untuk dukungan dan sumber daya tambahan, terdapat [area khusus di iis.net][php-iis] untuk PHP.

Umumnya menjalankan aplikasi Anda pada lingkungan yang berbeda dalam pengembangan dan produksi dapat menyebabkan munculnya bug aneh saat Anda mulai menggunakannya. Jika Anda mengembangkan aplikasi di Windows dan menerapkannya di Linux (atau apa pun yang bukan Windows), maka Anda harus mempertimbangkan untuk menggunakan [Mesin Virtual](/#virtualization_title).

Chris Tankersley memiliki posting blog yang sangat bermanfaat tentang alat apa yang ia gunakan untuk melakukan [pengembangan PHP menggunakan Windows][windows-tools].

[easyphp]: https://www.easyphp.org/
[phpmanager]: http://phpmanager.codeplex.com/
[openserver]: https://ospanel.io/
[wamp]: https://www.wampserver.com/en/
[php-downloads]: https://windows.php.net/download/
[php-iis]: https://php.iis.net/
[windows-path]: https://www.windows-commandline.com/set-path-command-line/
[windows-tools]: https://ctankersley.com/2016/11/13/developing-on-windows-2016/
[xampp]: https://www.apachefriends.org/
