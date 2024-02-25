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
2. [Soal 1](#1-jelaskan-langkah-langkah-proses-booting-)
3. [Soal 2](#2-bagaimana-cara-install-debian-di-virtual-box-)
4. [Referensi](#referensi)


## Sistem Operasi Debian 12

Sistem operasi (Inggris: operating system; disingkat OS) adalah perangkat lunak sistem yang mengatur sumber daya dari perangkat keras dan perangkat lunak, serta sebagai daemon untuk program komputer. Tanpa sistem operasi, pengguna tidak dapat menjalankan program aplikasi pada komputer mereka, kecuali program booting.
Sistem operasi mempunyai penjadwalan yang sistematis mencakup perhitungan penggunaan memori, pemrosesan data, penyimpanan data, dan sumber daya lainnya.

Contoh sistem operasi modern adalah Linux, Android, iOS, Mac OS X, dan Microsoft Windows.

Debian adalah sistem operasi komputer yang tersusun dari paket-paket perangkat lunak yang dirilis sebagai perangkat lunak bebas dan terbuka dengan lisensi mayoritas GNU General Public License dan lisensi perangkat lunak bebas lainnya. Debian GNU/Linux memuat perkakas sistem operasi GNU dan kernel Linux merupakan distribusi Linux yang populer dan berpengaruh. Debian didistribusikan dengan akses ke repositori dengan ribuan paket perangkat lunak yang siap untuk instalasi dan digunakan. 

## Soal

### 1. Jelaskan langkah-langkah proses booting!

## Proses Booting

Proses booting pada komputer, termasuk laptop, terdiri dari beberapa tahapan yang menyusun dari saat tombol power ditekan hingga sistem operasi siap untuk digunakan. Berikut adalah tahapan-tahapan proses booting :

1. <b>Power On</b>
Saat tombol power atau tombol reset dihidupkan, sumber daya listrik akan mengalir ke komputer.
Kemudian, perangkat keras akan menerima daya untuk dinyalakan.

2. <b>Power-On Self-Test (POST)</b>
Setelah dinyalakan, komputer akan melakukan Power-On Self-Test atau POST, yang merupakan serangkaian tes perangkat keras untuk memastikan bahwa semuanya berfungsi dengan baik. 
POST akan memeriksa RAM, prosesor, kartu grafis, dan perangkat keras lainnya. 
Jika ada masalah dengan perangkat keras, komputer akan memberikan pesan kesalahan yang sesuai.

3. <b>Inisialisasi Perangkat Keras</b>
Setelah POST selesai, komputer akan menginisialisasi perangkat keras seperti hard drive, keyboard, mouse, dan perangkat lainnya. 
Proses ini melibatkan tahap mengenali perangkat keras, memuat driver yang diperlukan, dan menyiapkan perangkat untuk digunakan.

4. <b>Membaca Sektor Boot</b>
Selanjutnya, komputer akan mencari sektor boot di hard drive atau perangkat penyimpanan lainnya. 
Sektor boot sendiri adalah area khusus yang berisi instruksi awal untuk memuat sistem operasi.

5. <b>Memuat Sistem Operasi</b>
Setelah sektor boot ditemukan, komputer akan memuat sistem operasi ke dalam memori utama (RAM). 
Kemudian, sistem operasi akan mengambil alih kendali dan mulai menjalankan program-program yang diperlukan untuk mengoperasikan komputer.

### 2. Bagaimana cara install Debian 12 di Virtual Box?

## Tahap Instalasi

### Langkah 1

<h3>Install Aplikasi Virtualbox</h3>
<p><b>1.</b> Buka Browser anda lalu ketik pada pencarian VirtualBox</p>
<p><b>2.</b> Klik download virtualbox</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/0.png">

<p><b>3.</b>Pilih varian platform packages yang ingin anda gunakan, lalu download</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/01.png">

<p><b>4.</b>Tunggu sampai download selesai</p>
  
  <p><b>5.</b>buka apikasi virtualbox</p>
  <img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/02.png">
  <img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/1.png">

  <p><b>6.</b>Klik next</p>
  <img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/2.png">

<p><b>7.</b>Setelah anda next maka akan uncul tampilan seperti berikut</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/3.png">

<p><b>8.</b>Klik "Yes" untuk melanjutkan proses instalasi</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/4.png">

<p><b>9.</b>Klik Install</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/5.png">

<p><b>10.</b>Tunggu sampai proses selesai</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/6.png">

<p><b>11.</b>Jika sudah opsi Start Oracle VM Virtual Box dan klik tombol Finish.</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/Virtualbox/7.png">

<p>Selsesai</p>

<h3>Instalasi Debian</h3>
<p><b>1.</b>Klik "new" untuk membuat virtual machine</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/1.png">

<p><b>2.</b>Create virtual machine dengan mengisi nama, dan iso image. tap checklist dan next</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/Screenshot%202024-02-22%20151734.png">

<p><b>3.</b>Ubah ukuran base memory menjadi 4096 dan Cpu menjadi 2</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/3.png">

<p><b>4.</b>Ubah ukuran virtual hardisk menjadi 26,50 GB</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/4.png">

<p><b>5.</b>klik finis</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/5.png">

<p><b>6.</b>Klik start</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/5.png">

<p><b>7.</b>Pilih bahasa sesuai keinginan</p>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/6.png">

<p><b>8.</b>Pilih Lokasi</p>Asia</b>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/7.png">

<p><b>9.</b>Pilih lokasi </p>Indonesia</b>
<img src="https://github.com/YafiRiifdah/Sistem-Operasi/blob/main/Image/debian/8.png">


## Referensi
[VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)

[Debian 12 Download](https://www.debian.org/download)

[Sistem Operasi](https://id.wikipedia.org/wiki/Sistem_operasi)

[Debian](https://id.wikipedia.org/wiki/Debian)
