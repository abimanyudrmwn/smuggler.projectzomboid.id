---
title: "Alasan saya menggunakan Tailwind CSS"
description: Alasan saya menggunakan Tailwind CSS.
frase: Alasan pertama karena Tailwind mungkin satu-staunya framework yang berbasis Utility.
tags:
  - Frontend
  - TailwindCSS
category: Opini
coverImage: alasan-memakai-tailwind.jpg
alt: tailwindCSS
date: 2022-12-02 14:22:52
---

Ceritanya tuh saya lagi ngembangin gtherlink yaitu penggantinya  [linktr.ee](http://linktr.ee/)  gitulah yang saya kembangin sendiri. Masalahnya untuk web apps yang sedang saya buat ini masih Single Page App (SPA) yang emang saya minimalisir penggunaan hostingnya.

Terlepas dari itu saya nyaman dan suka menggunakan Tailwind karena:

## 1. Utility Based


Alasan pertama karena Tailwind mungkin satu-staunya framework yang berbasis Utility. Sedangkan framework yang lainnya kebanyakan berbasis komponen.

Bootstrap memang punya class utility, tapi tidak sebanyak Tailwind. Class-class di Tailwind 100% adalah Utility.

Ini membuat kita bebas membuat komponen sendiri.

## 2. Ukuran File Kecil

Ini mungkin karena Tailwind menggunakan  [PurgeCSS](https://purgecss.com/).

Jadi class-class yang tidak terpakai, tidak akan ditambahkan pada CSS hasil build. Ini membuat CSS-nya lebih kecil.

Berbeda dengan CSS framework yang berbasis komponen. Walaupun kita tidak pakai komponen tertentu, maka class-nya akan tetap ikut ditambahkan di file CSS.

Dulu saya pernah coba PurgeCSS di Bootstrap, tapi hasilnya tidak maksimal. beberapa komponen tidak bisa bekerja dengan normal.

Karena itu, mungkin CSS Framework yang berbasis komponen kurang cocok dipakein PurgeCSS.

Meski terasa mubazir, mau tidak mau harus rela membiarkan class yang tidak terpakai tetap berada di dalam file CSS production.

tentu membebani ukuran file perbandingan hasil build web yang menggunakan Bootstrap dan Tailwind juga signifikan, untuk ukuran dihasil build Bootstrap di 150kb sementara Tailwind cukup unggul di size 30kb sangat jauh beda ukurannya.

## 3. Cocok dipakai dengan Framework JS kekinian

Khususnya sudah hampir 6 bulan saya pakai Vue JS pada Web yang saya buat, setelah saya mengenal Tailwind rasanya jadi lebih mudah dan cocok aja.

mungkin ini cuma perasaan saya aja, belum tentu orang lain juga nyaman menggunakannya 😁

## 4. Lagi Hits

Tailwind memang begitu populer belakangan ini. Banyak web yang mengadopsinya dan review-review-nya menjanjikan.

Baru saja saya dengar kalau Google IO 2022 juga menggunakan TailwindCSS

Cek Tweet nya [disini](https://twitter.com/tailwindcss/status/1520144767887327233)
## 5. Ingin Belajar TailwindCSS


Alasan terakhir karena saya memang ingin belajar Tailwind.

Dulu memang pernah pakai saat masih versi 1, tapi hasil buildnya saya rasa masih kurang optimal. Tidak sebagus sekarang yang versi 3.

Atau mungkin saya yang kurang tau cara build-nya dulu 😄..

Sekarang belajar lagi, mengenal dan membiasakan diri menggunakan class-class Tailwind.
> Written with [StackEdit](https://stackedit.io/).