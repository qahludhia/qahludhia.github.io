---
layout: post
title: "Linux #5: Compressing file with tar & gzip"
date: 2018-30
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan menjelaskan tentang bagaimana caranya mengkompress folder/file di linux menggunakan tar & gzip

##### Yang Pertama

Yang pertama adalah tar. Tar ini kayaknya gak terlalu "ngefek" sih, tapi ya ada sangkut pautnya sama gzip jadi harus tau juga kita.

```console
tar cvf folder.tar /folder
```

Misalnya kita mau membuat /folder (folder dengan nama folder(folderception:D)), kita ketikkan seperti yang diatas, mungkin kalian bertanya-tanya, maksud dari **cvf** itu apa? Ok, jadi **c** itu maksudnya *create* , sedangkan **v** maksudnya verbose, kalo **v** ini sebenernya ga wajib, kita bisa pake bisa nggak, tapi biar lebih memudahkan aja, jadi kalo pake **v** itu nanti keliatan prosesnya. Sedangkan **f** artinya file. Abis kita ketik **tar cvf** kita memberi nama file.tar sesuka kita, pokoknya rumusnya begitu. Abis itu, baru kalian masukkan folder apa yang kalian ingin buat .tar. Jadi, rumusnya begini: 
command > namafolder.tar > /foldermana.

Nah, misalnya kita udah masukkin /folder kedalam folder.tar, cara melihatnya gampang, tinggal kita ganti **c** didepan dengan **t**.

##### Yang Kedua

Nah kalo yang ini itu kelanjutan dari yang pertama, kita udah punya file.tar. Seperti yang sudah saya bilang tadi, tar itu ga terlalu "ngefek", makannya kita harus tambahin gzip atau yang biasa kalian pake di Windows seperti winrar/winzip dan semacamnya lah.

```console
gzip folder.tar
```
Output yang bakalh keluar adalah, folder.tar akan berubah menjadi folder.tar.gz.


##### Yang Ketiga

Nah yang terakhir nih yang paling efektif dan menghemat waktu. Kan kalo kita masukin folder kedalam .tar dulu abis itu baru kita .gzip terlalu lama tuh, nah di Linux ini untungnya menyediakan langsung untuk membuat folder.tar.gz secara langsung.

```console
tar cfvz folder.tar.gz /folder
```

Yang sama persis dengan **Cara yang pertama** diatas, bedanya disini ada **z** nya. **z** disini maksudnya zip.


##### Yang Keempat

Kita udah buat file gzip, pertanyaanya? Gimana cara extractnya? Mudah kali, cukup mudah, mudah kali (Wkwk).

```console
tar xfvz folder.tar.gz	
```
Bingung gak? Kok hampir sama sama yang atas? Beda lah cooy. Kan sudah ku bilang tadi, sangat mudah. Kalian hanya perlu mengganti **c** dengan **x** yang artinya *extract*. Tapi gausah masukin /folder nya lagi, gaperlu, kita hanya perlu folder.tar.gz.

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter ataupun Instagram yang tertera dibagian paling bawah web saya. 

Terima Kasih. 