---
id: 169
title: Review Instal Ubuntu 12.04 LTS di Netbook Aspire One D270
date: 2012-11-12T15:19:00+00:00
author: Ihsan Ariswanto
layout: post
permalink: /uncategorized/review-instal-ubuntu-12-04-lts-di-netbook-aspire-one-d270/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2012/11/review-instal-ubuntu-1204-lts-di.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/7851329913872291775
tags:
  - Komputer
  - REVIEW HARDWARE
---
<div style="text-align: justify;">
  <div style="clear: both; text-align: center;">
    <a href="http://www.ubuntu.com/download/desktop" target="_blank"><img border="0" height="169" src="/wp-content/uploads/2012/11/Ubuntu-4.12-LTS-300x159.jpg" width="320" /></a>
  </div>
  
  <div style="text-align: center;">
  </div>
  
  <p>
    <i>Prolog: </i></div> 
    
    <div style="text-align: justify;">
      <i><br /></i>
    </div>
    
    <div style="text-align: justify;">
      <i>Acer Aspire One D270 mengusung CPU intel Atom N2600. Intel dikenal sebagai produsen hardware yang ramah Linux, karena intel adalah salah satu sponsor kernel linux.</i>
    </div>
    
    <div style="text-align: justify;">
      <i><br /></i>
    </div>
    
    <div style="text-align: justify;">
      <i>Masalahnya netbook ini memakai kartu grafis DMA 3600 (aka Cedar Trail). yang, walaupun bermerek Intel, tetapi adalah buatan PowerVR. Sayangnya PowerVR (pada awalnya) tidak merilis kode sumber untuk drivernya. Satu-satunya driver yang tersedia hanya untuk Windows 7 32bit.</i>
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      <i>Untungnya pada bulan April, Intel mengeluarkan driver tertutup (proprietary) DMA 3600 untuk distro <a href="https://meego.com/">Meego</a>. Canonical sukses mem-port driver ini untuk Ubuntu.</i><br /><a name='more'></a><br /><a href="http://www.blogger.com/null" name="more"></a>
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Instalasi Ubuntu 12.04 tidak ada masalah kecuali kartu grafis tersebut yang tidak didukung kernel bawaan. Akibatnya, video tidak lancar diputar <i>fullscreen</i>.
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Untuk mengatasinya, lakukan update sistem Ubuntu Anda (otomatis disarankan). Yang perlu Anda lakukan adalah terhubung dengan internet.
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Selesai update, Anda akan disarankan menginstal driver tertutup untuk wifi broadcom (1 driver) dan untuk kartu grafis DMA 3600 (ada 2 driver).
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Selesai instal driver, Anda perlu restart komputer. Kartu grafis Anda sudah didukung&nbsp; dan bisa memutar video dengan lancar.
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Untuk performa batre-nya, kernel bawaan bisa mengaturnya dengan baik. Pemakaian wajar bisa tahan hingga 6 jam lebih.
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Kesimpulan: Jika Anda anti dengan software proprietary, maka netbook ini tidak cocok untuk Anda.
    </div>
    
    <div style="text-align: justify;">
    </div>
    
    <div style="text-align: justify;">
      Catatan:
    </div>
    
    <ul>
      <li>
        Saya tidak mencoba wifi-nya sebelum instal driver, saya memakai modem GSM, jadi tidak tahu apakah wifi bisa jalan tanpa driver tambahan atau tidak. Tapi tampaknya bisa jalan, karena terdeteksi di panel atas.
      </li>
      <li>
        Untuk bisa memutar banyak format video, instal dulu Ubuntu restricted extras. Bisa diinstal dari software center.
      </li>
    </ul>