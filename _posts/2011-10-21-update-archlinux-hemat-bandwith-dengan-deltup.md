---
id: 200
title: Update Archlinux Hemat Bandwith dengan Deltup
date: 2011-10-21T15:05:00+00:00
author: Ihsan Ariswanto
layout: post
guid: /uncategorized/update-archlinux-hemat-bandwith-dengan-deltup/
permalink: /uncategorized/update-archlinux-hemat-bandwith-dengan-deltup/
blogger_blog:
  - ihsanariswanto.blogspot.com
blogger_author:
  - ihsan
blogger_permalink:
  - /2011/10/update-archlinux-hemat-bandwith-dengan.html
blogger_internal:
  - /feeds/811343025317713881/posts/default/591952616615284665
tags:
  - Komputer
  - TUTORIAL GNU/LINUX
---
<div style="text-align: justify;">
  Sebagai distro rolling release, Arch Linux memang menuntut untuk sering-sering update sistem. Bagi yang punya koneksi dewa tentu gak masalah. Tapi bagi yang koneksinya pas-pasan, apalagi terbatas quota, perlu cari cara untuk sedikit lebih ngirit bandwith.</p> 
  
  <p>
    Cara menyiasatinya bisa dengan deltup (delta update). Intinya, delta hanya akan mendowload perbedaan atau selisih antara versi paket yang telah terinstal dengan versi paket yang baru, kemudian menggabungkan ulang (rebuild). Berikut langkah instal dan setting deltup di Archlinux kita.</div> 
    
    <p>
      <a name='more'></a>
    </p>
    
    <div style="text-align: justify;">
      <span>1. Instal paket xdelta3</span>
    </div>
    
    <pre><blockquote>
  # pacman -S xdelta3
</blockquote></pre>
    
    <div style="text-align: justify;">
      <span>2. Edit file</span><span style="font-weight: bold;"> <span style="color: rgb(51, 51, 255);">/etc/pacman.d/mirrorlist</span></span>, masukkan repo yang mendukung delta, salah satunya repo Delta Archlinux.fr
    </div>
    
    <p>
    </p>
    
    <pre style="white-space: pre-wrap; overflow-x: auto; padding: 0.25em; margin: 0 0 0.50em 0; background-color: #F7F7F7; border: thin dashed #7F7F7F; border-top: none">##<br />## Arch Linux repository mirrorlist<br />## Generated on 2011-03-24<br />##<br /><br />## Delta Archlinux.fr<br />Server = https://delta.archlinux.fr/$repo/os/$arch<br />.....</pre>
    
    <p>
    </p>
    
    <div style="text-align: justify;">
      3. Sebelum mengaktifkan repo delta, kita bisa cek dulu, gimana bedanya sebelum dan sesudah memakai deltup.
    </div>
    
    <div style="margin: 5px;">
      <div style="margin-bottom: 2px;">
        <i><span style="font-weight: bold;">Sebelum </span></i>
      </div>
      
      <p>
        <div style="border: 1px inset ; margin: 0px; padding: 6px;">
          <div style="display: none;">
            <div style="padding: 0.5em; line-height: 1.1; background-color: #333; color: #eee; border: 1px solid #08c">
              <code>#  pacman -Syu&lt;/p>
&lt;p>:: Synchronizing package databases...&lt;br />kde4-eyecandy-64 is up to date&lt;br />core is up to date&lt;br />extra is up to date&lt;br />community is up to date&lt;br />multilib is up to date&lt;br />:: Starting full system upgrade...&lt;br />warning: frozen-bubble: ignoring package upgrade (2.2.0-3 =&gt; 2.2.1beta1-1)&lt;br />:: Replace lib32-libjpeg with multilib/lib32-libjpeg-turbo? [Y/n]&lt;br />:: Replace vlc-plugin with extra/vlc? [Y/n]&lt;br />warning: warmux: ignoring package upgrade (11.01-1 =&gt; 11.04.1-3)&lt;br />resolving dependencies...&lt;br />warning: dependency cycle detected:&lt;br />warning: lib32-gcc-libs will be installed before its %s dependency gcc-libs-multilib&lt;br />looking for inter-conflicts...&lt;/p>
&lt;p>Remove (2): lib32-libjpeg-8.3.0-1 [0,48 MB]  vlc-plugin-1.1.9-1 [0,13 MB]&lt;/p>
&lt;p>Total Removed Size:   0,61 MB&lt;/p>
&lt;p>Targets (147): attr-2.4.46-1 [0,06 MB]  acl-2.2.51-1 [0,13 MB]  acpid-2.0.10-2 [0,04 MB]&lt;br />     lib32-gcc-libs-4.6.0-6 [0,71 MB]  gcc-libs-multilib-4.6.0-6 [0,73 MB]&lt;br />     icu-4.8-1 [5,10 MB]  boost-libs-1.46.1-3 [1,49 MB]  libmysqlclient-5.5.13-1 [2,92 MB]&lt;br />     mysql-clients-5.5.13-1 [0,79 MB]  mysql-5.5.13-1 [5,70 MB]  akonadi-1.5.3-2 [0,63 MB]&lt;br />     util-linux-2.19.1-2 [1,37 MB]  apr-1.4.5-1 [0,22 MB]  apr-util-1.3.12-1 [0,14 MB]&lt;br />     sqlite3-3.7.6.3-1 [0,36 MB]  glib2-2.28.8-1 [1,58 MB]  gstreamer0.10-0.10.34-1 [1,33 MB]&lt;br />     gstreamer0.10-base-0.10.34-1 [1,13 MB]  gnutls-2.12.6.1-1 [1,49 MB]&lt;br />     glib-networking-2.28.7-1 [0,04 MB]  libsoup-2.34.2-1 [0,30 MB]&lt;br />     hunspell-1.3.2-1 [0,18 MB]  enchant-1.6.0-2 [0,03 MB]  libwebkit-1.4.1-1 [5,03 MB]&lt;br />     pango-1.28.4-3 [0,48 MB]  gstreamer0.10-base-plugins-0.10.34-1 [0,16 MB]&lt;br />     banshee-2.0.1-2 [2,57 MB]  binutils-multilib-2.21-8 [3,25 MB]  bison-2.5-1 [0,42 MB]&lt;br />     bluez-4.93-2 [0,49 MB]  boost-1.46.1-3 [6,56 MB]  cairomm-1.10.0-1 [0,41 MB]&lt;br />     ccrtp-1.8.0-1 [0,17 MB]  nspr-4.8.8-1 [0,22 MB]  nss-3.12.10-1 [1,37 MB]&lt;br />     chromium-12.0.742.91-1 [19,41 MB]  consolekit-0.4.5-1 [0,08 MB]  gmp-5.0.2-1 [0,41 MB]&lt;br />     coreutils-8.12-2 [2,00 MB]  module-init-tools-3.13-1 [0,34 MB]  udev-171-2 [0,20 MB]&lt;br />     device-mapper-2.02.85-2 [0,12 MB]  cryptsetup-1.3.1-1 [0,09 MB]&lt;br />     libssh2-1.2.7-2 [0,17 MB]  curl-7.21.6-2 [0,46 MB]  libgnome-keyring-3.0.3-1 [0,09 MB]&lt;br />     libsoup-gnome-2.34.2-1 [0,01 MB]  icon-naming-utils-0.8.90-2 [0,01 MB]&lt;br />     gnome-icon-theme-3.0.0-2 [8,21 MB]  libgweather-3.0.2-1 [2,15 MB]&lt;br />     evolution-data-server-3.0.2.1-1 [2,48 MB]  fam-2.7.0-15 [0,07 MB]&lt;br />     gstreamer0.10-good-0.10.29-1 [0,94 MB]  gstreamer0.10-bad-0.10.22-1 [0,83 MB]&lt;br />     farsight2-0.0.28-2 [0,21 MB]  file-5.07-3 [0,19 MB]  nspluginwrapper-1.4.2-1 [0,13 MB]&lt;br />     flashplugin-10.3.181.22-1 [6,02 MB]  gcc-multilib-4.6.0-6 [17,44 MB]&lt;br />     glew-1.6.0-1 [0,28 MB]  startup-notification-0.12-1 [0,02 MB]  libcups-1.4.6-3 [0,26 MB]&lt;br />     gtk3-3.0.11-1 [4,66 MB]  gnome-desktop-3.0.2-1 [0,48 MB]  libwnck3-3.0.2-1 [0,34 MB]&lt;br />     telepathy-glib-0.14.7-1 [1,07 MB]  gnome-panel-3.0.2-1 [1,49 MB]  gperf-3.0.4-3 [0,09 MB]&lt;br />     grep-2.8-1 [0,17 MB]  libjpeg-turbo-1.1.1-1 [0,20 MB]  v4l-utils-0.8.4-1 [0,23 MB]&lt;br />     jack-0.120.2-1 [0,28 MB]  gstreamer0.10-good-plugins-0.10.29-1 [0,31 MB]&lt;br />     gvfs-1.8.2-1 [0,80 MB]  help2man-1.39.4-1 [0,06 MB]  iproute2-2.6.38-3 [0,36 MB]&lt;br />     kbd-1.15.3-1 [0,98 MB]  initscripts-2011.06.3-1 [0,02 MB]  poppler-0.16.5-1 [0,71 MB]&lt;br />     poppler-glib-0.16.5-1 [0,17 MB]  inkscape-0.48.1-3 [12,51 MB]&lt;br />     inputproto-2.0.2-1 [0,04 MB]  jre-6u26-1 [20,85 MB]  kdesdk-okteta-4.6.3-2 [0,54 MB]&lt;br />     kdesdk-scripts-4.6.3-2 [0,17 MB]  linux-firmware-20110512-2 [9,17 MB]&lt;br />     mkinitcpio-busybox-1.18.4-1 [0,16 MB]  mkinitcpio-0.6.12-1 [0,02 MB]&lt;br />     kernel26-2.6.38.8-1 [35,93 MB]  kernel26-headers-2.6.38.8-1 [4,18 MB]&lt;br />     laptop-mode-tools-1.57-3 [0,05 MB]  less-443-2 [0,09 MB]&lt;br />     lib32-libjpeg-turbo-1.1.1-1 [0,14 MB]  libass-0.9.12-1 [0,06 MB]&lt;br />     libdvbpsi-0.2.0-1 [0,05 MB]  libftdi-0.19-1 [0,04 MB]  libgsf-1.14.21-1 [0,18 MB]&lt;br />     libgssglue-0.1-4 [0,03 MB]  libwps-0.2.2-1 [0,04 MB]  neon-0.29.6-1 [0,17 MB]&lt;br />     libtextcat-2.2-8 [0,29 MB]  libreoffice-3.4.0-2 [73,84 MB]&lt;br />     libreoffice-ru-3.4.0-1 [7,76 MB]  libssh-0.5.0-1 [0,11 MB]&lt;br />     libvncserver-0.9.8-2 [0,23 MB]  libzrtpcpp-1.4.2-5 [0,09 MB]  lvm2-2.02.85-2 [0,54 MB]&lt;br />     lzo2-2.05-1 [0,07 MB]  make-3.82-3 [0,34 MB]  man-db-2.6.0.2-2 [0,38 MB]&lt;br />     mercurial-1.8.4-1 [1,36 MB]  net-tools-1.60-16 [0,10 MB]  qt-4.7.3-2 [24,12 MB]&lt;br />     ntrack-1:13-2 [0,03 MB]  parted-2.4-1 [0,47 MB]  perl-capture-tiny-0.11-1 [0,01 MB]&lt;br />     php-5.3.6-4 [2,90 MB]  php-pear-5.3.6-4 [0,24 MB]  pixman-0.22.0-1 [0,16 MB]&lt;br />     pkg-config-0.26-1 [0,03 MB]  poppler-qt-0.16.5-1 [0,11 MB]  raptor-2.0.3-1 [0,23 MB]&lt;br />     skype-2.2.0.35-1 [21,56 MB]  sox-14.3.2-3 [0,49 MB]  strigi-0.7.5-1 [0,67 MB]&lt;br />     sudo-1.8.1.p2-1 [0,37 MB]  telepathy-farsight-0.0.18-1 [0,04 MB]&lt;br />     telepathy-qt4-0.6.1-1 [1,16 MB]  twinkle-1.4.2-10 [1,23 MB]  udisks-1.0.3-3 [0,15 MB]&lt;br />     upower-0.9.11-1 [0,09 MB]  virtualbox-4.0.8-2 [16,53 MB]  vlc-1.1.10-1 [7,07 MB]&lt;br />     vte-common-0.28.0-2 [0,00 MB]  vte-0.28.0-2 [0,33 MB]  vte3-0.28.0-2 [0,32 MB]&lt;br />     webkit-sharp-0.3-2 [0,02 MB]  wine-1.3.21-2 [25,78 MB]  xorg-iceauth-1.0.5-1 [0,01 MB]&lt;br />     xorg-server-common-1.10.2-1 [0,02 MB]  xorg-server-1.10.2-1 [1,21 MB]&lt;br />     xorg-xauth-1.0.6-1 [0,02 MB]  xorg-xlsclients-1.1.2-1 [0,01 MB]  xterm-270-1 [0,22 MB]&lt;br />     xulrunner-2.0.1-2 [18,57 MB]  xvidcore-1.3.2-1 [0,25 MB]  xz-5.0.3-1 [0,31 MB]&lt;/p>
&lt;p>Total Download Size:   416,89 MB&lt;br />Total Installed Size:   1933,56 MB&lt;/p>
&lt;p>Proceed with installation? [Y/n]</code>
            </div></p>
          </div>
        </div></div> 
        
        <p>
          Total update 416,89 MB. Pilih N untuk membatalkan.
        </p>
        
        <div style="text-align: justify;">
          4. Edit file <span style="font-weight: bold; color: rgb(51, 51, 255);">/etc/pacman.conf</span>, buang komentar (tanda #) pada pilihan UseDelta, jadinya seperti ini:
        </div>
        
        <p>
        </p>
        
        <pre style="white-space: pre-wrap; overflow-x: auto; padding: 0.25em; margin: 0 0 0.50em 0; background-color: #F7F7F7; border: thin dashed #7F7F7F; border-top: none">.....<br /># Misc options (all disabled by default)<br />#UseSyslog<br />ShowSize<br />UseDelta<br />TotalDownload<br />.....</pre>
        
        <div style="text-align: justify;">
          5. Sekarang kita coba lagi setelah mengaktifkan deltup,
        </div>
        
        <p>
        </p>
        
        <div style="margin: 5px;">
          <div style="margin-bottom: 2px;">
            <i><span style="font-weight: bold;">Sesudah </span></i>
          </div>
          
          <p>
            <div style="border: 1px inset ; margin: 0px; padding: 6px;">
              <div style="display: none;">
                <div style="padding: 0.5em; line-height: 1.1; background-color: #333; color: #eee; border: 1px solid #08c">
                  <code># pacman -Syu&lt;/p>
&lt;p>:: Synchronizing package databases...&lt;br />kde4-eyecandy-64 is up to date&lt;br />core is up to date&lt;br />extra is up to date&lt;br />community is up to date&lt;br />multilib is up to date&lt;br />:: Starting full system upgrade...&lt;br />warning: frozen-bubble: ignoring package upgrade (2.2.0-3 =&gt; 2.2.1beta1-1)&lt;br />:: Replace lib32-libjpeg with multilib/lib32-libjpeg-turbo? [Y/n]&lt;br />:: Replace vlc-plugin with extra/vlc? [Y/n]&lt;br />warning: warmux: ignoring package upgrade (11.01-1 =&gt; 11.04.1-3)&lt;br />resolving dependencies...&lt;br />warning: dependency cycle detected:&lt;br />warning: lib32-gcc-libs will be installed before its %s dependency gcc-libs-multilib&lt;br />looking for inter-conflicts...&lt;/p>
&lt;p>Remove (2): lib32-libjpeg-8.3.0-1 [0,48 MB]  vlc-plugin-1.1.9-1 [0,13 MB]&lt;/p>
&lt;p>Total Removed Size:   0,61 MB&lt;/p>
&lt;p>Targets (147): attr-2.4.46-1 [0,06 MB]  acl-2.2.51-1 [0,13 MB]  acpid-2.0.10-2 [0,04 MB]&lt;br />       lib32-gcc-libs-4.6.0-6 [0,71 MB]  gcc-libs-multilib-4.6.0-6 [0,73 MB]&lt;br />       icu-4.8-1 [5,10 MB]  boost-libs-1.46.1-3 [1,49 MB]  libmysqlclient-5.5.13-1 [2,92 MB]&lt;br />       mysql-clients-5.5.13-1 [0,79 MB]  mysql-5.5.13-1 [5,70 MB]  akonadi-1.5.3-2 [0,63 MB]&lt;br />       util-linux-2.19.1-2 [1,37 MB]  apr-1.4.5-1 [0,22 MB]  apr-util-1.3.12-1 [0,14 MB]&lt;br />       sqlite3-3.7.6.3-1 [0,36 MB]  glib2-2.28.8-1 [1,58 MB]  gstreamer0.10-0.10.34-1 [1,33 MB]&lt;br />       gstreamer0.10-base-0.10.34-1 [1,13 MB]  gnutls-2.12.6.1-1 [1,49 MB]&lt;br />       glib-networking-2.28.7-1 [0,04 MB]  libsoup-2.34.2-1 [0,30 MB]&lt;br />       hunspell-1.3.2-1 [0,18 MB]  enchant-1.6.0-2 [0,03 MB]  libwebkit-1.4.1-1 [5,03 MB]&lt;br />       pango-1.28.4-3 [0,48 MB]  gstreamer0.10-base-plugins-0.10.34-1 [0,16 MB]&lt;br />       banshee-2.0.1-2 [2,57 MB]  binutils-multilib-2.21-8 [3,25 MB]  bison-2.5-1 [0,42 MB]&lt;br />       bluez-4.93-2 [0,49 MB]  boost-1.46.1-3 [6,56 MB]  cairomm-1.10.0-1 [0,41 MB]&lt;br />       ccrtp-1.8.0-1 [0,17 MB]  nspr-4.8.8-1 [0,22 MB]  nss-3.12.10-1 [1,37 MB]&lt;br />       chromium-12.0.742.91-1 [19,41 MB]  consolekit-0.4.5-1 [0,08 MB]  gmp-5.0.2-1 [0,41 MB]&lt;br />       coreutils-8.12-2 [2,00 MB]  module-init-tools-3.13-1 [0,34 MB]  udev-171-2 [0,20 MB]&lt;br />       device-mapper-2.02.85-2 [0,12 MB]  cryptsetup-1.3.1-1 [0,09 MB]&lt;br />       libssh2-1.2.7-2 [0,17 MB]  curl-7.21.6-2 [0,46 MB]  libgnome-keyring-3.0.3-1 [0,09 MB]&lt;br />       libsoup-gnome-2.34.2-1 [0,01 MB]  icon-naming-utils-0.8.90-2 [0,01 MB]&lt;br />       gnome-icon-theme-3.0.0-2 [8,21 MB]  libgweather-3.0.2-1 [2,15 MB]&lt;br />       evolution-data-server-3.0.2.1-1 [2,48 MB]  fam-2.7.0-15 [0,07 MB]&lt;br />       gstreamer0.10-good-0.10.29-1 [0,94 MB]  gstreamer0.10-bad-0.10.22-1 [0,83 MB]&lt;br />       farsight2-0.0.28-2 [0,21 MB]  file-5.07-3 [0,19 MB]  nspluginwrapper-1.4.2-1 [0,13 MB]&lt;br />       flashplugin-10.3.181.22-1 [6,02 MB]  gcc-multilib-4.6.0-6 [17,44 MB]&lt;br />       glew-1.6.0-1 [0,28 MB]  startup-notification-0.12-1 [0,02 MB]  libcups-1.4.6-3 [0,26 MB]&lt;br />       gtk3-3.0.11-1 [4,66 MB]  gnome-desktop-3.0.2-1 [0,48 MB]  libwnck3-3.0.2-1 [0,34 MB]&lt;br />       telepathy-glib-0.14.7-1 [1,07 MB]  gnome-panel-3.0.2-1 [1,49 MB]  gperf-3.0.4-3 [0,09 MB]&lt;br />       grep-2.8-1 [0,17 MB]  libjpeg-turbo-1.1.1-1 [0,20 MB]  v4l-utils-0.8.4-1 [0,23 MB]&lt;br />       jack-0.120.2-1 [0,28 MB]  gstreamer0.10-good-plugins-0.10.29-1 [0,31 MB]&lt;br />       gvfs-1.8.2-1 [0,80 MB]  help2man-1.39.4-1 [0,06 MB]  iproute2-2.6.38-3 [0,36 MB]&lt;br />       kbd-1.15.3-1 [0,98 MB]  initscripts-2011.06.3-1 [0,02 MB]  poppler-0.16.5-1 [0,71 MB]&lt;br />       poppler-glib-0.16.5-1 [0,17 MB]  inkscape-0.48.1-3 [12,51 MB]&lt;br />       inputproto-2.0.2-1 [0,04 MB]  jre-6u26-1 [20,85 MB]  kdesdk-okteta-4.6.3-2 [0,54 MB]&lt;br />       kdesdk-scripts-4.6.3-2 [0,17 MB]  linux-firmware-20110512-2 [9,17 MB]&lt;br />       mkinitcpio-busybox-1.18.4-1 [0,16 MB]  mkinitcpio-0.6.12-1 [0,02 MB]&lt;br />       kernel26-2.6.38.8-1 [35,93 MB]  kernel26-headers-2.6.38.8-1 [4,18 MB]&lt;br />       laptop-mode-tools-1.57-3 [0,05 MB]  less-443-2 [0,09 MB]&lt;br />       lib32-libjpeg-turbo-1.1.1-1 [0,14 MB]  libass-0.9.12-1 [0,06 MB]&lt;br />       libdvbpsi-0.2.0-1 [0,05 MB]  libftdi-0.19-1 [0,04 MB]  libgsf-1.14.21-1 [0,18 MB]&lt;br />       libgssglue-0.1-4 [0,03 MB]  libwps-0.2.2-1 [0,04 MB]  neon-0.29.6-1 [0,17 MB]&lt;br />       libtextcat-2.2-8 [0,29 MB]  libreoffice-3.4.0-2 [73,84 MB]&lt;br />       libreoffice-ru-3.4.0-1 [7,76 MB]  libssh-0.5.0-1 [0,11 MB]&lt;br />       libvncserver-0.9.8-2 [0,23 MB]  libzrtpcpp-1.4.2-5 [0,09 MB]  lvm2-2.02.85-2 [0,54 MB]&lt;br />       lzo2-2.05-1 [0,07 MB]  make-3.82-3 [0,34 MB]  man-db-2.6.0.2-2 [0,38 MB]&lt;br />       mercurial-1.8.4-1 [1,36 MB]  net-tools-1.60-16 [0,10 MB]  qt-4.7.3-2 [24,12 MB]&lt;br />       ntrack-1:13-2 [0,03 MB]  parted-2.4-1 [0,47 MB]  perl-capture-tiny-0.11-1 [0,01 MB]&lt;br />       php-5.3.6-4 [2,90 MB]  php-pear-5.3.6-4 [0,24 MB]  pixman-0.22.0-1 [0,16 MB]&lt;br />       pkg-config-0.26-1 [0,03 MB]  poppler-qt-0.16.5-1 [0,11 MB]  raptor-2.0.3-1 [0,23 MB]&lt;br />       skype-2.2.0.35-1 [21,56 MB]  sox-14.3.2-3 [0,49 MB]  strigi-0.7.5-1 [0,67 MB]&lt;br />       sudo-1.8.1.p2-1 [0,37 MB]  telepathy-farsight-0.0.18-1 [0,04 MB]&lt;br />       telepathy-qt4-0.6.1-1 [1,16 MB]  twinkle-1.4.2-10 [1,23 MB]  udisks-1.0.3-3 [0,15 MB]&lt;br />       upower-0.9.11-1 [0,09 MB]  virtualbox-4.0.8-2 [16,53 MB]  vlc-1.1.10-1 [7,07 MB]&lt;br />       vte-common-0.28.0-2 [0,00 MB]  vte-0.28.0-2 [0,33 MB]  vte3-0.28.0-2 [0,32 MB]&lt;br />       webkit-sharp-0.3-2 [0,02 MB]  wine-1.3.21-2 [25,78 MB]  xorg-iceauth-1.0.5-1 [0,01 MB]&lt;br />       xorg-server-common-1.10.2-1 [0,02 MB]  xorg-server-1.10.2-1 [1,21 MB]&lt;br />       xorg-xauth-1.0.6-1 [0,02 MB]  xorg-xlsclients-1.1.2-1 [0,01 MB]  xterm-270-1 [0,22 MB]&lt;br />       xulrunner-2.0.1-2 [18,57 MB]  xvidcore-1.3.2-1 [0,25 MB]  xz-5.0.3-1 [0,31 MB]&lt;/p>
&lt;p>Total Download Size:   343,15 MB&lt;br />Total Installed Size:   1933,56 MB&lt;/p>
&lt;p>Proceed with installation? [Y/n]</code>
                </div></p>
              </div>
            </div></div> 
            
            <p>
            </p>
            
            <div style="text-align: justify;">
              Setelah menggunakan deltup, update menjadi 343,15 MB.
            </div>
            
            <div style="text-align: justify;">
            </div>
            
            <div style="text-align: justify;">
              Itu tadi langkah-langkahnya. Perlu diperhatikan, terkadang (hanya beberapa kasus sih) delta gagal untuk rebuild paket, jadi terpaksa harus donlot dan instal manual.
            </div>
            
            <p>
              referensi:<a href="https://adf.ly/3KK8l"> archlinux wiki</a>
            </p>