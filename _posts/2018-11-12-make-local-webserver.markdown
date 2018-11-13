---
layout: post
title: "Linux #10: Make local webserver on Ubuntu with Apache2"
date: 2018-11-11
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan menjelaskan cara membuat webserver local di Ubuntu menggunakan apache2.

Langsung saja kita menuju step yang pertama.

##### Yang Pertama

Yang pertama yang harus kita lakukan adalah menginstall apache2 dengan cara

```console
sudo apt-get install apache2
```
##### Yang Kedua

Yang kedua, kita harus menginstall lynx. Lynx itu semacam browser tapi didalam terminal. Cara installnya sebagai berikut

```console
sudo apt-get install lynx
```
Jika sudah terinstall, coba kita jalankan

```console
lynx localhost
```
Yang dihasilkan pasti seperti dibawah ini:

![Placeholder](/assets/images/apache1.png)

Karena kita belum start apache2nya. Caranya seperti ini:

```console
systemctl start apache2
```
setelah itu kita cek status 

```console
systemctl status apache2
```
Maka sekarang akan seperti ini

![Placeholder](/assets/images/apache2.png)

Setelah itu, kita cobalagi  

```console
lynx localhost
```
Maka akan keluar output seperti dibawah

![Placeholder](/assets/images/apache3.png)


## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih. 
