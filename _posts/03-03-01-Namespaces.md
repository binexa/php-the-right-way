---
title  : Namespace
isChild: true
anchor :  namespaces
---

## Namespace {#namespaces_title}

Seperti disebutkan di atas, komunitas PHP memiliki banyak pengembang yang membuat banyak kode. 
Ini berarti bahwa kode PHP satu pustaka mungkin menggunakan nama kelas yang sama dengan pustaka lainnya. 
Ketika kedua pustaka digunakan dalam namespace yang sama, keduanya bertabrakan dan menyebabkan masalah.

_Namespace_ memecahkan masalah ini. Seperti yang dijelaskan dalam manual referensi PHP, 
namespace dapat dibandingkan dengan direktori sistem operasi yang berisi file _namespace_; 
​​dua file dengan nama yang sama dapat hidup berdampingan dalam direktori terpisah. Demikian pula, 
dua kelas PHP dengan nama yang sama dapat hidup berdampingan dalam namespace PHP yang terpisah. Sesederhana itu.

Penting bagi Anda untuk memberi namespace pada kode Anda sehingga dapat digunakan oleh pengembang lain tanpa takut bertabrakan dengan pustaka lain.

Salah satu cara yang direkomendasikan untuk menggunakan namespace diuraikan dalam [PSR-4][psr4], 
yang bertujuan untuk menyediakan konvensi file, kelas, dan namespace standar untuk memungkinkan kode plug-and-play.

Pada bulan Oktober 2014, PHP-FIG menghentikan penggunaan standar autoloading sebelumnya: [PSR-0][psr0]. 
Baik PSR-0 maupun PSR-4 masih dapat digunakan dengan sempurna. PSR-4 memerlukan PHP 5.3, sehingga banyak proyek PHP 5.2 saja yang mengimplementasikan PSR-0.

Jika Anda akan menggunakan standar autoloader untuk aplikasi atau paket baru, lihat PSR-4.

* [Baca tentang Namespace][namespaces]
* [Baca tentang PSR-0][psr0]
* [Baca tentang PSR-4][psr4]


[namespaces]: https://www.php.net/language.namespaces
[psr0]: https://www.php-fig.org/psr/psr-0/
[psr4]: https://www.php-fig.org/psr/psr-4/
