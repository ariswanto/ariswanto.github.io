---
id: 218
title: Boot File ISO Langsung dari GRUB2
date: 2011-04-09T01:12:00+00:00
author: Ihsan Ariswanto
layout: post
guid: /uncategorized/boot-file-iso-langsung-dari-grub2/
permalink: /uncategorized/boot-file-iso-langsung-dari-grub2/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2011/04/boot-file-iso-langsung-dari-grub2.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/9021173136422202047
tags:
  - Komputer
  - TUTORIAL GNU/LINUX
---
<div style="text-align: justify;">
  Tujuan: booting CD installer atau LIVE CD GNU/LINUX tanpa harus membakar ke CD atau flashdisk.</p> 
  
  <p>
    Bahan2 percobaan:<br />1. File ISO Puppy Linux,<br />2. GRUB2 yang sudah terinstal (Saya pake GRUB2 di Ubuntu Lucid).
  </p>
  
  <p>
    Langkah-langkah:<a name='more'></a>
  </p>
  
  <p>
    1. buka /etc/grub.d/40_custom (sebagai root)<br />2. Masukkan menu entry puppy, kita misalkan file .iso puppy ada di partisi sda6, di folder Gukguk, ini contohnya:
  </p>
</div>

<div style="text-align: justify;">
  <pre></pre>
  
  <p>
    #!/bin/sh<br />echo &#8220;add entry&#8221; >&2
  </p>
  
  <p>
    exec tail -n +3 $0<br /># This file provides an easy way to add custom menu entries. Simply type the<br /># menu entries you want to add after this comment. Be careful not to change<br /># the &#8216;exec tail&#8217; line above.
  </p>
  
  <p>
    cat << EOF
  </p>
  
  <p>
    menuentry &#8220;Maverick &#8211; Live CD&#8221; {<br />loopback loop (hd0,6)/ihsan/ubuntu-10.10-desktop-i386.iso
  </p>
  
  <p>
    linux (loop)/casper/vmlinuz boot=casper iso-scan/filename=/iso/ubuntu-10.10-desktop-i386.iso noprompt noeject<br />initrd (loop)/casper/initrd.lz<br />}
  </p>
  
  <p>
    menuentry &#8220;Quirky 140 &#8211; Live CD&#8221; {<br />loopback loop (hd0,6)/Gukguk/qrky-140.iso<br />linux (loop)/vmlinuz<br />initrd (loop)/initrd.gz<br />}
  </p>
  
  <p>
    menuentry &#8220;Puppy 520 &#8211; Live CD&#8221; {
  </p>
  
  <p>
    loopback loop (hd0,6)/Gukguk/lupu-520.iso<br />linux (loop)/vmlinuz<br />initrd (loop)/initrd.gz<br />}
  </p>
  
  <p>
    EOF</div> 
    
    <div style="text-align: justify;">
      <p>
        keterangan sda6 = (hd0,6)
      </p>
      
      <p>
        3. Coba cek dulu /etc/default/grub, pastikan dikasih time out agar GRUB2-nya nongol
      </p>
      
      <p>
        GRUB_TIMEOUT=10
      </p>
      
      <p>
        buat nongolin menu entry GRUB2 selama 10 detik
      </p>
      
      <p>
        4. Setelah selesai, ketik sudo update-grub<br />Reboot, insyaAlloh Puppy Live CD bisa muncul di pilihan&#8230;</div>