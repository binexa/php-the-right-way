---
title: Antarmuka Baris Perintah (CLI)
isChild: true
anchor:  command_line_interface
---

## Antarmuka Baris Perintah (CLI) {#command_line_interface_title}

PHP diciptakan untuk menulis aplikasi web, tetapi juga berguna untuk membuat skrip program antarmuka baris perintah 
(_command line interface_), disingkat CLI. Program PHP baris perintah dapat membantu mengotomatiskan tugas-tugas 
umum seperti pengujian, penerapan, dan administrasi aplikasi.

Program PHP CLI sangat hebat karena Anda dapat menggunakan kode aplikasi Anda secara langsung 
tanpa harus membuat dan mengamankan GUI web untuknya. Pastikan **tidak** meletakkan skrip PHP CLI Anda di root web publik Anda!

Coba jalankan PHP dari baris perintah Anda:

{% highlight console %}
> php -i
{% endhighlight %}

Opsi `-i` akan mencetak konfigurasi PHP Anda seperti fungsi [`phpinfo()`][phpinfo].

Opsi `-a` menyediakan shell interaktif, mirip dengan IRB milik Ruby atau shell interaktif milik Python. 
Ada sejumlah [opsi baris perintah][cli-options] lain yang berguna juga.

Mari kita tulis program CLI sederhana "Halo, $name". Untuk mencobanya, buat file bernama `hello.php`, seperti di bawah ini.

{% highlight php %}
<?php
if ($argc !== 2) {
    echo "Usage: php hello.php <name>" . PHP_EOL;
    exit(1);
}
$name = $argv[1];
echo "Hello, $name" . PHP_EOL;
{% endhighlight %}

PHP menyiapkan dua variabel khusus berdasarkan argumen yang digunakan untuk menjalankan skrip Anda. 
[`$argc`][argc] adalah variabel integer yang berisi argumen *count* dan [`$argv`][argv] adalah variabel array yang berisi *value* setiap argumen. 
Argumen pertama selalu berupa nama file skrip PHP Anda, dalam hal ini `hello.php`.

Ekspresi `exit()` digunakan dengan angka bukan nol untuk memberi tahu shell bahwa perintah gagal. 
Kode keluar yang umum digunakan dapat ditemukan [di sini][exit-codes].

Untuk menjalankan skrip kita di atas, dari baris perintah:

{% highlight console %}
> php hello.php
Usage: php hello.php <name>
> php hello.php world
Hello, world
{% endhighlight %}


 * [Pelajari tentang menjalankan PHP dari baris perintah][php-cli]

[phpinfo]: https://www.php.net/function.phpinfo
[cli-options]: https://www.php.net/features.commandline.options
[argc]: https://www.php.net/reserved.variables.argc
[argv]: https://www.php.net/reserved.variables.argv
[exit-codes]: https://www.gsp.com/cgi-bin/man.cgi?section=3&amp;topic=sysexits
[php-cli]: https://www.php.net/manual/en/features.commandline.php
