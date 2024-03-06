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

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
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

Proses booting pada komputer, termasuk laptop, terdiri dari beberapa tahapan yang menyusun dari saat tombol power ditekan hingga sistem operasi siap untuk digunakan. Berikut adalah tahapan-tahapan proses booting :

1. <b>Power ON</b>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%201/Image/Power%20on.jpg">
Saat tombol power atau tombol reset dihidupkan, sumber daya listrik akan mengalir ke komputer.
Kemudian, perangkat keras akan menerima daya untuk dinyalakan.

2. <b>Power-On Self-Test (POST)</b>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%201/Image/3.jpeg">
Setelah dinyalakan, komputer akan melakukan Power-On Self-Test atau POST, yang merupakan serangkaian tes perangkat keras untuk memastikan bahwa semuanya berfungsi dengan baik. 
POST akan memeriksa RAM, prosesor, kartu grafis, dan perangkat keras lainnya. 
Jika ada masalah dengan perangkat keras, komputer akan memberikan pesan kesalahan yang sesuai.

3. <b>Inisialisasi Perangkat Keras</b>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%201/Image/1.jpeg">
Setelah POST selesai, komputer akan menginisialisasi perangkat keras seperti hard drive, keyboard, mouse, dan perangkat lainnya. 

4. <b>Membaca Sektor Boot</b>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%201/Image/2.jpeg">
Selanjutnya, komputer akan mencari sektor boot di hard drive atau perangkat penyimpanan lainnya. 
Sektor boot sendiri adalah area khusus yang berisi instruksi awal untuk memuat sistem operasi.

5. <b>Memuat Sistem Operasi</b>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Minggu%201/Image/4.jpeg">
Setelah sektor boot ditemukan, komputer akan memuat sistem operasi ke dalam memori utama (RAM). 
Kemudian, sistem operasi akan mengambil alih kendali dan mulai menjalankan program-program yang diperlukan untuk mengoperasikan komputer.

### 2. Bagaimana cara install Debian 12 di VirtualBox?

## Installation

### Langkah 1

Download dan Install Software Virtualbox

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/1.png?raw=true)

Download VirtualBox sesuai dengan Sistem Operasi dan spesifikasi yang digunakan

### Langkah 2

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/2.png?raw=true)


Buka VirtualBox, kemudian klik "Next"

### Langkah 3

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/3.png?raw=true)

Lanjut klik "Next"

### Langkah 4

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/4.png?raw=true)

Klik "Yes" untuk melanjutkan install software VirtualBox

### Langkah 5

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/5.png?raw=true)

Klik "Install"

### Langkah 6

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/6.png?raw=true)

Tunggu hingga proses instalasi selesai

### Langkah 7

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/7.png?raw=true)

Klik "Finish" 

### Langkah 8

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/8.png?raw=true)

Ini adalah tampilan awal pada software VirtualBox yang sudah terinstall kemudian klik "New"

### Langkah 9

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/9.png?raw=true)

Masukkan nama dan file .iso debian 12 yang sudah di download lalu klik "Next"

### Langkah 10

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/10.png?raw=true)

Isikan Base Memory sebesar 4096 MB dan prosesor CPU sebesar 2 Core

### Langkah 11

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/11.png?raw=true)


Isikan ukuran Disk Size pada 26.50 GB 

### Langkah 12

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/12.png?raw=true)

Klik tombol "Finish" jika merasa sudah benar

### Langkah 13

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/13.png?raw=true)

Klik "Start" pada virtual machine yang dibuat

### Langkah 14

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/graphical%20install.png?raw=true)

Pilih "Graphic Install" kemudian enter

### Langkah 15

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/14.png?raw=true)

Pilih bahasa yang ingin digunakan, kemudian klik "Continue"

### Langkah 16

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/15.png?raw=true)

Pilih lokasi yang ingin digunakan, kemudian klik "Continue"

### Langkah 17

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/16.png?raw=true)

Masukkan Hostname, kemudian klik "Continue"

### Langkah 18

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/17.png?raw=true)

Kosongi domain, kemudian klik "Continue"

### Langkah 19

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/18.png?raw=true)

Masukkan password pertama untuk root user, kemudian klik "Continue"

### Langkah 20

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/19.png?raw=true)

Masukkan full name untuk pengguna baru, kemudian klik "Continue"

### Langkah 21

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/20.png?raw=true)

Masukkan username untuk akun anda, kemudian klik "Continue"

### Langkah 22

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/21.png?raw=true)

Masukkan password kedua untuk root user, kemudian klik "Continue"

### Langkah 23

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/22.png?raw=true)

Pilih waktu sesuai lokasi yang dipilih tadi, kemudian klik "Continue"

### Langkah 24

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/23.png?raw=true)

Pilih Manual, kemudian klik "Continue"

### Langkah 25

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/24.png?raw=true)

Pilih "SCSI3 (0,0,0) (sda) - 28.5 GB AT VBOX HARDDISK", kemudian klik "Continue"

### Langkah 26

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/25.png?raw=true)

Klik "Yes", kemudian klik "Continue"

### Langkah 27

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/26.png?raw=true)

Pilih "pri/log 28.5 GB FREE SPACE", kemudian klik "Continue"

### Langkah 28

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/27.png?raw=true)

Klik "Create a new partition" 

### Langkah 29

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/28.png?raw=true)

Masukkan size untuk partisi pertama sebesar 20GB

### Langkah 30

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/29.png?raw=true)

Pilih "Primary"

### Langkah 31

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/30.png?raw=true)

Pilih "Beginning" dan Continue

### Langkah 32

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/31.png?raw=true)

Klik "Done setting up the partition", kemudian klik "Continue" untuk kembali ke menu partisi selanjutnya

### Langkah 33

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/32.png?raw=true)

Kemudian klik "pri/log 8.5 GB FREE SPACE" untuk membuat partisi kedua lalu klik "Continue"

### Langkah 34

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/33.png?raw=true)

Masukkan size untuk /storage sebesar 5GB

### Langkah 35

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/34.png?raw=true)

Pilih "Primary" sama seperti partisi pertama

### Langkah 36

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/35.png?raw=true)

Pilih "Beginning" sama seperti partisi pertama

### Langkah 37

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/36.png?raw=true)

Pada Mount point pilih Enter manually dan isikan /storage, kemudian klik "Continue"

### Langkah 38

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/37.png?raw=true)

Pilih "pri/log 3.5 GB FREE SPACE" untuk membuat partisi ketiga

### Langkah 39

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/38.png?raw=true)

Masukkan size untuk swap area sebesar 1,5GB

### Langkah 40

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/39.png?raw=true)

Pilih opsi swap area

### Langkah 41

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/40.png?raw=true)

Klik "Done setting up the partition"

### Langkah 42

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/41.png?raw=true)

Klik "Finish"

### Langkah 43

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/42.png?raw=true)

Tunggu proses install hingga selesai

### Langkah 44

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/43.png?raw=true)

Pilih "No" dan klik "Continue"

### Langkah 45

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/44.png?raw=true)

Pilih lokasi "Indonesia" untuk konfigurasi package

### Langkah 46

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/45.png?raw=true)

Pilih "kebo.pens.ac.id"

### Langkah 47

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/46.png?raw=true)

Kosongi HTTP proxy dan klik "Continue"

### Langkah 48

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/47.png?raw=true)

Tunggu hingga proses selesai 

### Langkah 49

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/48.png?raw=true)

Pilih "Yes" dan klik "Continue"

### Langkah 50

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/49.png?raw=true)

Klik "Continue"

### Langkah 51

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/50.png?raw=true)

Tunggu hingga proses selesai 

### Langkah 52

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/51.png?raw=true)

Pilih /dev/sda dan klik "Continue"

### Langkah 53

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/52.png?raw=true)

Tunggu proses akhir instalasi hingga selesai

### Langkah 54

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/53.png?raw=true)

Pada tampilan ini Debian siap digunakan, kemudian klik "Continue"

### Langkah 55

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/54.png?raw=true)

Jika sudah, maka tampilan berubah seperti gambar diatas

### Langkah 56

![App Screenshot](https://github.com/maulaasn/SysOp-3123500008/blob/main/Week-1/img/55.png?raw=true)

Debian GNU/Linux is ready to be used

## Referensi

- [VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)
- [Debian 12 Download](https://www.debian.org/download)
- [Sistem Operasi](https://id.wikipedia.org/wiki/Sistem_operasi)
- [Debian](https://id.wikipedia.org/wiki/Debian)
- [Proses Booting](https://asani.co.id/blog/booting-adalah/)
