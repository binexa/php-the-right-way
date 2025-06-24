---
title: Manajemen Ketergantungan
anchor: dependency_management
---

# Manajemen Ketergantungan {#dependency_management_title}

Ada banyak sekali pustaka (_library_), kerangka kerja (_framework_), dan komponen (_component_) PHP yang dapat dipilih. 
Proyek Anda kemungkinan akan menggunakan beberapa di antaranya — ini adalah ketergantungan proyek. 
PHP tidak memiliki cara yang baik untuk mengelola ketergantungan proyek ini. Bahkan jika Anda mengelolanya secara manual, 
Anda tetap harus mengkhawatirkan pemuat otomatis (_autoloader_). Itu bukan lagi masalah.

Saat ini ada dua sistem manajemen paket utama untuk PHP - [Composer] dan [PEAR]. 
Composer saat ini merupakan manajer paket paling populer untuk PHP, namun untuk waktu yang lama 
PEAR merupakan manajer paket utama yang digunakan. Mengetahui sejarah PEAR merupakan ide yang bagus, karena 
Anda mungkin masih menemukan referensi ke sana meskipun Anda tidak pernah menggunakannya.

[Composer]: {{ site.baseurl }}/#composer_and_packagist
[PEAR]: {{ site.baseurl }}/#pear
