---
title  : Paradigma Pemrograman
isChild: true
anchor:  programming_paradigms
---

## Paradigma Pemrograman {#programming_paradigms_title}

PHP adalah bahasa yang fleksibel dan dinamis yang mendukung berbagai teknik pemrograman. Bahasa ini telah berkembang 
secara dramatis selama bertahun-tahun, terutama dengan menambahkan model berorientasi objek yang solid di PHP 5.0 (2004), 
fungsi anonim dan namespace di PHP 5.3 (2009), dan trait di PHP 5.4 (2012).

### Pemrograman Berorientasi Obyek

PHP memiliki seperangkat fitur pemrograman berorientasi objek yang sangat lengkap termasuk dukungan untuk kelas (_class_), 
kelas abstrak (_abstract class_), antarmuka (_interfaces_), pewarisan (_inheritance_), konstruktor (_constructor_), kloning (_cloning_), pengecualian (_exception_), dan banyak lagi.

* [Read about Object-oriented PHP][oop]
* [Read about Traits][traits]

### Pemrograman Functional

PHP mendukung fungsi kelas satu, yang berarti bahwa suatu fungsi dapat ditetapkan ke suatu variabel. 
Baik fungsi yang ditentukan pengguna maupun fungsi bawaan dapat direferensikan oleh suatu variabel dan dipanggil secara dinamis. 
Fungsi dapat diteruskan sebagai argumen ke fungsi lain (fitur yang disebut _Fungsi Tingkat Tinggi_) dan fungsi dapat mengembalikan fungsi lain.

Rekursi, sebuah fitur yang memungkinkan suatu fungsi memanggil dirinya sendiri, didukung oleh bahasa tersebut, 
tetapi sebagian besar kode PHP difokuskan pada iterasi.

New anonymous functions (with support for closures) are present since PHP 5.3 (2009).

PHP 5.4 added the ability to bind closures to an object's scope and also improved support for callables such that they
can be used interchangeably with anonymous functions in almost all cases.

* Continue reading on [Functional Programming in PHP](/pages/Functional-Programming.html)
* [Baca tentang Anonymous Functions][anonymous-functions]
* [Baca tentang Closure class][closure-class]
* [Rincian lebih lanjut ada di Closures RFC][closures-rfc]
* [Baca tentang Callables][callables]
* [Baca tentang pemanggilan fungsi secara dinamis dengan `call_user_func_array()`][call-user-func-array]

### Pemrograman Meta (_Meta Programming_)

PHP supports various forms of meta-programming through mechanisms like the Reflection API and Magic Methods. There are
many Magic Methods available like `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()`, etc. that allow
developers to hook into class behavior. Ruby developers often say that PHP is lacking `method_missing`, but it is
available as `__call()` and `__callStatic()`.

PHP mendukung berbagai bentuk pemrograman-meta (_meta-programming_) melalui mekanisme seperti _Reflection API_ dan _Magic Methods_. Ada banyak _Magic Methods_ yang tersedia seperti `__get()`, `__set()`, `__clone()`, `__toString()`, `__invoke()`, dll. yang memungkinkan pengembang untuk mengaitkan perilaku kelas. Pengembang Ruby sering mengatakan bahwa PHP kekurangan `method_missing`, tetapi tersedia sebagai `__call()` dan `__callStatic()`.

* [Baca tentang Magic Methods][magic-methods]
* [Baca tentang Reflection][reflection]
* [Baca tentang Overloading][overloading]


[oop]: https://www.php.net/language.oop5
[traits]: https://www.php.net/language.oop5.traits
[anonymous-functions]: https://www.php.net/functions.anonymous
[closure-class]: https://www.php.net/class.closure
[closures-rfc]: https://wiki.php.net/rfc/closures
[callables]: https://www.php.net/language.types.callable
[call-user-func-array]: https://www.php.net/function.call-user-func-array
[magic-methods]: https://www.php.net/language.oop5.magic
[reflection]: https://www.php.net/intro.reflection
[overloading]: https://www.php.net/language.oop5.overloading
