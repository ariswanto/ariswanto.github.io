---
id: 166
title: Instal Printer HP K110a di Debian Squeeze
date: 2013-03-04T18:31:00+00:00
author: Ihsan Ariswanto
layout: post
permalink: /uncategorized/instal-printer-hp-k110a-di-debian-squeeze/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2013/03/instal-printer-hp-k110a-di-debian.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/1493042035978888371
tags:
  - Komputer
  - REVIEW HARDWARE
  - TUTORIAL GNU/LINUX
---
<div style="clear: both; text-align: center;">
</div>

<div style="text-align: center;">
  <div style="text-align: justify;">
    Nama lengkap printer ini adalah <b>HP Deskjet Ink Advantage 2060 ALL-IN-ONE K110</b>. Saya beli dengan harga Rp 660.000 di satu toko komputer dekat UGM.</p> 
    
    <p>
      Printer ini dilengkapi dengan <i>scanner</i> yang juga bisa digunakan untuk foto kopi tanpa harus terhubung ke komputer.<br /><a name='more'></a></div> 
      
      <div style="text-align: justify;">
      </div>
      
      <table align="center" cellpadding="0" cellspacing="0" style="margin-left: auto; margin-right: auto; text-align: center;">
        <tr>
          <td style="text-align: center;">
            <a href="/wp-content/uploads/2013/03/Untitled.jpg" style="margin-left: auto; margin-right: auto;"><img border="0" height="331" src="/wp-content/uploads/2013/03/Untitled-300x249.jpg" width="400" /></a>
          </td>
        </tr>
        
        <tr>
          <td style="text-align: center;">
            Penampakan printer HP K110a di rumah saya
          </td>
          
          <td style="text-align: center;">
          </td>
          
          <td style="text-align: center;">
          </td>
        </tr>
      </table>
      
      <div style="text-align: justify;">
        Seperti produk HP lain, printer ini bisa jalan dengan baik di linux berkat driver HPLIP. Sayangnya, di Debiaan Squeeze, versi HPLIP-nya jadul, sehingga printer terdeteksi, namun scanner-nya tidak terdeteksi.</p> 
        
        <p>
          Tapi jangan khawatir, kita bisa instal HPLIP terbaru dengan mudah langsung dari web-nya HPLIP. Caranya akan kita bahas berikut ini.<br /><a href="http://www.blogger.com/null" name="more"></a>
        </p>
        
        <p>
          <i><b>PERSIAPAN:</b></i> 
          
          <ul>
            <li>
              Pastikan komputer terhubung dengan internet. Karena yang didonlot agak besar (20 MB), maka perlu koneksi yang lumayan kencang.
            </li>
            <li>
              Usahakan komputer terhubung dengan UPS kalau tempat Anda rawan mati listrik. Untuk laptop, sebaiknya dalam kondisi dicharge. Ini penting, karena HPLIP-nya harus dicompile.
            </li>
          </ul>
          
          <p>
            <i><b>&nbsp;DOWNLOAD dan INSTAL</b></i>:</div> 
            
            <div style="text-align: justify;">
              <ul>
                <li>
                  Download dengan install wizard, buka: <a href="http://hplipopensource.com/hplip-web/install_wizard/index.html">http://hplipopensource.com/hplip-web/install_wizard/index.html</a>
                </li>
                <li>
                  Pilih Distro dan tipe printernya (lihat gambar di bawah ini). kalau sudah, klik next.
                </li>
              </ul>
            </div>
            
            <div style="clear: both; text-align: center;">
              <a href="/wp-content/uploads/2013/03/1.jpg" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="244" src="/wp-content/uploads/2013/03/1-300x230.jpg" width="320" /></a>
            </div>
            
            <div style="text-align: justify;">
            </div>
            
            <p>
              <ul style="text-align: justify;">
                <li>
                  <span style="font-size: small;">klik next, akan munc<span style="font-size: small;">ul:</span></span>
                </li>
              </ul>
              
              <div style="clear: both; text-align: center;">
                <a href="/wp-content/uploads/2013/03/Screenshot-1.png" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="160" src="/wp-content/uploads/2013/03/Screenshot-1-300x152.png" width="320" /></a>
              </div>
              
              <div style="text-align: justify;">
                <span style="font-size: small;"><span style="font-size: small;">&nbsp;</span> </span>
              </div>
              
              <ul style="text-align: justify;">
                <li>
                  <span style="font-size: small;">Kilik next lagi<span style="font-size: small;">. Selanjutnya akan muncul halaman panduan. Anda tinggal ikuti <span style="font-size: small;">langkah-langkah yang disebutkan di sana.</span></span></span>
                </li>
                <li>
                  Selesai proses instal, printer. Selamat, printer dan scanner Anda sudah terdeteksi 😀
                </li>
                <li>
                  &nbsp;
                </li>
              </ul>
              
              <div style="text-align: justify;">
                <i><b>PASCA INSTAL&nbsp;</b></i>
              </div>
              
              <div style="text-align: justify;">
              </div>
              
              <div style="text-align: justify;">
                Untuk men-scan lebih gampang, Andai perlu software khusus bernama <b>XSANE</b>. Cara downloadnya, buka saja System >> Administration >> Synaptic, lalu cari xsane. Atau ketik di terminal: <i><b>sudo apt-get install xsane.</b></i>
              </div>
              
              <div style="text-align: justify;">
              </div>
              
              <div style="text-align: justify;">
                Dan agar hasil scan bisa diubah menjadi text, perlu instal <b>GOCR</b>. Caranya sama, cari di Synaptic. Atau ketik di terminal: <i><b>sudo apt-get install gocr.</b></i>
              </div>
              
              <p>
                <div style="text-align: justify;">
                  <div style="clear: both; text-align: center;">
                  </div>
                </div></div>