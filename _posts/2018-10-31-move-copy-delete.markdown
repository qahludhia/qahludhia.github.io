---
layout: post
title: "Linux #6: Move, copy, and delete files"
date: 2018-10-31
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan menjelaskan tentang bagaimana cara membuat folder, memodifikasi file, ntah itu merename ataupun copy dan semacamnya dengan terminal di Linux.

##### Yang Pertama

```console
Mkdir (namafolder)
```

Yang pertama adalah membuat folder/directory. Kita hanya perlu mengetik perintah seperti diatas, maksud dari *namafolder* adalah nama folder yang kita inginkan, nah ada perintah lagi **mkdir** ini. Kita bisa membuat dua bahkan lebih folder sekaligus. Kita hanya perlu mengetikkan seperti dibawah ini:

```console
Mkdir -p folder1/folder2
```

Maksud dari **p** diatas adalah parent, jadi namanya parent kan punya anak, begitupula dengan ini.

##### Yang Kedua

```console
cp gaje.txt /home/dhia/Documents
```

Yang kedua ini adalah copy, contoh diatas saya ingin mengopi file saya yang bernama *gaje.txt* ke directory /home/dhia/Document. Yang kita perlukan menuju ke folder dimana file kita berada, setelah itu baru deh ketikkan seperti command yang diatas.

##### Yang Ketiga

```console
mv gaje.txt /home/dhia/Documents
```

Yang ketiga ini adalah move, sama seperti cp, tapi dia bedanya itu bukan copy, tapi cut. Jadi, file yang kita move bakal ilang di folder aslinya, jadinya cuma ada di folder tempat kita naro tadi. Tapi **mv** ini juga bisa buat rename, caranya mudah banget, kita hanya butuh mengetikkan seperti dibawah ini:

```console
mv gaje.txt asli.txt
```

Jadi kita hanya mengetikkan file yang ingin kita rename, dan setelah itu memberi nama yang baru sesuka kita.

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter ataupun Instagram yang tertera dibagian paling bawah web saya. 

Terima Kasih. 