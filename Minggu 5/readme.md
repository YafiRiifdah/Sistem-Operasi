<div align="center">
  <h1 style="text-align: center;font-weight: bold">Pratikum Minggu 5<br>Proses dan Manajemen Proses<br>Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br/>
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

<div>
<h1 align="center">Pratikum 4 A<br>Proses dan Manajemen Proses</h1>
<h3>A. Tugas Pendahuluan</h3>
<ul>1. Apa yang dimaksud dengan proses?
<ul><li>Proses adalah program yang sedang dieksekusi.</ul> 
2. Apa yang dimaksud perintah untuk menampilkan status proses: ps, pstree.
<ul><li>ps adalah singkatan dari "process status". Perintah ini digunakan untuk menampilkan daftar proses yang sedang berjalan di sistem dan menampilkan Proses Id (PID)</ul> 
<ul><li>pstree adalah perintah yang menampilkan daftar proses dalam bentuk pohon (hierarchy).</ul> 
3. Sebutkan opsi yang dapat diberikan pada perintah ps
<ul><li>-e: Menampilkan semua proses</ul> 
<ul><li>-f: Menampilkan output dalam format yang lebih lengkap, termasuk informasi seperti UID, PID, PPID, C, STIME, TTY, TIME, dan CMD.</ul> 
<ul><li>-u user: Menampilkan proses yang dimiliki oleh pengguna tertentu.</ul> 
<ul><li>-a: Menampilkan proses dari semua pengguna, bukan hanya dari pengguna yang sedang login.</ul> 
4. Apa yang dimaksud dengan sinyal? apa perintah untuk mengirim sinyal?
<ul><li>sinyal adalah cara untuk mengirim pesan atau perintah ke proses atau thread di dalam sistem.</ul> 
<ul><li>Proses mengirim sinyal melalui instruksi “kill” dengan format
<i>kill [-nomor sinyal] PID</i>
</ul> 
5. Apa yang dimaksud dengan proses foreground dan background pada job control?
<ul><li>foreground: Proses yang diciptakan oleh pemakai langsung pada terminal (interaktif, dialog) Pada foreground hanya diperuntukkan untuk satu job pada satu waktu. Job pada foreground akan mengontrol shell - menerima input dari keyboard dan mengirim output ke layar.</ul> 
<ul><li>Background: adalah proses yang berjalan di latar belakang tanpa memerlukan interaksi langsung dengan pengguna. Job pada background tidak menerima input dari terminal, biasanya berjalan tanpa memerlukan interaksi.</ul> 
6. Apa yang dimaksud perintah-perintah penjadwalan prioritas: top, nice, renice.
<ul><li><b>top</b> adalah perintah yang digunakan untuk menampilkan daftar proses yang sedang berjalan di sistem secara real-time.</ul> 
<ul><li><b>nice</b> adalah perintah yang digunakan untuk menjalankan proses dengan prioritas yang berbeda. Prioritas ini diukur dalam "nilai nice". Semakin kecil nilai nice, semakin tinggi prioritasnya.</ul> 
<ul><li><b>renice</b> adalah perintah yang digunakan untuk mengubah prioritas (nilai nice) dari proses yang sedang berjalan dan menurunkan atau meningkatkan prioritas suatu proses</ul> 
</ul>
<h3>B. Percobaan</h3>
<ul><b>Percobaan 1: Status Proses</b>
<br>1. Instruksi ps (process status) digunakan untuk melihat kondisi proses yang ada. PID adalah Nomor Identitas Proses, TTY adalah nama terminal dimana proses tersebut aktif, STAT berisi S (Sleeping) dan R (Running), COMMAND merupakan instruksi yang digunakan.
<i>$ ps</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_01.png?raw=true)

<p><b>Analisa:</b>
melihat kondisi proses yang pada terminal saya. PID adalah Nomor Identitas Proses, TTY adalah nama terminal dimana proses tersebut aktif. Pada gambar tersebut PID 4242 untuk proses terminal/bash kemudian untuk PID 4245 untuk proses ps.
</p>
<br>2. Untuk melihat faktor/elemen lainnya, gunakan option –u (user). %CPU adalah presentasi CPU time yang digunakan oleh proses tersebut, %MEM adalah presentasi system memori yang digunakan proses, SIZE adalah jumlah memori yang digunakan, RSS (Real System Storage) adalah jumlah memori yang digunakan, START adalah kapan proses tersebut diaktifkan
<i>$ ps -u</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_02.png?raw=true)

<p>Analisa:  Instruksi ps -u (user), digunakan untuk melihat elemen/faktor lain dari kondisi proses yang ada serta menampilkan nama user

</p>
<br>3. Mencari proses yang spesifik pemakai. Proses diatas hanya terbatas pada proses milik pemakai, dimana pemakai teresbut melakukan login
<i>$ ps –u (user)</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_03.png?raw=true)

<p>Analisa:Mencari proses yang spesifik pemakai. Proses diatas hanya terbatas pada proses milik pemakai. Perintah tersebut digunakan untuk menampilkan proses pada user yang kita inginkan
</p>
<br>4.	Mencari proses lainnya gunakan opsi a (all) dan au (all user)
<br><i>$ ps –a</i>
<br><i>$ ps –au</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_04.png?raw=true)

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_05.png?raw=true)

<p>Analisa:Perintah ps -au digunakan untuk menampilkan informasi yang lebih rinci tentang semua proses yang sedang berjalan, termasuk proses yang dimiliki oleh pengguna (termasuk proses terminal yang sedang dijalankan) dan proses sistem.

</p>
<br><b>Percobaan 2: Menampilkan Hubungan Proses Parent dan Child</b>
<br>1. Ketik <b>ps –eH</b> dan tekan Enter. Opsi e memilih semua proses dan opsi H menghasilkan tampilan proses secara hierarki. Proses child muncul dibawah proses parent. Proses child ditandai dengan awalan beberapa spasi.
<br><i>$ ps -eH</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_06.png?raw=true)

<p>Analisa:Perintah tersebut digunakan untuk menampilkan seluruh proses secara hierarki. Dimana opsi e digunakan untuk memilih semua proses dan opsi H untuk menghasilkan tampilan proses secara hierarki.
</p>
<br>2. Ketik ps –e f dan tekan Enter. Tampilan serupa dengan langkah 2. Opsi
–f akan menampilkan status proses dengan karakter grafis (\ dan _)
<br><i>$ ps –e f</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_07.png?raw=true)

<p>Analisa:Menghasilkan tampilan serupa dengan langkah 2. Opsi f disini berfungsi untuk menampilkan STAT dari sebuah proses dan menampilkan status proses dengan karakter grafis ( \ dan _ )
</p>
<br>3. Ketik pstree dan tekan Enter. Akan ditampilkan semua proses pada sistem dalam bentuk hirarki parent/child. Proses parent di sebelah kiri proses child. Sebagai contoh proses init sebagai parent (ancestor) dari semua proses pada sistem. Beberapa child dari init mempunyai child. Proses login mempunya i proses bash sebagai child. Proses bash mempunyai proses child startx. Proses startx mempunyai child xinit dan seterusnya.
<br><i>$ pstree</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_08.png?raw=true)

<p>Analisa: Gambar diatas tampak seperti pohon atau diagram. Perintah tersebut berfungsi untuk menampilkan struktur proses yang berjalan di sistem secara hirarkis parent/child.
</p>
<br>4. Ketik pstree | grep mingetty dan tekan Enter. Akan menampilkan semua proses mingetty yang berjalan pada system yang berupa console virtual. Selain menampikan semua proses, proses dikelompokkan dalam satu baris dengan suatu angka sebagai jumlah proses yang berjalan.
<br><i>$ pstree | grep mingetty</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_09.png?raw=true)

<p>Analisa: Perintah ini berfungsi untuk menampilkan semua proses mingetty yang berjalan pada sistem yang berupa console virtual. Pada gambar diatas tidak ada output yang keluar dikarenakan tidak ada proses mingetty yang sedang berjalan
</p>
<br>5. Untuk melihat semua PID untuk proses gunakan opsi <b>–p</b>.
<i>$ pstree –p</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_09.png?raw=true)

<p>Analisa: Perintah pstree -p dalam sistem operasi Linux adalah varian dari perintah pstree yang menampilkan struktur proses dalam bentuk pohon, namun dengan tambahan informasi tentang ID proses (PID) untuk setiap proses yang ditampilkan.
</p>
<br>6. Untuk menampilk an proses dan ancestor yang tercetak tebal gunakan opsi
–h.
<br><i>$ pstree –h</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_10.png?raw=true)

<p>Analisa:Dalam sistem Linux, perintah pstree -h digunakan untuk menampilkan struktur proses dalam bentuk pohon dengan opsi "human-readable" yang menyederhanakan ukuran angka yang besar ke format yang lebih mudah dipahami manusia.
</p>
<br><b>Percobaan 3: Menampilkan Status Proses dengan Berbagai Format</b>
<br>1.	Ketik ps –e | more dan tekan Enter. Opsi -e menampilkan semua proses dalam bentuk 4 kolom : PID, TTY, TIME dan CMD.
<br><i>$ ps –e | more</i>
<br>Jika halaman penuh terlihat prompt --More-- di bagian bawah screen, tekan q untuk kembali ke prompt perintah.

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_11.png?raw=true)

<p>Analisa: Perintah ps -e | more berfungsi untuk menampilkan daftar semua proses yang sedang berjalan di sistem secara berurutan, dan outputnya akan ditampilkan secara bertahap menggunakan perintah more
</p>
<br>2.	Ketik ps ax | more dan tekan Enter. Opsi a akan menampilkan semua proses yang dihasilkan terminal (TTY). Opsi x menampilkan semua proses yang tidak dihasilkan terminal. Secara logika opsi ini sama dengan opsi –e . Terdapa 5 kolom : PID, TTY, STAT, TIME dan COMMAND.
<br><i>$ ps ax | more</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_12.png?raw=true)

<p>Analisa: Opsi a akan menampilkan semua proses yang dihasilkan terminal (TTY). Opsi x menampilkan semua proses yang tidak dihasilkan terminal. Yang kemudian outputnya ditampilkan secara bertahap menggunakan perintah more

</p>
<br>3. Ketik ps –e f | more dan tekan Enter. Opsi –e f akan menampilkan semua proses dalam format daftar penuh.
<br><i>$ ps ef | more</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_13.png?raw=true)

<p>Analisa: Ketika perintah ps – ef | more dieksekusi maka opsi -ef akan menampilkan semua proses dalam format daftar penuh. Yang kemudian outputnya ditampilkan secara bertahap menggunakan perintah more
</p>
<br>4. Ketik ps –eo pid, cmd | more dan tekan Enter. Opsi –eo akan menampilkan semua proses dalam format sesuai definisi user yaitu terdiri dari kolom PID dan CMD.
<br><i>$ ps –eo pid,cmd | more</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_14.png?raw=true)

<p>Analisa: Opsi –eo akan menampilkan semua proses dalam format sesuai definisi user yaitu terdiri dari kolom PID dan CMD. Yang kemudian outputnya akan ditampilkan secara bertahap menggunakan perintah more
</p>
<br>5.	Ketik ps –eo pid,ppid,%mem,cmd | more dan tekan Enter. Akan menampilkan kolom PID, PPID dan %MEM.   PPID adalah proses ID dari proses parent. %MEM menampilkan persentasi memory system yang digunakan proses. Jika proses hanya menggunakan sedikit memory system akan dita mpilkan 0.
<br><i>$ ps –eo pid,ppid,%mem,cmd | more</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_15.png?raw=true)

<p>Analisa: Perintah ps -eo pid,ppid,%mem,cmd | more akan menampilkan kolom PID, PPID dan %MEM. Dimana PPID adalah proses ID dari proses parent. %MEM menampilkan persentasi memory system yang digunakan proses. Jika proses hanya menggunakan sedikit memory system akan ditampilkan 0.
</p>
<br><b>Percobaan 4: Mengontrol proses pada shell</b>
<br>1. Gunakan perintah yes yang mengirim output y yang tidak pernah berhenti
<br><i>$ yes</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_16.png?raw=true)

<p>Analisa:Perintah yes akan memberikan output huruf y yang tidak pernah berhenti. Untuk menghentikannya harus menggunakan Ctrl + C

</p>
<br>2. Belokkan standart output ke /dev/null
<br><i>$ yes > /dev/null</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_17.png?raw=true)

<p>Analisa: Membelokkan standard output dari perintah yes ke /dev/null. Untuk menghentikannya harus menggunakan Ctrl + C.
</p>
<br>3. Salah satu cara agar perintah yes tetap dijalankan tetapi shell tetap digunakan untuk hal yang lain dengan meletakkan proses pada background dengan menambahkan karakter & pada akhir perintah.
<br><i>$ yes > /dev/null &</i>
<br>Angka dalam ”[ ]” merupakan job number diikuti PID.
<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_18.png?raw=true)

<p>Analisa: Salah satu cara agar perintah yes tetap dijalankan tetapi shell tetap digunakan untuk hal yang lain dengan meletakkan proses pada background dengan menambahkan karakter '&' pada akhir perintah. [1] merupakan job number PID.

</p>
<br>4. Untuk melihat status proses gunakan perintah jobs.
<br><i>$ jobs</i>


<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_19.png?raw=true)

<p>Analisa: Perintah di atas digunakan untuk melihat status proses yang telah digunakan.
</p>
<br>5. Untuk menghentikan job, gunakan perintah kill diikuti job number atau PID proses.   Untuk identifikasi job number, diikuti prefix dengan karakter ”%”.
<br><i>$ kill %(nomor job) contoh : kill %1</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_20.png?raw=true)

<p>Analisa: Perintah kill digunakan untuk menghentikan job diikuti oleh job number atau PID Proses. Untuk identifikasi job number, penulisan perintah diikuti prefix dengan karakter %. Perintah jobs untuk melihat status job setelah diterminasi.

</p>
<br>6. Lihat status job setelah diterminasi
<br><i>$ jobs</i>

<br>

![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%205/Assets/IMG_21.png?raw=true)

<p>Analisa: Perintah di atas digunakan untuk melihat status proses yang telah digunakan.
</p>

</div>