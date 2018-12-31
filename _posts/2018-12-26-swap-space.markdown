---
layout: post
title: "Linux #19: Swap Space"
date: 2018-12-26
description: Pada post ini, saya akan menjelaskan bagaimana caranya membuat swap space.
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---

Sebenernya, apa si itu swap space? Kalo analoginya si begini, misalnya kita kerja dikantoran, nah meja kerja kita udah banyak tumpukan tugas yang mesti dikerjakan, sehingga kalo ada berkas baru lagi gabakal muat, alhasil dibuat lah ruang berkas, jadi berkas-berkas yang ada di meja kerja kita ga terlalu penuh.

Begitulah analoginya, swap itu kayak memori cadangan. 

Lalu, cara membuat memori swap ada dua cara, yakni dengan menggunakan partisi, dan menggunakan folder atau file biasa

#### Cara Pertama

Yang pertama, saya akan menjelaskan bagaimana caranya membuat memori swap yang menggunakan partisi.

Caranya:

##### Yang Pertama

Tentukan partisi yang akan anda jadikan memori swap.

![Placeholder](/assets/images/swap1.png)

Saya akan menjadi kan partisi sdb3 saya menjadi memori swap. 

Bagaimana caranya?

```console
mkswap /dev/sdb3
```
Lalu, untuk menyalakannya 
```console
swapon /dev/sdb3
```
![Placeholder](/assets/images/swap2.png)

Terlihat kan bedanya?

lalu, kalian bisa cek apakah sudah berfungsi di

```console
free -mt
```
![Placeholder](/assets/images/swap3.png)

Lalu, jika kalian ingin memantenkan(membuat permanen) saat restart pun langsung muncul, jadi kita ga nyalain setiap kita nyalain pc kita.

Caranya:

```console
nano /etc/fstab
```
Tambahkan
```console
/dev/sdb3 swap swap defaults 0 0
```
![Placeholder](/assets/images/swap4.png)

Sesuaikan dengan partisi yang kalian miliki

#### Cara Kedua

Yang kedua, kita menggunakan file untuk memori swap.

Caranya:

##### Yang Pertama

```console
dd if=/dev/zero of=/root/myswapfile bs=1M count=1024
```
nama setelah /root/myswapfile (ini bebas)

##### Yang Kedua

Yang kedua kita ganti permissionnya menjadi

```console
chmod 600 /root/myswapfile
```

##### Yang Ketiga

Sama seperti cara yang pertama

```console
mkswap /root/myswapfile

lalu

swapon /root/myswapfile
```
Setelah udah, lalu kita ingin patenkan seperti cara yang pertama, caranya pun juga sama

```console
nano /etc/fstab

lalu tambahkan

/root/myswapfile swap swap defaults 0 0
```

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih.



