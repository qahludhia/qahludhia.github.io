---
layout: post
title: "Linux #2: Manipulating file"
date: 2018-10-24
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan menjelaskan tentang manipulating file di Linux.

## Manipulating File

Karena saya bingung bagaimana jelasinnya, kita langsung liat contoh dibawah ini saja.

##### Yang pertama

```console
sort (file.txt) 
```
Anggap aja kita punya file yang bernama file.txt, isi dari file itu adalah nama murid-murid dikelas kita tetapi tidak berurutan secara alphabet. Dengan command diatas, kita bisa dengan mudah mengurutkan nama murid-murid kita sesuai dengan urutan alfabet. Seperti gambar dibawah ini.

![Placeholder](/assets/images/absen1.png)
Gambar adalah gambar file yang saya miliki sebelum saya lakukan command sort.

![Placeholder](/assets/images/absen2.png)
Sedangkan gambar diatas adalah gambar file yang saya miliki sesudah saya lakukan command sort. Terlihat berbeda bukan?

Dan tambahan lagi, kamu juga bisa membalikan urutan alfabet dari Z-A dengan cara seperti dibawah ini:

```console
sort -r (file.txt) 
```

Kamu juga bisa melakukan hal lain dengan command sort ini, kamu hanya perlu melihatnya di manpage sort dengan cara seperti dibawah ini:

```console```console
sort (file.txt) 
```
man sort
```

##### Yang Kedua

```console
fmt -u (namafile.txt)
```
Kalau fungsi command yang ini adalah, kita bisa merapikan spacing di text jika text yang kita punya spacingnya berantakan.

```console
 ✘ dhia@Puco-pc  ~/BelajarLinux  cat gajebo.txt 
Ini      adalah    file   yang spacingnya   ga        beraturan  banget
```
Bisa dilihat? Spacingnya sangat berantakan. Bagaimana kalau kita merapikannya secara manual? Memakan waktu bukan? Nah, kita coba dengan cara seperti ini:

```console
 dhia@Puco-pc  ~/BelajarLinux  fmt -u gajebo.txt 
Ini adalah file yang spacingnya ga beraturan banget
```
Nah itu dia hasilnya. Kita tidak perlu membutuhkan banyak waktu untuk merapikan spacing yang berantakan.

##### Yang Ketiga

```console
nl (namafilemu.txt)
```
Fungsi dari command diatas adalah untuk memberi nomor pada text yang kita punya. Misalnya kita mau memberikan nomor pada file absen yang kita miliki seperti ini.

![Placeholder](/assets/images/absen2.png)
Absen ini belum ada urutannya bukan?

Nah kita tinggal mengetikkan

```console
nl absen.txt
```

Maka outputnya akan seperti gambar dibawah ini:

![Placeholder](/assets/images/absen3.png)

##### Penyelesaian

Semua command diatas tidak permanen. Tapi tenang kita hanya cukup menambahkan ">". Bingung? Langsung aja kita praktek

![Placeholder](/assets/images/absen2.png)

```console
nl absen.txt > absenurut.txt 
```
![Placeholder](/assets/images/absen3.png)
Jreeng.. Magic bukan? Semua command caranya sama seperti itu, jadi tidak usah dibingungkan lagi. Oiya kalau kalian masih bingung, jangan lupa untuk membuka manpage yang sudah tertera diatas.

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter ataupun Instagram yang tertera dibagian paling bawah web saya. 

Terima Kasih. 