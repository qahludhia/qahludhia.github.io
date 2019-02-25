---
layout: post
title: "Linux #23: Create & Configure Filesystem"
date: 2019-01-15
description: Membuat filesystem menggunakan mkfs
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---

Kali ini saya akan memberitau bagaimana caranya membuat filesystem. Disini saya akan membuat filesystem berjenis ext4 dan btrfs.

Langsung saja ke step yang pertama

##### Yang Pertama

Pastikan kita sudah mempunya partisi atau harddisk yg ingin kita jadikan filesystem. Di langkah pertama ini, saya akan membuat hardisk saya menjadi filesystem ext4

![Placeholder](/assets/images/fs1.png)

partisi yang ingin saya jadikan ext4 adalah sdb

```console
mkfs -t ext4 /dev/sdb
```

![Placeholder](/assets/images/fs2.png)

Jika sudah seperti ini, kita coba lsblk lagi, dan tidak akan terjadi perubahan.

Maka, langkah selanjutnya, kita harus mount. Saya mount di /mnt/ext4

```console
mount /dev/sdb /mnt/ext4
```

![Placeholder](/assets/images/fs3.png)
Nah, setelah kita mount, lalu kita lihat lsblk lagi, maka akan ada perbedaan

##### Yang Kedua

Yang kedua sama saja seperti yang pertama, bedanya kita membuat filesystem bertipe btrfs. Kita hanya butuh install 1 item

```console
sudo apt-get install btrfs-tools
```

Karena kalau tidak di install, akan ada error yang terjadi

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter, Instagram yang tertera dibagian paling bawah web saya, atau di menu kritik & saran yang berada dipojok kanan atas web saya. 

Terima Kasih.




