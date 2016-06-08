---
layout: post
title: Masalah Laptop Kepanasan Sudah Teratasi dengan Thermald
summary: Baru tahu ada daemon khusus Intel untuk mengatur temperatur prosesor. Namanya thermald.
category: komputer
---

Ke mana saja saya selama ini ya? Baru tahu ada <em>daemon</em> khusus Intel untuk 
mengatur temperatur prosesor. Namanya thermald (<a href="httpss://01.org/linux-thermal-daemon">linux thermal daemon</a>).

Selama ini saya manual saja menjaga laptop agar tidak panas. Tidak menjalankan aplikasi berat, menghindari kompilasi, sampai-sampai 
tak berani memakai KDE karena Nepomuk-nya bisa membuat laptop mati karena kepanasan saat mengindeks.

Atau jangan-jangan saya dulu pernah tahu thermald, kemudian lupa. Soalnya dulu tidak pernah kena masalah panas saat memakai KDE di Slackware.

Thermald ini menjaga kinerja prosesor. Kalau prosesor terlalu kencang bekerja sampai mendekati panas, thermald akan menyuruh prosesor untuk <em>alon-alon wae mas</em>. Kalau sudah turun suhunya, baru digeber lagi. Demikian seterusnya.

Saya instal thermald dari <a href="https://slackbuilds.org/repository/14.1/system/thermal_daemon/">slackbuilds</a>, dan masalah kepanasan selesai sudah.

