---
layout: post
title: "Linux #18: Configure Systems to Mount File Systems at or During Boot"
date: 2018-12-25
description: Menjelaskan tentang partisi di Linux yang biasanya kita harus mount manual setiap kita nyalain PC kita, disini saya akan menjelaskan bagaimana caranya agar menjadi otomatis setiap kita nyalain PC kita
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Kali ini saya akan membahas tentang partisi lagi. 

Karena tidak semua patisi di Linux sudah ter-mount setiap kita nyalain komputer, ga kaya windows yang praktis. Setiap dinyalain paritisinya langsung bisa dipake.

Begini contohnya

![Placeholder](/assets/images/boot1.png)
Screenshot diatas adalah partisi sdb1 saya yang dimount di /mnt/kadir sebelum saya restart. Terlihat kan ada beberapa file didalamnya. Nah sekarang saya restart, dan saya melihat lagi isi folder dari /mnt/kadir, dan hasilnya seperti dibawah

![Placeholder](/assets/images/boot2.png)
Logikanya berarti kan belom kebaca atau belum kecolok setiap kita restartnya, nah disini saya akan menjelaskan bagaimana caranya agar paritisi tersebut sudah kecolok atau kebaca setiap kita restart atau mematikan komputer kita.

##### Yang Pertama

Yang perlu kita ketaui pertama, kita harus tau UUID dan jenis partisi kita harus ext4, cara ceknya disini

```console
blkid
```

![Placeholder](/assets/images/boot3.png)

Kalau paritisi kita belum ext4, ubah di

```console
mkfs -t ext4 /dev/sdb1
```
Setelah kita udah tau id-nya, kita masuk ke 

```console
nano /etc/fstab
```

![Placeholder](/assets/images/boot4.png)

```console
UUID=a685a0c0-c9e0-4d32-91b8-ff18b12e1143 /mnt/kadir ext4 defaults 0 2
```
-Blok pertama, UUID, masukkan UUID partisi milik kalian yang ada di **blkid**

-Blok kedua, tempat kalian mount partisi kalian

-Blok ketiga, jenis harddisk kalian, default Linux sama

-Blok keempat, isi aja dengan defaults

-Blok kelima, itu urutan dia dibooting urutan keberapa, disitu kita taro 0 2, berarti dia boot nomor 3.

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih.
