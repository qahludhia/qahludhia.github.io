---
layout: post
title: "Linux #21: Sticky Bit"
date: 2019-01-07
description: Membuat permission Sticky Bit
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan membahas tentang sticky bit.

Sticky bit itu salah satu permission di Linux, kita bisa ubah permission directory jadi ada sticky bit-nya. Jadi, file yang ada didalam direktori yang punya permission sticky bit, bisa di edit oleh user lain, tetapi gabisa diapus oleh selain user yang membuat file itu.

Langsung aja lah ke contohnya biar ga pusing :P

##### Yang Pertama

Yang pertama, kita buat dulu aja direktori atau folder. Terserah mau buat dimana.

![Placeholder](/assets/images/stiki3.png)

Saya sudah membuat directory bernama **bala**, yang mempunyai permission rwx untuk semuanya

##### Yang Kedua

Kita buat directory tadi menjadi ada stickybit-nya.

```console
sudo chmod +t bala/
atau
sudo chmod 1777 bala/
```
![Placeholder](/assets/images/stiki2.png)

Bisa diliat perbedaanya dengan gambar sebelumnya? Ya, ada huruf "t" dipaling belakang permission.

##### Yang Ketiga

Selanjutnya, kita tes buat file didalamnya.

![Placeholder](/assets/images/stiki5.png)

Disitu, saya mencoba membuat file bernama "dhia" dan saya hapus kembali, dan bisa, karena owner dari file itu ada "dhia" yang mana itu adalah user yang saya pakai untuk membuat file itu dan menghapusnya juga menggunakan user yang sama.

Sekarang, saya akan mencoba membuat file yang sama tetapi menghapus-nya dengan user yang berbeda.

Disini, saya menggunakan user "ninja" dan lihat apa yang terjadi jika saya ingin menghapus file yang owner-nya user "dhia"

![Placeholder](/assets/images/stiki6.png)

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih.




