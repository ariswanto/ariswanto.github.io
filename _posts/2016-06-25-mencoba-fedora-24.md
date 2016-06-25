---
layout: post
title: Mencoba Fedora 24 Workstation
summary: Fedora 24 Workstation, masalah kepanasan dan cara mengatasinya.
category: komputer
---
Fedora 24 baru saja [diluncurkan](https://fedoramagazine.org/fedora-24-released/) 
beberapa hari yang lalu. Versi ini selain membawa GNOME 3.20, juga membawa [Flatpak](https://flatpak.org/) 
yang digadang-gadang sebagai pengelola paket yang dapat berjalan pada semua distribusi GNU/Linux.

Berhubung kemarin sempat mendapat tugas rapat di sebuah hotel dengan wifi supercepat (untuk ukuran
Indonesia), saya iseng mengunduh [Fedora 24 Workstation](https://getfedora.org/workstation/) dan mengorbankan
satu partisi untuk mencobanya.

Saya memang kurang familiar dengan Fedora, terutama dengan Anaconda yang merupakan program pemasang yang dipakai
Fedora (juga RHEL dan kloningnya). Sempat kesulitan dalam mengatur partisi, akhirnya saya temukan cara mudahnya:
menyediakan satu partisi kosong dan membiarkan Anaconda mengatur menggunakan LVM.

Sukses memilih partisi, pemasangan Fedora pun berjalan. Nah di sini muncul masalah abadi laptop saya: KEPANASAN
dan langsung mati. Duuh.

Berbeda dengan Ubuntu, Fedora tidak membawa [thermald](https://ariswanto.github.io/komputer/2015/11/24/masalah-laptop-kepanasan-kelar-sudah/)
dalam paket bawaannya. Bahkan thermald juga tidak tersedia di repository resminya. Padahal, tanpa
thermald, laptop saya pasti _overheat_ saat melakukan kerja yang sedikit berat.

Untungnya ada repository tidak resmi yang menyediakan thermald untuk Fedora 24. Saya memakai repo milik [slaykovsky](https://copr.fedorainfracloud.org/coprs/slaykovsky/thermald/). Caranya cukup unduh berkas
[.repo-nya](https://copr.fedorainfracloud.org/coprs/slaykovsky/thermald/repo/fedora-24/slaykovsky-thermald-fedora-24.repo)
kemudian letakkan di /etc/yum.repos.d/. Pasang thermald dengan perintah `sudo dnf install thermal-daemon-(pencet tombol tab)`.

Setelah terpasang thermald, aktifkan dengan `sudo systemctl enable thermald.service` lalu `sudo systemctl start thermald.service`.
Selesai diaktifkan, pemasangan Fedora 24 berjalan lancar tanpa kepanasan.



