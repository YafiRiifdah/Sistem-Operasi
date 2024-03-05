<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 1<br>Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Kelompok 4</h3>
  <p style="text-align: center;">
    <strong>Muhammad Yafi Rifdah Zayyan (3123500001)</strong><br>
    <strong>Muhammad Daffa Erfiansyah (3123500006)</strong><br>
    <strong>Maula Shahihah Nur Sa'adah (3123500008)</strong>
  </p>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2024/2025</h3>
  <hr><hr>
</div>

## Daftar Isi

1. [Pendahuluan](#sistem-operasi-)
2. [Soal 1](#1-Perbedaan-LEGACY-dan-UEFI-)
3. [Referensi](#referensi)

## Pengertian dan Fungsi Bios
BIOS adalah singkatan dari Basic Input Output System yang merupakan program dasar pada komputer untuk mengatur proses input dan output data. Program ini juga bertanggung jawab untuk mengelola fungsi-fungsi dari perangkat keras yang terdapat pada komputer. Oleh karena itu, BIOS bisa dibilang sebagai program dasar yang terintegrasi dalam sistem komputer.

## Fungsi Bios
1. <b>Melakukan Pengujian POST (Power On Self Test)</b>
<p>BIOS berfungsi untuk memastikan tingkat kompatibilitas antara sistem operasi yang digunakan dengan spesifikasi perangkat komputer. Pengecekan ini penting dilakukan di awal sebelum melakukan instalasi sistem operasi pada komputer.</p>

2. <b>Konfigurasi Dasar Komputer</b>
<p>BIOS juga berfungsi untuk mengatur konfigurasi dasar perangkat komputer. Hal ini dilakukan dengan memberikan informasi yang diperlukan untuk menjalankan sistem dengan lancar. Pengguna komputer dapat menyesuaikan proses ini sesuai dengan kebutuhan mereka.</p>

3. <b>Memberikan Informasi Dasar tentang Komputer</b>
<p>BIOS juga berfungsi untuk memberikan informasi dasar tentang berbagai proses yang terjadi di dalam komputer. Contoh informasi yang disediakan oleh BIOS, antara lain yaitu alokasi memori yang akan digunakan untuk instalasi sistem operasi, serta detail lainnya yang berkaitan dengan interaksi perangkat keras komputer.</p>

4. <b>Memuat dan Menjalankan Sistem Operasi Komputer</b>
<p>IBM BIOS dikembangkan oleh IBM. Inc., perusahaan software dan perangkat keras ternama yang berasal dari Amerika Serikat. IBM BIOS kemudian dibagi lagi menjadi 3 versi:</p>


## Sistem Operasi LEGACY dan UEFI
Pada setiap komputer terdapat 2 perangkat penting yang berfungsi untuk menjalankan komputer yaitu perangkat hardware dan software
Tetapi masih ada satu lagi perangkat yang memiliki fungsi untuk menghubungkan antara software dan hardware. yang dikenal dengan dengan nama firmware Untuk masuk BIOS biasanya Anda diharuskan memencet tombol Esc, F2, F10 atau Delete saat proses booting.

BIOS ini berfungsi untuk menyimpan pengaturan pada komputer, jadi saat booting BIOS akan mengkonfigurasi pengaturan yang disimpan pada BIOS.

BIOS ini sebenarnya adalah teknologi lama yang sudah ada sejak dulu yang pertama kali diperkenalkan oleh IBM tahun 1975.

Jika ada yang menyebut Legacy BIOS itu sama saja dengan BIOS. Sampai sekarang BIOS/Legacy masih digunakan dan belum banyak berubah.

Tetapi beberapa tahun belakangan ini muncul penganti Legacy BIOS yang bernama UEFI.

## Soal
### 1. Perbedaan LEGACY dan UEFI

## Apa Itu UEFI
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%202/Perbedaan%20Legacy%20dan%20Uefi/Image/Contoh%20Uefi.png">
UEFI kepanjangan dari (Unifield Exstensible Firmware Interface) merupakan teknologi terbaru yang berfungsi untuk mempercanggih BIOS (Basic Input Output System). Munculnya UEFI adalah pada pertengahan tahun 1990an yang dimulai dengan munculnya standar EFI dan hanya pada komputer jenis server yang memiliki BIOS EFI yaitu keluarn Intel dan HP.

Seiring bergulirnya waktu dan berkembang pesatnya teknologi, fitur dari EFI diperbaharui agar lebih baik untuk semua platfom hardware terbaru. Maka lahirlah teknologi UEFI saat ini yang mana EFI diperbaharui menjadi UEFI, huruf "U" merupakan tanda United atau Universal yang artinya mampu digunakan di berbagai jenis platform hardware. Pada awal lahirnya UEFI ini hanya dapat ditemukan pada jenis BIOS komputer sever, namun saat ini sobat akan semakin sering menemukannya pada jenis komputer biasa. Terlebih semua jenis laptop keluaran tahun 2014 sudah dapat dipastikan memiliki fitur UEFI walaupun diikutsertakan juga fitur EFI/Legacy sebagai fitur lama yang masih bisa digunakan.

Oleh sebab itu sobat semua kelahiran UEFI sebagai pengganti EFI ini harus dipahami sebagai sebuah perkembangan teknologi yang luar biasa, pada perkembangan teknologi komputer, fitur bahasa pemograman, kecanggihan hardware, visualisasi, kapasitas dan memori dan kode bit menjadi acuan.

## Kelebihan  Uefi
1. UEFI memiliki komunikasi yang lebih baik  dengan hardware dan firmware dibandingkan dengan BIOS. Contoh saja UEFI tidak lagi memerlukan boot sector pada hardisk, bisa menggunakan mouse dan keyboard untuk interface.

2. UEFI bisa custom program sehingga produsen hardware bisa menambahkan aplikasi dan driver di dalamnya, jadi sudah tidak perlu lagi CD driver seperti yang ada pada komputer BIOS.

3. Tampilan UEFI lebih menarik dan modern dibandingkan BIOS.

4. Bisa menggunakan mouse dan keyboard untuk inputnya.

5. Security UEFI lebih kuat jika dibandingkan dengan BIOS

6. UEFI mendukung kapasitas hardisk lebih dari 2,2 TB, jadi lebih aman untuk Anda yang suka menyimpan file pada hardisk.

7. UEFI memiliki waktu startup yang lebih cepat.

8. Proses resume dari hibernate yang lebih cepat.

9. UEFI mendukung driver perangkat 64 bit.

10. Saat ini UEFI bisa menjalankan BIOS, jadi untuk hardware lama masih bisa tetap berjalan normal.

## Ciri Bios LEGACY dan UEFI
1. BIOS yang digunakan 2014 ke atas sudah dipastikan terdapat fitur UEFI
2. BIOS di bawah tahun 2014 masih menggunakan fitur EFI/Legacy
3. Tidak dapat install sistem operasi 64 bit pada komputer atau laptop, adalah tanda bahwa BIOS sudah memiliki fitur UEFI
4. Komputer atau laptop yang sudah terpasang sistem operasi windows 8.x atau windows 10 sebagai bawaannya, sudah dipastikan BIOS support dengan jenis UEFI.

## Perbedaan UEFI dan LEGACY
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%202/Perbedaan%20Legacy%20dan%20Uefi/Image/bios%20uefi.jpg">
<p>Seperti yang sudah Kami jelaskan diatas bahwa UEFI adalah versi terbaru dari Legacy BIOS yang sudah ada sejak tahun 75.

Pada dasarnya BIOS Legacy lama masih menggunakan sistem partisi MBR atau Master Boot Record. Sedangkan untuk UEFI sudah menggunakan partisi GPT atau GUID Partition Table.</p>

<h3><b>Berikut perbedaan antara UEFI dan Legacy:</b></h3>
1. Batasan partisi untuk MBR Legacy hanya mampu 2 Terabyte sedangkan untuk GPT UEFI bisa lebih besar dari 2 Terabyte keatas.
2. MBR Legacy hanya bisa membuat partisi utama 4 saja, sedangkan GPT UEFI bisa lebih sampai 128 partisi utama.
3. Pada MBR Legacy hanya mampu menyimpan 1 bootloader saja, sedangkan untuk GPT UEFI bisa lebih dari satu partisi bootloader

Untuk bisa menggunakan UEFI, Anda tidak bisa langsung update begitu saja, perlu melakukan cek apakah hardware yang Anda gunakan sudah support dengan firmware UEFI.

Jika belum Anda perlu mengupgrade hardware yang dimiliki dengan versi yang lebih baru.

Anda juga tidak perlu takut jika kebingungan menggunakan firmware UEFI yang baru karena belum terbiasa, UEFI juga menyediakan emulator BIOS sehingga Anda tetap bisa menggunakan BIOS seperti biasanya.</P>


## Referensi
[Pengertian dan Fungsi Bios](https://www.acerid.com/berita-teknologi/fungsi-bios-pada-sistem-komputasi)

[SIstem Operasi Legacy dan Uefi](https://seberkas.com/perbedaan-uefi-dan-legacy/)

[Apa itu UEFI](https://www.buatkuingat.com/2019/02/apa-bedanya-bios-legacy-dan-uefi.html)

[Kelebihan UEFI](https://qwords.com/blog/apa-itu-uefi-dan-legacy/)

[Ciri bios Legacy dan Uefi](https://www.buatkuingat.com/2019/02/apa-bedanya-bios-legacy-dan-uefi.html)

[Perbedaan UEFI dan LEGACY](https://qwords.com/blog/apa-itu-uefi-dan-legacy/)
