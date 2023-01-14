---
title: "Membatasi String Lenght pada JavaScript"
description: Membatasi String Lenght pada JavaScript
frase: Biasanya case ini terjadi pada saat kita fetching sebuah API yang 
tags:
  - JavaScript
  - VueJS
category: JavaScript
coverImage: limits-string-character-in-javascript.jpg
alt: Membatasi String Lenght pada JavaScript
date: 2022-12-05 20:22:22
---


## Bagaimana Cara membatasi String data pada JavaScript

Biasanya case ini terjadi pada saat kita fetching sebuah API yang biasa dalam berbentuk string sebuah Judul, Slug atau Spotlight description blog yang terlalu panjang atau nama sebuah produk yang panjang sehingga menutupi atau menggangu responsifitas tampilan web, nah kita bisa 'membatasi' nama tersebut menjadi lebih pendek atau 'memisahkan' karakter tersebut, jadi kita lebih leluasa untuk mengatur komposisi data tersebut di frontend.

![Before and After](https://www.drmwn.space/images/content/before-and-after.jpg)

Contoh, disini case nya Breadcumb blog, ingin memanggil data judul blog terkadang judul blog terlalu panjang sehingga mengganggu responsifitas tampilan, sebenarnya kalian bisa mengatasi ini melalui css langsung tapi di artikel ini kita akan bahas melalui JavaScript langsung.

## Let's Go!
Contoh Code
```javascript
var example = "I am too long string";
var result;
```
Kamu bisa tambahkan Slice atau Str Substring
```javascript
// Slice is JS function
result = example.slice(0, 10)+'...'; //titik-titik tersebut merupakan karakter tambahan
```
Maka hasil variable akan menjadi "I am too l..."

Jika kamu memanggil sebuah data seperti ini pada Vue JS
```javascript
const title = "Ini merupakan judul panjang banget banget banget banget banget banget";
```
Pemanggilan data kedalam komponen Vue JS
```javascript
<div>
	<h1>{{  article.title }}</h1>
</div>
```
dan ingin melimit karakter data tersebut, bisa dengan gampang menambahkan
```javascript
<div>
	<h1>{{  article.title.substring(0,18)+"..."  }}</h1>
</div>
```
Maka hasilnya akan menjadi "Ini merupakan judul p..."
angka "18" setelah "0" merupakan jumlah string yang ingin dimunculkan, jadi kalian bisa melimitnya sesuai keinginan.

> Written with [StackEdit](https://stackedit.io/).