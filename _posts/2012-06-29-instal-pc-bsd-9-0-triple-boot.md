---
id: 172
title: Instal PC-BSD 9.0, Triple Boot
date: 2012-06-29T23:51:00+00:00
author: Ihsan Ariswanto
layout: post
permalink: /uncategorized/instal-pc-bsd-9-0-triple-boot/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2012/06/instal-pc-bsd-90-triple-boot.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/7933737869154734287
tags:
  - Komputer
  - TUTORIAL GNU/LINUX
---
Akhirnya sukses juga instal PC-BSD 9.0, versi usb-lite, desktopnya pakai LXDE.  
Cara instalnya baca saja di buku petunjuknya: [di wiki PC-BSD.](https://wiki.pcbsd.org/index.php/PC-BSD_Users_Handbook)

Sedikit yang perlu diperhatikan, tadinya repot setting bootloader GRUB2 (tripleboot dg Debian dan Arch). Ikut petunjuk di bukunya tidak berhasil. Akhirnya dapat cara dari googling, ternyata cukup gampang:  
<a name='more'></a>

<lj-cut text="Read more..."></lj-cut>  
Tinggal masukan menuentry di /etc/grub.d/40_custom milik Debian, seperti ini:  
<a href="https://www.blogger.com/null" name="more"></a>

<div style="margin-bottom: 2px;">
  Code:
</div>

<pre style="background: none repeat scroll 0% 0% #e1e4f2; border: 1px inset; font-family: monospace; font-size: 0.9em; line-height: 1.25; margin: 0px; overflow: auto; padding: 6px; text-align: left;"><br />menuentry "PCBSD 9.0" {<br />set root=(hd0,2)<br />chainloader +1<br />}</pre>

Sukses login PC-BSD 9.0.

Habis itu setting modem USB GSM (Sierra 305), setingannya nyomot di google lupa dari mana tadi sumbernya. Kalau gak salah aslinya setingan buat huawei, tapi jalan juga saya coba buat sierra. (<img alt="" border="0" ilo-full-src="/wp-content/uploads/2012/06/malus.gif" src="/wp-content/uploads/2012/06/malus.gif" title="Malu (S)" />)

Setingan /etc/ppp/ppp.conf seperti ini (pakai kartu Tri):

<div style="margin-bottom: 2px;">
  Code:
</div>

<pre style="background: none repeat scroll 0% 0% #e1e4f2; border: 1px inset; font-family: monospace; font-size: 0.9em; line-height: 1.25; margin: 0px; overflow: auto; padding: 6px; text-align: left;"><br />default:<br />  set log local Phase Chat LCP IPCP CCP tun command<br />  disable pred1 deflate deflate24 protocomp acfcomp shortseq vj<br />  deny pred1 deflate deflate24 protocomp acfcomp shortseq vj<br />  set speed 9600<br />tri:<br />  set login<br />  set device /dev/cuaU0.0<br />  set phone *99#<br />  set dial "ABORT BUSY ABORT NO\sCARRIER<br />  TIMEOUT 5 <br />  "" ATE1 <br />  OK-AT-OK ATQ0V1X4 OK <br />  AT+CGDCONT=1,\"ip\",\"3data\" <br />  OK \dATDT\T <br />  TIMEOUT 45 <br />  CONNECT"<br />  set authname 3data<br />  set authkey 3data<br />  set ifaddr 10.0.0.1/0 10.0.0.2/0 255.255.255.2555 0.0.0.0<br />  enable dns<br />  add! default HISADDR<br />  disable ipv6<br />  disable lqr</pre>

Seting /etc/ppp/ppp.linkup:

<div style="margin-bottom: 2px;">
  Code:
</div>

<pre style="background: none repeat scroll 0% 0% #e1e4f2; border: 1px inset; font-family: monospace; font-size: 0.9em; line-height: 1.25; margin: 0px; overflow: auto; padding: 6px; text-align: left;"><br />tri:<br />  shell route delete default<br />  shell route add default -interface INTERFACE<br />  delete ALL</pre>

Seting /etc/ppp/ppp.linkdown:

<div style="margin-bottom: 2px;">
  Code:
</div>

<pre style="background: none repeat scroll 0% 0% #e1e4f2; border: 1px inset; font-family: monospace; font-size: 0.9em; line-height: 1.25; margin: 0px; overflow: auto; padding: 6px; text-align: left;"><br />tri:<br />   shell route delete default</pre>

Kalu sudah tinggal ketik peintah:  
**sudo ppp**

muncul tanda >

ketik lagi:  
**dial tri**

Kalau tulisan **ppp** berubah jadi **PPP**, berarti udah konek.