---
id: 158
title: 'Ganti distro lagi: dari Slackware 14 ke Trisquel 6'
date: 2013-11-16T20:53:00+00:00
author: Ihsan Ariswanto
layout: post
permalink: /uncategorized/ganti-distro-lagi-dari-slackware-14-ke-trisquel-6/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2013/11/ganti-distro-lagi-dari-slackware-14-ke.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/6410346708908389454
tags:
  - Komputer
  - REVIEW SOFTWARE
  - TUTORIAL GNU/LINUX
---
<div style="text-align: justify;">
  Setelah beberapa bulan cukup nyaman dengan Slackware 14, kemarin malam aku putuskan untuk pindah ke distro lain. Sebenarnya aku tak ada masalah dengan Slackware 14, namun gara-gara instal <a href="https://www.droplinegnome.org/" target="_blank">dropline-gnome</a> yang setengah-setengah, beberapa library jadi agak kacau.<br /><a name='more'></a>
</div>

<div style="text-align: justify;">
  Aku pikir-pikir daripada memperbaiki instalasi dengan mendowload paket-paket Slackware 14, lebih baik aku instal ulang saja, sekalian ganti suasana. Sempat terpikir untuk menginstal <a href="https://www.slackware.com/" target="_blank">Slakware terbaru (14.1)</a>, namun karena file iso-nya cukup besar (versi DVD lebih dari 2GB) sepertinya akan memakan waktu lama, dan emmm&#8230; boros kuota juga.
</div>

<div style="text-align: justify;">
</div>

<div style="text-align: justify;">
  Selain itu, karena sedang ingin belajar software itung duit <a href="https://www.gnucash.org/" target="_blank">GnuCash</a> (yang di Slackware harus build dari source), sepertinya lebih baik pindah distro lain yang lebih manusiawi.. :-D.&nbsp;
</div>

<div style="text-align: justify;">
</div>

<div style="text-align: justify;">
  Kebetulan di hard disk sudah ada 2 iso, satunya Trisquel 6, dan satunya lagi Zorin OS, hasil download dari <a href="httpss://facebook.com/groups/631892160170483" target="_blank">grup facebook</a> (dulu waktu AON masih bisa diajak kerjasama&#8230;). Keduanya sama-sama turunan Ubuntu, jadi tak jauh beda.
</div>

<div style="text-align: justify;">
</div>

<div style="text-align: justify;">
  Pilihan jatuh ke <a href="https://trisquel.info/" target="_blank">Trisquel</a> (baca: Triskel) dengan pertimbangan:
</div>

  * Trisquel lebih istimewa karena <a href="https://en.wikipedia.org/wiki/Free_software" target="_blank">100% libre </a>dan sudah <a href="https://www.gnu.org/distros/free-distros.html" target="_blank">diberkati</a> oleh <a href="https://en.wikipedia.org/wiki/Richard_Stallman" target="_blank">Mbah Stallman,</a> hehe. Semua hardwareku tak perlu driver non-libre, jadi gak akan ada masalah.
  * Pengen pindah ke 64 bit, kebetulan iso Trisquelnya versi 64 juga. Alasan milih 64bit: kalau pas main-main virtualbox, 32bit tidak bisa jalankan virtual 64bit, tapi 64bit bisa jalankan virtual 32bit.

<div style="text-align: justify;">
  Ya sudah, tanpa babibu, langsung iso Trisquel dibakar ke flashdisk memakai Unetbootin.&nbsp; tancap. setting bios, reboot. Masuk instalasi dst dll. Format partisi untuk /. Proses instal tak sampai 15 menit. Restart dan&#8230;. jreng&#8230; jreng&#8230;. Trisquel 6 dengan gnome classic (tampilan defaultnya).
</div>

<div style="text-align: justify;">
</div>

<div style="clear: both; text-align: center;">
  <a href="/wp-content/uploads/2013/11/Trisquel_6.0_LTS_screenshot.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="300" src="/wp-content/uploads/2013/11/Trisquel_6.0_LTS_screenshot-300x225.png" width="400" /></a>
</div>

<div style="text-align: justify;">
</div>

<div style="text-align: justify;">
  Oke.. ritual selanjutnya sebagaimana distro berbasis deb lain adalah:&nbsp;
</div>

> <div style="text-align: justify;">
>   <span style="font-family: &quot;Helvetica Neue&quot;,Arial,Helvetica,sans-serif;">sudo apt-get update && sudo apt-get upgrade</span>
> </div>

Selanjutnya, karena pengen tampilan Gnome Shell (bukan classic), jadi saya instal paket minimalnya:

> <span style="font-family: &quot;Helvetica Neue&quot;,Arial,Helvetica,sans-serif;">sudo apt-get install gnome-session gnome-shell</span>

Logout, lalu masuk lagi dengan pilih gnome. Ganti-ganti wallpaper. Tweak-tweak sedikit dengan extension. Hasilnya&#8230;. 



<div style="clear: both; text-align: center;">
  <a href="/wp-content/uploads/2013/11/Screenshot-from-2013-11-16-20-26-34.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="300" src="/wp-content/uploads/2013/11/Screenshot-from-2013-11-16-20-26-34-300x225.png" width="400" /></a>
</div>

<div style="text-align: center;">
  <a href="/wp-content/uploads/2013/11/Screenshot-from-2013-11-16-20-25-54.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="300" src="/wp-content/uploads/2013/11/Screenshot-from-2013-11-16-20-25-54-300x225.png" width="400" />&nbsp;</a>
</div>

<div style="text-align: justify;">
</div>

<div style="text-align: justify;">
  Semua hardware jalan dengan baik. Performa oke, tidak nge-lag atau lambat. Beberapa catatan aja:
</div>

  * Browser&nbsp; bawaan Trisquel adalah &#8220;a browser&#8221; alias browser tanpa nama. Sebenarnya ini Firefox yang dikostumisasi. Setelah diupgrade, versinya jadi 25, sama seperti Firefox.
  * Karena 100% libre, jadi jangan harap ada adobe flash. Sebagai gantinya telah terinstal gnash. Aku coba buka Youtube, jalan, tapi sedikit gak mulus.
  * Libreoffice bawaan, versi 3.X.X. Aku uninstal dan instal versi terbaru (4.1) dari libreoffice.org (pilih versi deb).
  * Software lain sama seperti yang ada di Ubuntu 12.04 LTS, Trisquel 6 juga kompatibel dengan repo Ubuntu 12.04 LTS. Bedanya di Trisquel tak ada software&nbsp; non-libre.
  * Trisquel 6 akan disupport sampai tahun 2017, sama seperti Ubuntu 12.04 LTS.
  * Mulai versi 6 ini, Trisquel hanya merilis versi LTS saja, tidak lagi 6 bulanan.