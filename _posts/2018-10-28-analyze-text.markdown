---
layout: post
title: "Linux #3: Analyze text using regular expression "
date: 2018-10-28
description: 
image: /assets/images/linux.jpg
author: Muhammad Dhia Ul Haq
tags:
 - Tech
---
Pada postingan kali ini, saya akan menjelaskan tentang **Analyze text using regular expression**.

## Apa sih Analyze text itu?
Mudahnya si kayak find di aplikasi-aplikasi semacam Microsoft Word gitu. Tapi bedanya disini kita menggunakan terminal di Linux.

##### Yang Pertama

```console
grep '^The' alice.txt  
```
Jadi saya punya file namanya "alice.txt". Saya mau nyari paragraf yang berawalan dengan kata "The". Penjelasannya adalah, (^) berfungsi sebagai alat, semacam gayung kalau kita mau nyiduk air, (^) sebagai alat untuk menyiduk paragraf yang berawalan dengan kalimat "The".

##### Yang Kedua

```console
grep '^T[a-z][^e]' alice.txt 
```
Kalau yang ini, kita ingin mencari paragraf yang kata awalnya berawalan huruf "T" dan dilanjutkan oleh huruf antara "a-z" kecuali huruf "e".
Jadi penjelasannya, (^) ini sama yang seperti diatas, dia untuk mencari awal paragraf, tapi kalo yang didalam [^] beda ya, ini untuk pengecualian.

##### Yang Ketiga

```console
grep '\<[tT]he\>' alice.txt
```
Mencari seluruh text yang kalimatnya mengandung huruf “Tt” dan “he” setelahnya. Jadi ini keseluruhan, tidak diawal kalimat pada setiap paragraf saja, yang ditengah pun bakal keciduk juga.

##### Yang Keempat

```console
grep '\([a-z][a-z]\)'
```
Yang ini hampir sama dengan yang diatas, tapi kalo yang ini, kita mencari kata yang mengandung huruf "a-z" dan dilanjutkan dengan huruf "a-z" juga. Tidak termasuk huruf kapital.

## Terima Kasih
Mungkin itu yang dapat saya tulis kali ini, sebagaimana biasanya, kritik & saran sangat diperlukan dalam tulisan saya agar menjadi lebih baik lagi kedepannya. Jadi, kalian bisa hubungi saya lewat Twitter ataupun Instagram yang tertera dibagian paling bawah web saya. 

Terima Kasih. 