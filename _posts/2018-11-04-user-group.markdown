---
layout: post
title: "Linux #8: Create, Delete, and Modify Local User Accounts, Modify Local Groups and Group Memberships"
date: 2018-11-04
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---

Hari ini saya akan menjelaskan tentang bagaimana cara membuat user dan grub baru di Linux.

##### Yang Pertama

Yang pertama adalah membuat user baru. Membuat user baru ada beberapa cara, yang pertama adalah

```console
sudo useradd toni
```

dan yang kedua adalah

```console
sudo adduser lulu
```

Perbedaannya adalah, kalau *useradd* itu langsung kebuat tanpa password, jadi kita harus set password lagi, sedangkan *adduser* semuanya udah include, jadi kita langsung diminta buat password, dll, seperti gambar dibawah ini:

![Placeholder](/assets/images/user2.png)

Oiya, kalo kita ingin memastikan user yang tadi udah kebuat, kita bisa liat di folder 

```console
cat /etc/passwd
```
![Placeholder](/assets/images/user1.png)


##### Yang Kedua

Yang kedua adalah delete user. Delete user sangat mudah, kita hanya perlu mengtikkan command

```console
userdel (nama user yang ingin dihapus)
```

##### Yang Ketiga

Yang ketiga adalah membuat user baru dengan include file yang kita ingin buat. Caranya, kita buat atau copy folder yang kita punya ke directory atau folder

```console
/etc/skel
```
Foldernya akan muncul di home directory user kita yang baru tapi tidak muncul di home directory kita. Caranya, kita taro file di skel dulu baru kita buat user baru

##### Yang Keempat

Yang keempat adalah membuat group baru. Group ini gunanya untuk mengelompokkan user. Jadi ini mungkin sangat berguna bila kita nanti kerja diperusahaan yang banyak karyawannya, mungkin bisa membuat grub untuk masing-masing divisi. Sama seperti membuat user, cara membuat grub juga ada dua cara. Yang pertama:

```console
addgroup (namagrup)
```
dan
```console
groupadd (namagrup)
```

Perbedaanya mungkin hanya sedikit, kalo addgroup ada semacam prosesnya gitu, sedangkan groupadd gak ada.

Dan kalo kita ingin mengecek group yang ada, kita hanya perlu melihatnya di

```console
cat /etc/group
```

dan untuk menghapusnya, kita hanya perlu mengetikkan command

```console
groupdel (nama grup yang pengen dihapus)
```

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter ataupun Instagram yang tertera dibagian paling bawah web saya. 

Terima Kasih. 