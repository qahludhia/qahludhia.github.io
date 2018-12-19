---
layout: post
title: "Linux #15: Partition"
date: 2018-12-18
description:  
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Hello guys, kali ini saya akan menjelaskan tentang partitions di Linux, sebenernya ada emang aplikasi yang ada GUInya, cuman kalo begitu semua orang pasti bisa, karena kita harusnya berbeda. Haha.

Oiya, mungkin ini sedikit sulit, dan bisa membahayakan data-data kalian, jadi saya sarankan untuk menggunakan virtual machine untuk mencobanya.

##### Yang Pertama

Yang pertama kita coba list partisi yang kita punya, dengan cara mengetikkan

```console
lsblk
```
Nanti, output yang bakal keluar seperti ini

![Placeholder](/assets/images/partisi4.png)

##### Yang Kedua

Kita masuk kedalam fdisk dengan cara

```console
fdisk /dev/sdb(ini sesuaikan dengan nama device yang kalian punya)
```
Karena device saya namanya **sdb** maka hasilnya seperti ini

![Placeholder](/assets/images/partisi5.png)

dan kalau kalian ingin melihat panduannya, kalian ketikkan huruf "m". Maka akan keluar seperti ini

![Placeholder](/assets/images/partisi6.png)
![Placeholder](/assets/images/partisi7.png)

##### Yang Ketiga

Nah, sekarang kita akan mencoba membagi partisi **sdb** tadi, menjadi beberapa bagian lagi

![Placeholder](/assets/images/partisi8.png)


```console
Command (m for help): n = new (buat partisi baru)
Partition type
   p   primary (0 primary, 0 extended, 4 free)
   e   extended (container for logical partitions)
Select (default p): p (utama)
Partition number (1-4, default 1): Kasih nomornya terserah, tapi kalo langsung enter, nanti dia setting ke default (1), dan kalo udah ada satu nanti dia setting langsung (2), dan seterusnya. 
First sector (2048-2360137, default 2048): (ini langsung default aja) 
Last sector, +sectors or +size{K,M,G,T,P} (2048-2360137, default 2360137): +200M (size yang mau di kasih)

Created a new partition 1 of type 'Linux' and of size 200 MiB.

Command (m for help): 
```

Setelah itu coba kita ketik **p** (print)

Sebelum kita bagi:

![Placeholder](/assets/images/partisi9.png)

Setelah dibagi:

![Placeholder](/assets/images/partisi10.png)

Setelah itu, coba kita keluar dari fdisk dengan cara mengetikkan **quit**

Dan kita ketik **lsblk** lagi dan lihat hasilnya

![Placeholder](/assets/images/partisi11.png)

Nah, kita udah bagi partisi nih, terus, kemana sisanya? 

Tenang, sisanya masih ada, tapi kita gabungin pake cara yang lain, yaitu dengan cara seperti ini

```console
parted /dev/sdb (sesuaikan dengan device kalian masing masing)
```
Maka akan keluar seperti ini:

![Placeholder](/assets/images/partisi12.png)

Nah, caranya menggabungkan tadi yang terpisah seperti ini:

![Placeholder](/assets/images/partisi13.png)

```console
        copyright information of GNU Parted
(parted) mkpart (make part)                                                          
Partition type?  primary/extended? primary (utama)                                
File system type?  [ext2]? ext4 (ini udah default Linux)
Start? 500MB (Ini kita kira-kira aja, nanti systemnya akanmenyesuaikan sendiri)
End? 1100MB  (Sama kaya yg atas, systemnya menyesuaikan sendiri, kalaupun error nanti dia bakal ngasih tau apa yang salah)
(parted) (berhasil)
```
Setelah itu, coba kita ketik **lsblk** lagi, dan anda akan melihat sisanya akan dialokasikan ke partisi baru

![Placeholder](/assets/images/partisi14.png)

Tapi kayaknya ini kurang pas, karena saya mungkin salah itung, wkwk.

##### Bonus

Oiya, bagi kalian yang ingin menggunakan virtual-box, saya sarankan settingan koneksi di virtual-box-nya kita ubah agar kita bisa meremotnya menggunakan terminal linux kita yang asli, karena kalau kita bermain di virtual-box-nya akan terasa berat.

Begini caranya:

![Placeholder](/assets/images/virtualbox.png)

Ikuti yang seperti digambar, maka anda akan bisa meremotnya menggunakan ssh dengan perantara terminal Linux asli anda. Tapi jangan lupa untuk menginstall sh terlebih dahulu, ok!

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih.







