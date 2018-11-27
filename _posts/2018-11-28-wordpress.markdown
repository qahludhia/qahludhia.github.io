---
layout: post
title: "Linux #12: Wordpress"
date: 2018-11-28
description:  
image: /assets/images/wordpress.png
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Oke bro, sis, lama ga posting karena ada hal yang membuat saya ga posting (read: males)

Let's stick to the point, kali ini saya akan menjelaskan bagaimana caranya menginstall Wordpress di OS Linux.

##### Yang Pertama

Yang pertama kita harus sudah menginstall apache2 terlebih dahulu, kalau belum ada, kalian bisa liat dipostingan sebelum ini yang membahas tentang apache2.

##### Yang Kedua

Yang kita butuhkan selanjutnya adalah MySQL server. Cara menginstallnya seperti ini

```console
sudo apt-get install mysql-client mysql-server
```
maka akan keluar pop up seperti dibawah ini

![Placeholder](/assets/images/apache1.png)

dan masukkan password root(admin) yang ingin kalian masukkan.

Tapi, MySQL kalian belum sepenuhnya aman, kita harus menginstall 1 hal lagi yakni,

```console
sudo mysql_secure_installation 
```
Pertama, kalian akan diminta untuk install 'validate_password' plugin, jadi pencet Yes(Y) dan Enter. Yang paling penting, kalo kalian tidak pengen mengganti password root (admin), pencet No(N), setelah itu Yes(Y) aja setelahnya.

##### Yang Ketiga

Selanjutnya kita harus menginstall PHP dan modules agar bekerja dengan web dan databasenya. Cara installnya seperti ini

```console
sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd  
```

Dan untuk mengetes apakah php-nya sudah bekerja dengan webserver, kita coba membuat file bernama *info.php* didalam folder /var/www/html

```console
sudo nano /var/www/html/info.php
```
dan paste code dibawah ini kedalam file info.php

```console
<?php 
phpinfo();
?>
```

Jika sudah, lalu buka *localhost/info.php*, maka tampilannya akan seperti ini

![Placeholder](/assets/images/php.png)

##### Yang Keempat

Yang terakhir adalah menginstall WordPress. Yang pertama kita harus download latest wordpress (wordpress yang paling baru) dengan cara:

```console
wget -c http://wordpress.org/latest.tar.gz
tar -xzvf latest.tar.gz
```
Jika sudah, pindahkan file dari folder yang sudah di extract kedalam folder root milik Apache

```console
sudo rsync -av wordpress/* /var/www/html/
```
Setelah itu, kita rubah permission folder website kita.

```console
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/
```

##### Yang Terakhir

Yang terakhir adalah, menginstall Database untuk Wordpress
Ketikkan 

```console
mysql -u root -p 
```
dan ketikkan seperti dibawah ini, enter setiap barisnya

```console
mysql> CREATE DATABASE wp_myblog;

mysql> GRANT ALL PRIVILEGES ON nama-datebase.* TO ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password-mu';

mysql> FLUSH PRIVILEGES;

mysql> EXIT;
```
Setelah itu pindah ke folder /var/www/html dan rename *wp-config-sample.php* menjadi *wp-config.php*. Setelah itu update isinya dengan isian yang sama seperti yang kamu buat di MySQL.

![Placeholder](/assets/images/wordpress1.png)

Karena saya sudah menginstall, tampilan yang saya punya jika membuka localhost/wp-admin seperti ini

![Placeholder](/assets/images/wordpress2.png)

Jika kalian belum menginstall, makan akan seperti ini

![Placeholder](/assets/images/wordpress3.png)

Caranya tinggal klik, klik, pokoknya semudah membuat facebook dan sosmed lain.

**Source:** https://www.tecmint.com/install-wordpress-on-ubuntu-16-04-with-lamp/

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih. 
