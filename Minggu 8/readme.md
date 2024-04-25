<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 8<br>Praktek Sistem Operasi</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Muhammad Yafi Rifdah Zayyan (3123500001) </strong><br>
    <strong>Muhammad Daffa Erfiansyah (3123500006) </strong><br>
    <strong>Maula Shahihah Nur Sa'adah (3123500008)</strong>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
  <hr><hr>
</div>

## Bash Programming

### Apa itu bash?

Bash, kependekan dari Bourne Again Shell, adalah open source command line interpreter dan scripting language. Ini menafsirkan perintah yang dimasukkan pengguna, baik secara interaktif atau dari file skrip.

Ini berfungsi sebagai interface untuk memanggil perintah, memungkinkan system function calls.

### Terdapat 2 tipe dari mode bash

- **Interactive Mode**
  <b>Juga disebut sebagai command intepreter</b>, memungkinkan eksekusi perintah di terminal. Ini mengeksekusi perintah secara berurutan jika ada beberapa perintah.

- **Non-interactive Mode**
  <b>Ini merujuk pada scrpts</b>, memungkinkan Anda menulis Bash syntax yang berisi rangkaian beberapa perintah untuk eksekusi skrip.

## Apa Perbedaan dari Bash dan Shell

Shell, alias Bourne Shell, adalah penerjemah baris perintah untuk OS Unix dan Linux. Bash, alias Bourne Again Shell, adalah versi yang disempurnakan.

### Untuk apa skrip bash digunakan?

Skrip Bash memiliki banyak kasus penggunaan, termasuk:

- Menulis skrip untuk mengotomatiskan tugas pemrograman
- Menyinkronkan tugas untuk menyalin file
- Menjalankan tugas cron untuk penjadwalan

### Bagaimana cara menulis kode di bash?

Untuk menulis kode dalam skrip Bash, ikuti langkah-langkah berikut:

- Di terminal, buat file menggunakan <code>vi test.sh.</code>
- Tambahkan <code>#!/bin/bash</code> di bagian atas file.
- Tambahkan beberapa cuplikan kode shell.
- Simpan file shell dengan <code>sh</code>. ekstensi.
- Jalankan skrip shell menggunakan <code>/test.sh</code> perintah di terminal.

### Apakah bash termasuk bahasa pengkodean?

Bash menjalankan perintah dari terminal atau file. Ini adalah bahasa pemrograman yang beroperasi pada sistem operasi kernel Unix/Linux, berisi semua fitur untuk menulis kode lengkap.

Bash adalah tipe shell khusus yang menerima masukan dari perintah, menjalankan kode, dan memproses masukan, serta mengembalikan hasilnya.

### Jenis Shell

Ada berbagai jenis shell di OS Unix.

<style>
  table {
    border-collapse: collapse;
    width: 100%;
    margin-bottom: 20px;
  }

  th, td {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
  }

  th {
    background-color: #3498db;
    color: white;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;
  }
</style>

<table>
  <thead>
    <tr>
      <th>Tipe Cangkang</th>
      <th>Alias</th>
      <th>Garis Pertama</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SH</td>
      <td>Bourne Shell</td>
      <td>#!/bin/sh</td>
    </tr>
    <tr>
      <td>bash</td>
      <td>Bourne Again Shell</td>
      <td>#!/bin/bash</td>
    </tr>
    <tr>
      <td>cshell</td>
      <td>C shel</td>
      <td>#!/bin/csh</td>
    </tr>
  </tbody>
</table>

| tcsh | TENEX C shell | #!/bin/tcsh | | | | ksh | Korn shell | #!/bin/ksh |

### Perbedaan dari Command Line dan Script di bash

Mari kita lihat perbedaan antara baris perintah dan skrip

Opsi baris perintah

- Baris perintah memiliki prompt yang menerima masukan dari pengguna
- Perintah tidak disimpan ke file.
- Ini hanya mendukung satu perintah pada satu waktu.

File skrip

- Mendukung banyak perintah dalam satu file
- Prompt masih dapat ditulis dalam file skrip
- Hanya satu baris dalam sebuah file yang dijalankan secara berurutan

## Bash - Variables

**Deklarasi Variable**: Untuk membuat variable, maka harus memberikan nilai padanya

```
variableName=VariableValue
```

Keterangan:

- variableName: dapat berisi kombinasi huruf apa saja, angka, dan garis bawah
- variableValue: adalah nilai yang disimpan dalam variabel, dan dapat berupa angka, string atau boolean. Simbol `=` digunakan untuk memberikan nilai pada suatu variabel.

Misalnya

```
AGE=25
```

### Cara mengakses variabel di bash

Setelah mendeklarasikan dan memberikan nilai pada variabel, Anda dapat mengaksesnya menggunakan simbol dolar ( $) diikuti dengan nama variabel.

<pre>AGE=25
echo $AGE</pre>

Pertama, deklarasikan variabel `AGE` dan beri nilai 25. Kemudian, gunakan `echo` untuk menampilkan outputnya. Simbol dolar `$` sebelum nama variabel sangat penting untuk mengakses nilainya.

Kode di atas mendeklarasikan variabel yang diberi nama `AGE` dengan nilai `25` dan kemudian digunakan `echo` untuk menampilkan nilai variabel `AGE`. Simbol `dollar` sebelum nama variabel sangat penting untuk mengakses nilainya.

### Variabel Hanya Membaca Bash Shell

Setelah variabel diberi nilai, kita dapat mengubahnya menjadi nilai baru menggunakan operator penugasan =.

<pre>AGE=25
echo $AGE
AGE=35
echo $AGE
</pre>

<b>Output:</b>

<pre>25
35
</pre>

Kata readonlykunci mencegah variabel diperbarui, secara efektif mengubahnya menjadi `constant`

<pre>
AGE=25
echo $AGE
readonly AGE
AGE=35
echo $AGE
</pre>

`AGE` adalah sebuah batasan, menetapkan nilai baru akan menimbulkan kesalahan, dan pesan kesalahannya adalah AGE: is `read-only.`

<b>Output:</b>

<pre>25
 line 6: AGE: is read-only</pre>

### Variabel Bash Tidak Disetel (Unset)

Kata `unset` membantu menghilangkan nilai dari variabel yang ditentukan. Variabel tetap dapat diakses tetapi mencetak nilai kosong.

<pre>AGE=25
echo $AGE
unset AGE
echo "empty":$AGE</pre>

<b>Output:</b>

<pre>25
empty:</pre>

Kode di atas,

- pertama-tama setel variabel AGE ke 25, cetak nilainya,
- lalu batalkan pengaturannya menggunakan unsetAGE.
- Selanjutnya, ia mencetak “kosong” diikuti dengan nilai AGE, yang sekarang muncul sebagai ruang kosong.

### Lingkup Variabel (Scope)

Setiap variabel yang dideklarasikan harus memiliki cakupan, yang menentukan di mana variabel tersebut dapat digunakan dalam program.

Misalnya, jika suatu variabel dideklarasikan di dalam suatu fungsi, maka variabel tersebut hanya tersedia di dalam fungsi tersebut dan tidak dapat diakses di luar fungsi tersebut.

Cakupan variabel di Bash dapat didefinisikan dengan dua cara

- Variabel global:
- Variabel lokal:

#### Variabel Global Bash

Variabel yang dideklarasikan dalam skrip shell disebut sebagai variabel global

Variabel global dapat diakses dalam suatu fungsi atau blok bersarang apa pun dari file skrip shell

<pre>setAge() {
    echo "Inside Function Age: $AGE"
}
AGE=40
setAge
echo "Script Age: $tmp"</pre>

<b>Output:</b>

<pre>Inside Function Age: 40
Script Age: 40</pre>

#### Variabel Lokal Bash

Variabel lokal dideklarasikan di dalam blok kode atau fungsi. Cakupan variabel-variabel ini hanya terlihat di dalam blok tempat variabel-variabel tersebut dideklarasikan.

- Syntax
  <pre>local variablename=variablevalue</pre>
  Dalam sintaks ini, variabel dideklarasikan dan ditetapkan dengan kata kunci`Lokal`

<pre>setAge() {
    local AGE=25
    echo "Local Variable Age: $AGE"
}
AGE=40
setAge
echo "Global Age: $tmp"</pre>

<b>Output:</b>

<pre>Local Variable Age: 25
Global Age: 40</pre>

Variabel lokal dideklarasikan di dalam suatu fungsi dan hanya terlihat di dalam fungsi tersebut. Variabel yang dideklarasikan di luar fungsi disebut variabel global dan tersedia untuk semua fungsi.

### Pengetikan Variabel

Skrip Bash bukan bahasa yang diketik, namun Anda dapat mendeklarasikan variabel dengan tipe data menggunakan perintah mendeklarasikan Berdasarkan tipe variabel, ini memungkinkan tipe data.

<pre>declare options variablename=value</pre>

- Variabel dideklarasikan dan diberi nilai.

- Opsi berisi opsi untuk membuat tipe variabel

- Array: Untuk membuat variabel array

<style>
  table {
    border-collapse: collapse;
    width: 100%;
  }

  th, td {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
  }

  th {
    background-color: #3498db;
    color: white;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;
  }
</style>

<table>
  <thead>
    <tr>
      <th>Tipe Variabel</th>
      <th>Sintaksis</th>
      <th>Keterangan</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Himpunan</td>
      <td>mendeklarasikan sebuah variabel</td>
      <td>mendeklarasikan variabel indexed array yang menyimpan string</td>
    </tr>
    <tr>
      <td>Array Terkait</td>
      <td>mendeklarasikan -A variabel</td>
      <td>Array Terkait</td>
    </tr>
    <tr>
      <td>Bilangan bulat</td>
      <td>mendeklarasikan variabel -i</td>
      <td>nilai numerik untuk disimpan dalam variabel</td>
    </tr>
    <tr>
      <td>Hanya dapat dibaca</td>
      <td>mendeklarasikan variabel -r</td>
      <td>variabel readonly, tidak dapat diubah atau tidak disetel</td>
    </tr>
    <tr>
      <td>Ekspor</td>
      <td>mendeklarasikan variabel -x</td>
      <td>ekspor variabel dan digunakan oleh semua proses anak</td>
    </tr>
  </tbody>
</table>

### Menampilkan Environtment Variabel Di Bash

Di Bash, ada dua jenis perintah untuk mencetak Environtmen Variabel.

- Perintah`printenv`​
- Perintah`env`

Kedua perintah ini mencantumkan semua Environtmen variabel terminal.​

### Konvensi Penamaan Variabel

- Variabel dibaca dengan mengawali simbol `$`.

- Nama variabel terdiri dari huruf, angka, atau garis bawah.
- Variabel peka huruf besar-kecil; misalnya, test dan Test dianggap sebagai dua variabel berbeda dalam skrip.
- Meskipun nama variabel biasanya ditulis dalam HURUF BESAR, Anda dapat membuatnya menggunakan UPPER atau LOWER diperlukan. Dan Environtmen variabel dan Shell keduanya dalam huruf besar.

- Nama variabel tidak boleh mengandung spasi
  Nama-nama biasanya harus camelCase. Contoh`firstName`

### Variabel Shell

Variabel shell adalah variabel yang diatur oleh shell, bukan oleh pengguna. Ini diperlukan oleh shell agar dapat bekerja dengan lancar

<style>
  table {
    border-collapse: collapse;
    width: 100%;
  }

  th, td {
    border: 1px solid #dddddd;
    text-align: left;
    padding: 8px;
  }

  th {
    background-color: #3498db;
    color: white;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;
  }
</style>

<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>PWD</td>
      <td>Current working directory</td>
    </tr>
    <tr>
      <td>Set-Location</td>
      <td>Change the working directory to new directory</td>
    </tr>
    <tr>
      <td>Rename-Item</td>
      <td>Rename a file</td>
    </tr>
    <tr>
      <td>IFS</td>
      <td>Internal Field Separator by default is space, set by Shell, Used for string split</td>
    </tr>
    <tr>
      <td>PATH</td>
      <td>Contains semicolon separated path of commands, Configured to lookup for commands</td>
    </tr>
    <tr>
      <td>UID</td>
      <td>Prints the User Identification number</td>
    </tr>
    <tr>
      <td>Home</td>
      <td>Home directory of a current user</td>
    </tr>
  </tbody>
</table>

## Bash Loop FIle

### Bagaimana Cara Membaca File Demi Baris Di Bash Shell

- Menggunakan While Loop

<pre>#!/bin/bash
while IFS= read -r line; do
   echo "$line"
done <filename.txt></filename.txt> </pre>

## Bash Comment

`Comment`sadalah pernyataan kode yang berisi teks yang dapat dibaca pengguna yang dilewati shell selama eksekusi. Setiap bahasa pemrograman menyertakan fitur comment, yang memberikan deskripsi baris kode atau pernyataan.
mendeklarasikan -sebuah variabel=
Terkadang kita ingin membaca konten file menggunakan bash programming.
Ada berbagai macam cara yang dapat kita lakukan

`Comment` sebaris dalam kode membantu pengembang dalam mengedit dan memahami kode dengan lebih baik.

### Comment satu baris Pada bash shell

Comment satu baris dalam skrip shell dilambangkan dengan `#`simbol di awal setiap baris.

Comment ini mencakup string yang memberikan informasi tentang baris kode terkait dalam skrip shell.

Penting untuk menempatkan comment satu baris pada baris terpisah untuk kejelasan.

Untuk Comment sebaris, gunakan simbol `#` di awal comment. comment satu baris selalu dimulai dengan `#`simbol.

<b>Syntax</b>

<pre># Single-line comments</pre>

Spasi kosong setelah `#` simbol tidak diperlukan. Berikut ini adalah contoh Comment satu baris dalam skrip shell

<pre># Single-line comments.
AGE=45
echo "Age:$AGE" ## printing age inline comment</pre>

### Comment multi-Baris dalam skrip shell

Comment multi-baris melibatkan penggunaan lebih dari satu baris untuk Comment.

Cara pertama untuk membuat comment multi-baris adalah dengan memanfaatkan komentar satu baris yang setiap barisnya dimulai dengan simbol comment satu baris.

<b>Syntax</b>

<pre># Line1 comments
# Line1 comments
# Line1 comments</pre>

Cara kedua untuk membuat comment multi-baris adalah dengan mengapit beberapa baris di dalam (` :`) dan (` '`).

Sintaks ini melibatkan:

- Comment dimulai dengan titik dua (:) diikuti dengan `'`.
- Ini diikuti oleh beberapa baris commentx.
- Comment diakhiri dengan `'`. Berikut sintaksnya:

<pre>: '
multiline comments example1
multiline comments example2
multiline comments example3
'</pre>

<b>Contoh comment Multi-Baris</b>

<pre>: '
multiline comments example1
multiline comments example2
multiline comments example3
'
echo "testing multi-line comments"</pre>

Hal ini berguna untuk memasukkan lebih banyak teks yang mencakup beberapa baris, juga melayani tujuan dokumentasi.

### Kesimpulan

Singkatnya, kita telah mempelajari cara menambahkan Comment tunggal dan multi-baris dalam pemrograman skrip shell.

## Bash Array

Array di shell adalah variabel yang menyimpan lebih dari satu nilai.

Misalkan, Anda memiliki daftar nomor 1 2 3.. 10 dan ingin menyimpan nomor-nomor ini di Shell Script

Tanpa array, Anda harus mendeklarasikan sebagai berikut:

<pre>let number1=1
let number1=1
...
...
let number10=10</pre>

Iterasinya sulit dan jika kita ingin menyimpan 100 angka, itu sangat sulit.

Jadi, Anda bisa menggunakan array yang merujuk ke satu variabel dan menyimpannya

### Bagaimana cara mendeklarasikan dan membuat array?

Ada dua jenis array yang bisa kita buat

- array yang diindeks: elemen array disimpan dengan indeks mulai dari nol

- array terkait: array disimpan dengan pasangan nilai kunci

<b>Deklarasi Sebuah Array</b>
Untuk membuat array, kita perlu mendeklarasikan sebuah array.

<pre>declares -a array; # indexed array
declare -A array; # associative array</pre>

sebuah array dideklarasikan dengan kata kunci `declare`dengan opsi `-a` atau `A`

<b>Contoh Array Yang Diindeks</b> Dalam hal ini, nilai Array disimpan dengan indeks=0 dan seterusnya. ini dibuat dengan `declare`dan `-a` opsi

<pre>declare -a array
array=(one two three)</pre>

Array ini adalah penyimpanan dengan indeks=0, ditambah 1 sebagai berikut.

<pre>array[0]=one
array[1]=two
array[2]=three</pre>

<b>contoh array asosiatif </b> Dalam hal ini, nilai Array disimpan dengan kunci. ini dibuat dengan `declare` dan `-A` opsi

<pre> declare -A array
array=(one two three)</pre>

Mari kita tetapkan nilainya

<pre>array=(1,2,3,4)</pre>

- <b>Tetapkan nilai tanpa mendeklarasikan array</b>

<pre>arrayvariable[index]=value</pre>

Array diindeks nol berdasarkan nol pada panjang array -1 indeks=0 - mengembalikan elemen pertama indeks=-1 mengembalikan elemen terakhir

Array bisa berisi angka, string, dan campurannya.

### Akses Nilai Array

Array berisi indeks untuk mendapatkan elemen. Elemen array dapat diakses menggunakan sintaks di bawah ini.

<pre>${array_name[index]}</pre>

### Deklarasikan Array angka dan ulangi

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

<pre>nums=(1 3 12)
for i in "${nums[@]}"
do
  echo "$i"
done</pre>

<b>Output:</b>

<pre>1
3
12</pre>

### Deklarasikan Array string dan ulangi

Array dapat berisi angka Contoh ini berisi array angka dan loop for untuk dicetak

<pre>numbers=("element1" "element2" "element3")
for i in "${numbers[@]}"
do
  echo "$i"
done</pre>

<b>Output:</b>

<pre>element1
element2
element3</pre>

### Akses elemen pertama array

Dalam elemen Array, indeks elemen Pertama adalah nol, dan array[0] mengembalikan elemen pertama

<pre>numbers=("element1" "element2" "element3")

echo ${numbers[0]}
echo ${numbers}</pre>

<b>Output:</b>

<pre>element1
element1</pre>

### Dapatkan elemen terakhir dari sebuah array

Dalam skrip bash, Anda dapat menggunakan indeks=-1 untuk mendapatkan elemen array terakhir

<pre>numbers=("element1" "element2" "element3")
echo ${numbers[-1]}</pre>

Dengan versi bash 4.0 terbaru, Anda dapat menggunakan sintaks di bawah ini untuk membaca elemen terakhir.

<pre>echo ${numbers[${#numbers[@]}-1]}</pre>

### Iterate atau Loop element array

For loop digunakan untuk mengulangi elemen.

Berikut adalah contoh contoh loop array untuk mencetak semua elemen

<pre>numbers=("element1" "element2" "element3")

for i in "${numbers[@]}"
do
  echo "$i"
done</pre>

<b>Output:</b>

<pre>element1
element2
element3</pre>

Cara lain untuk mencetak indeks dan elemen array menggunakan for loop.

<pre>numbers=("element1" "element2" "element3")

for i in "${!numbers[@]}"
do
  echo "$i" "${numbers[$i]}"
done</pre>

<b>Output:</b>

<pre>0 element1
1 element2
2 element3</pre>

### Cetak semua elemen array

Gunakan `[@]` atau `[*]` untuk mencetak semua elemen array.

<pre>arr=("element1" "element2" "element3") //
echo ${arr[@]} #element1 element2 element3
echo ${arr[*]}  #element1 element2 element3</pre>

### Hapus element dari array

Anda dapat menghapus elemen dari array menggunakan `unset`indeks tertentu.

<pre>numbers=("element1" "element2" "element3")
echo ${numbers[*]}
unset numbers[-1]
echo ${numbers[*]}</pre>

### Menambahkan elemen ke array

Anda dapat menambahkan elemen di posisi indeks mana pun menggunakan sintaksis di bawah ini.

<pre>array[index]=value</pre>

<b>Contoh penambahan elemen awal dan akhir serta tengah</b>

<pre>numbers=("element1" "element2" "element3")
echo ${numbers[*]}

 numbers[0]="element0"
echo ${numbers[*]}
 numbers[5]="element5"
echo ${numbers[*]}
 numbers[6]="element6"
echo ${numbers[*]}</pre>

<b>Output:</b>

<pre>element1 element2 element3
element0 element2 element3
element0 element2 element3 element5
element0 element2 element3 element5 element6</pre>

### Panjang sebuah array

Dalam hal ini, Temukan jumlah semua elemen dalam array.

Skrip shell menyediakan #

<pre>arr=("element1" "element2" "element3")
echo ${#arr[@]} # returns 3
echo ${#arr[*]} # returns 3</pre>

### Contoh lembar contekan array

| Contoh                        | Keterangan                                           |
| ----------------------------- | ---------------------------------------------------- |
| mendeklarasikan -sebuah array | Deklarasikan array yang diindeks                     |
| mendeklarasikan -A array      | Deklarasikan array Asosiatif                         |
| nyatakan -a array=()          | Deklarasikan array yang diindeks dengan array kosong |
| susunan=()                    | Buat array kosong dengan menyatakan valid            |
| susunan=(1 6 3)               | Inisialisasi array dengan angka                      |
| larik=(satu dua tiga)         | Inisialisasi array dengan string                     |
| larik=(satu dua 1)            | Inisialisasi array dengan data campuran              |
| ${array[0]}                   | Dapatkan elemen pertama                              |
| ${array[1]}                   | Dapatkan elemen Kedua                                |
| ${array[-1]}                  | Dapatkan elemen Terakhir                             |
| ${array[@]}                   | Dapatkan Semua elemen                                |
| ${array[*]}                   | Dapatkan Semua elemen                                |
| ${!susunan[@]}                | Dapatkan Semua indeks                                |
| ${#array[@]}                  | Panjang array                                        |
| susunan[0]=12                 | Tambahkan elemen ke array di posisi pertama          |
| susunan[-1]=22                | Tambahkan elemen ke array di posisi terakhir         |
| susunan+=(11)                 | Tambahkan nilai ke array                             |
| ${array[@]:k:i}               | Dapatkan elemen indeks=1 dimulai dari indeks=k       |

## Bash Expansi

perintah dimasukkan ke OS untuk membuat panggilan sistem dan melakukan tindakan. perintah masukan pengguna di terminal untuk melakukan operasi seperti ls, cd, mkdir dll.

Cara lain, Beberapa perintah dapat ditempatkan dalam satu file, juru bahasa bash membaca perintah dan menjalankannya

Cara menulis skrip shell di bash:

- Pilih Editor atau editor teks
- Buat file dengan ekstensi .sh atau .bash
- Tulis perintah dalam file
- Simpan file sebagai `hello.sh`

<pre>#!/bin/bash
echo "Hello World"</pre>

Ubah izin untuk mengeksekusi file

<pre>
chmod +x hello.sh</pre>

## Bash Ekspresi Kondisional (Conditional Expresion)

Ekspresi kondisional dievaluasi pada waktu eksekusi skrip, berdasarkan hasil, Ia mengeksekusi blok perintah tertentu.

Ada berbagai jenis ekspresi konisional di Bash

- Operator Perbandingan String
- Operator Perbandingan Numerik
- Operator File
- Operator Logis

### Operator File

Bash menyediakan operator logika pada FIle dan direktori untuk menguji ekspresi kondisional. Ini memungkinkan Anda untuk memeriksa berbagai operasi seperti keberadaan, dan izin, ukuran. Ini digunakan ekspresi kondisional dalam pernyataan kondisional seperti if else dan case.

<b>syntak</b>

<pre>if [[ conditiona_expressions]]; then
# code to handle
fi</pre>

`conditiona_expressions` berisi opsi, dan jalur file, yang selalu mengembalikan nilai benar atau salah.

berikut adalah opsi yang disediakan

- `-e file` Mengembalikan nilai benar jika file yang diberikan ada, file dapat berupa file atau direktori normal
- `-f file` Mengembalikan nilai benar jika file yang diberikan ada dan file (bukan direktori)
- `-d file` Mengembalikan nilai benar jika file adalah direktori
- `-r file` Mengembalikan nilai benar jika file ada dan memiliki izin yang dapat dibaca
- `-w file` Mengembalikan nilai benar jika file ada dan memiliki izin yang dapat ditulis
- `-x file` Mengembalikan nilai benar jika file ada dan memiliki izin yang dapat dieksekusi
- `-s file` Mengembalikan nilai benar jika file ada dan ukurannya tidak kosong
- `-G file` Mengembalikan nilai benar jika file ada dan dimiliki oleh ID Grup yang cocok
- `-O file` Mengembalikan nilai benar jika file ada dan dimiliki oleh ID pengguna yang cocok
- `-N file` Mengembalikan nilai benar jika file ada dan diubah berdasarkan tanggal baca terakhir
- `-L file` Mengembalikan nilai benar jika file ada dan merupakan Tautan simbolis
- `file1 -ot` file2 Mengembalikan nilai benar jika file1 lebih tua dari file2 atau file2 ada, file1 tidak ada
- `file1 -ne` file2 Mengembalikan nilai benar jika file1 lebih baru dari file2, file1 ada, file2 tidak ada
- `file1 -ef` file2 Mengembalikan nilai benar jika file1 dan file2 menunjuk ke perangkat dan inode yang sama

## Bash Pernyataan Khusus

Ini digunakan untuk membandingkan masukan yang diberikan dengan beberapa pola, dan perintah di dalam pola yang cocok dijalankan.

<b>Syntax</b>

<pre>case expression in

pattern1)
  ## Commands
  ;;
pattern1)
  ## Commands
  ;;
*)
   ## Default case to execute if none of the pattern is matched
  ;;</pre>

- ekspresi adalah variabel atau ekspresi yang valid untuk dievaluasi
- Ini berisi pola defiend di dalam case yang dievaluasi dengan membandingkan ekspresi, mencocokkan case fuound, mengeksekusi perintah di - dalamnya.
- case default ( `*`)) untuk dijalankan jika tidak ada pola yang cocok
- Setiap blok pola diakhiri dengan a`;;`
- `case` adalah kata awal dan `esac` merupakan kata yang mengakhiri pernyataan kasus

<b>contoh</b>

<pre>name="john1"

case $name in
    "john")
        echo "John."
        ;;
    "others" | "others2")
        echo "Other names."
        ;;

    *)
        echo "Default Name."
        ;;
esac</pre>

## Bash Karakter Khusus

Karakter khusus di bash dievaluasi dengan arti khusus dalam interpretasi suatu perintah. Karakter-karakter ini memiliki instruksi khusus, penggunaan karakter ini memiliki arti berbeda dalam konteks berbeda

### Ruang kosong(" "):

Ini juga disebut spasi putih, berisi tab, spasi, kembali, baris baru. Ini memberitahu penerjemah bash untuk memisahkan perintah dan konten. Ini adalah pembatas untuk memisahkan perintah dan string.

<pre>echo "Hello World"</pre>

Contoh di atas, echo adalah perintah yang diikuti spasi, dan strign berisi spasi untuk kata

### Ekspansi ($)

Simbol tanda dolar digunakan untuk berbagai jenis ekspansi parameter ekspansi, ( `$variable`, `${variable}`) Substitusi ( `$(expression)`) ekspresi artematis ( `$((expression))`)

### Ambersand (`&`)

Menambahkan `&k`e akhir perintah memungkinkan Anda menjalankan perintah di latar belakang.

<pre>command $</pre>

Misalnya, Untuk menjalankan server redis di latar belakang, gunakan perintah di bawah

<pre>redis-server &</pre>

### Pipe(`|`)

Ini digunakan untuk meneruskan keluaran dari satu perintah ke masukan ke perintah lain dari kiri ke kanan. Hal ini memungkinkan untuk membentuk rantai perintah

Sintaksnya adalah`command1 | command2`

Contoh : `echo "hello" | wc` mengembalikan jumlah karakter.

### Titik koma(`;`)

Ini digunakan untuk memisahkan beberapa perintah menggunakan `;`satu baris. `;`adalah pemisah perintah untuk mendefinisikan beberapa perintah dalam satu baris Sintaks:`command1; command2;command3`

Contoh:`cd /app/;ls;`

### Kutipan tunggal (Single Quotes)

Tanda kutip tunggal ( `'`) digunakan untuk mendefinisikan suatu string tanpa arti khusus. Artinya semua variabel dan ekspansi tidak diinterpretasikan dan mencetak string literal yang sama

<pre>name="Eric"

echo "Hi, $name"  # Hi, Eric
echo 'Hello, $name'  # Hi $name</pre>

Contoh, Gema pertama, variabel nama diperluas dan diinterpretasikan sebagai string dan dicetak. Gema kedua, menggunakan tanda kutip tunggal, dan variabel nama tidak diperluas dan dicetak sebagai string literal.

Jika kutipan tunggal berisi quoe tunggal bersarang, Anda harus menghindarinya menggunakan ```.

<pre>echo 'test string with nested single quote: '\''Hello'\'''</pre>

Contoh berisi ``` adalah karakter kutipan tunggal di dalam kutipan tunggal

### Kutipan ganda (Double Quotes)

Tanda kutip ganda ( `'`) digunakan untuk mendefinisikan string literal dengan arti khusus.

jika string berisi variabel dan sintaks perluasan, Ini diinterprestasikan dan diperluas, dengan nilai yang dievaluasi saat runtime.

jika string tidak ingin memperluas variabelnya, maka Anda dapat keluar `\`sebelum `$`simbol dolar

<pre>name="Eric"

echo "Hi, $name"  # Hi, Eric
echo "Hi, \$name"  # Hi, $name
</pre>

ontoh, Gema pertama, variabel nama diperluas dan diinterpretasikan sebagai string dan dicetak. Gema kedua, karakter escape dengan awalan $ `\`, dicetak sebagai string literal.

Misal

<pre>echo escape $$ example # escape 3225 example
echo escape \$$ example # escape $$ example</pre>

Pada contoh pertama, echo berisi `$$`, yang menampilkan id proses. Pada contoh kedua, echo berisi `\$$`, yang ditampilkan `$$` sebagai string literal. karakter escape diawali.

### Komentar ( `#`) (Comment)

Simbol komentar digunakan untuk mengomentari sebaris kode. Baris komentar selalu dimulai dengan `#`.

<pre># Line comment
echo "comment example" # Inline comment</pre>

### Tanda tanya( `?`)

tanda tanya mempunyai arti yang berbeda dalam konteksnya.

- Dalam konteks ekspresi reguler
- Di dalam
  periksa status keluar dari eksekusi perintah terakhir.

### Dot(`.`)

## Bash - if elif else

Skrip Bash menyediakan ekspresi kondisional untuk mengeksekusi kode berbeda berdasarkan kondisi yang ditentukan.

Sedang dimainkan

### Pernyataan Bersyarat Bash Shell

Terkadang, Anda mungkin perlu mengeksekusi beragam blok kode bergantung pada berbagai keputusan berdasarkan kondisi tertentu.

Skrip Bash memfasilitasi hal ini melalui pernyataan kondisional

<pre>  if condition; then
     # true code
  elif another_condition; then
     # condition is false, and another_condition is true
  else
     # none of the above conditions are true
  fi</pre>

- Pernyataan tersebut `if`digunakan untuk mengeksekusi blok kode jika suatu kondisi benar, dengan sintaksis `if then fi`.
- Pernyataan ini `else`digunakan untuk mengeksekusi kode jika suatu kondisi salah, mengikuti sintaksis `if then else fi`.
- Pernyataan ini `if..elif..elseberguna` ketika Anda perlu mengeksekusi kode jika tidak ada kondisi sebelumnya yang benar.

Sintaksnya - adalah sebagai berikut:

<b>Catatan</b>

- Kondisi adalah ekspresi yang mengevaluasi `true`atau `false` dalam skrip shell.
- Spasi diperlukan sebelum dan sesudah `[ dan ]`.
- Diperlukan titik koma sebelum itu.
- `if, else, then, elif, fi` adalah kata-kata khusus di Bash.
- Kondisi adalah ekspresi dengan perintah.
- Perintah yang berisi sintaks tanda kurung tunggal, contoh sintaksis `[expression]`dan digunakan untuk operasi string file.
- Sintaks tanda kurung ganda, contohnya adalah `[[expression]]`, yang digunakan untuk menggabungkan beberapa kondisi dan menangani pola regex.
- Tanda kurung ganda, contoh sintaksnya adalah `((expression))`, digunakan untuk operasi aritmatika.

### Jika Pernyataan Bersyarat

Pernyataan `if`di Bash digunakan untuk mengeksekusi blok kode ketika kondisi tertentu adalah `true`.

<pre>if [ condition ]; then
   # Execute code block if the condition is true
fi</pre>

Dalam sintaks di atas:

- Ganti `[ condition ]` dengan ekspresi kondisional.
- Blok kode dalam pernyataan `if` dieksekusi hanya jika kondisi yang ditentukan bernilai benar.
- Setiap `if`pernyataan harus diakhiri dengan `fi`.

<b>Contoh</b>

<pre>age=10
if [ $age -lt 50 ]; then
   echo "$age is less than 50"
fi
</pre>

<b>Output:</b>

<pre>10 is less than 50</pre>

### Pernyataan Kondisional If-Else

Pernyataan `if-else` kondisional di Bash memungkinkan Anda untuk mengeksekusi blok kode yang berbeda tergantung pada apakah suatu kondisi `true`atau `false`.

<pre>if [ condition ]; then
   # Execute code block if the condition is true
else
   # Execute code block if the condition is false
fi</pre>

Dalam sintaks di atas:

- Ganti `[ condition ]` dengan ekspresi yang akan diuji.
- Blok kode dalam `if`pernyataan dijalankan jika kondisi yang ditentukan adalah `true`.
- Blok kode dalam `else`pernyataan dijalankan jika kondisinya adalah `false`.
- Setiap pernyataan `if-else` harus diakhiri dengan `fi`.

<pre>#! /bin/sh
age=25
if [[ $age -gt 60 ]]; then
     echo "Senior Citizen"
else
     echo "Not Senior Citizen"
fi</pre>

Dalam contoh ini, jika usianya lebih dari 60 tahun, maka akan dihasilkan “Warga Negara Lanjut Usia”; jika tidak, akan ditampilkan “Bukan Warga Negara Lanjut Usia”.

### Pernyataan If..Elif..Else

Gunakan `if..elif..else` pernyataan kondisional di Bash untuk mengeksekusi blok kode berbeda berdasarkan beberapa kondisi.

<pre>if [ condition1 ]; then
	# Execute code if condition1 is true
elif [ condition2 ]; then
	# Execute code if condition1 is false and condition2 is true
else
	# Execute code if both condition1 and condition2 are false
fi</pre>

- Blok kode dalam `if`pernyataan pertama dijalankan jika `condition1`is `true`.
- Blok kode dalam `elif`pernyataan pertama dijalankan jika `condition1`benar `false`dan `condition2`benar``.
- Blok `else`dijalankan jika keduanya `condition1`salah `condition2`.
- Setiap `if..elif..else`pernyataan harus diakhiri dengan `fi`.

<b>Contoh</b>

<pre>age=25
if [[ $age -gt 60 ]]; then
    echo "Senior Citizen"
elif [[ $age -lt 14 ]]; then
    echo "Child"
else
    echo "Adult"
fi</pre>

Dalam contoh ini, skrip memeriksa apakah usia lebih besar dari 60, kurang dari 14, atau tidak termasuk dalam kategori apa pun, dan menampilkan pesan yang sesuai

## Bash Loops

Misalkan Anda ingin menjalankan perintah berulang kali atau mencetak array.for loop digunakan di Bash

Berbagai jenis loop

Skrip Bash menyediakan berbagai jenis loop

- For loops
- For Indexs Loops
- While Loops
- Until Loops

### For loop

for loop digunakan untuk mengeksekusi kode beberapa kali berdasarkan

<pre>for element in [list]
do
 ## Code block
done</pre>

Contoh ini mengulangi daftar dan mencetak ke konsol.

<pre>for element in 1 2 3 4 5
do
  echo $element
done</pre>

### For Indexs Loops

untuk **For Indexs Loops** mirip dengan bahasa C untuk loop indeks. Ini mengeksekusi kode beberapa kali berdasarkan kondisi benar, Ini dimulai dengan nilai awal dan iterasi berisi nilai yang akan bertambah 1.

<pre>for (( assignment; condition; iteration )); do
  # code block
done</pre>

**Contoh**

<pre>for ((i=0;i<5;i++));do
 echo $i
done</pre>

Ini mencetak angka dari 0 hingga 5

### While Loops Di Bash

Perulangan `while`di Bash memungkinkan eksekusi kode berulang selama kondisi yang ditentukan adalah `true`. Jika kondisinya menjadi `false`, perulangan akan keluar.

Struktur dasar perulangan while adalah sebagai berikut:

<pre>while [ condition ]; do
  # code block
done</pre>

**Contoh**

<pre>i=0
while [[ i -lt 100 ]]; do
  echo "$i"
  i=$((i+1))
done</pre>

while loop mengeksekusi kode selama kondisi yang ditentukan ( `[[ i -lt 100 ]]`) benar.

Blok kode menambah nilai sebesar 1 dan mencetak nilainya.

jika kondisi salah, loop keluar.

### Until Loops di Bash

Kata kunci `until` di Bash digunakan untuk mengeksekusi kode berulang kali hingga kondisi tertentu menjadi `true`, di mana loop keluar.

Struktur dasar dari perulangan sampai adalah sebagai berikut:

<pre>until [ condition ]; do
  # code block
done</pre>

`until`kata kunci digunakan di Bash dan diakhiri dengan `done`

<pre>i=0
until [[ i -eq 100 ]];
do
 echo "$i"
 i=$((i+1))
done</pre>.

Dalam contoh ini, blok kode dijalankan selama [[i -eq 100]]bernilai salah. Ini menambah nilai sebesar 1 dan mencetak nilainya.

output mencetak angka dari 0 hingga 99 angka

## Bash - Append String

### Ekspresi Bash Athematic

Ekspresi artema digunakan untuk melakukan operasi matematika

ekspresi adalah istilah yang digunakan dalam matematika untuk menunjukkan suatu operasi. Ini berisi operan dan operator untuk melakukan operasi matematika. `a<b` adalah sebuah ekspresi. Ini mungkin berisi operator biner atau unary

Di bash, Experssions dibuat menggunakan `(())` tanda kurung dengan operan dan operator sebagai argumen. `((a ))` adalah ekspresi bash.

**Sintaksnya adalah**:

<pre>((expression))</pre>

ekspresi adalah operasi matematika, Ini dapat berisi sub ekspresi yang dipisahkan dengan koma.

<pre>result=$((12 + 11))
echo "$result"</pre>

## Bash Fungsi

Fungsi adalah kode yang dapat digunakan kembali dan dikelompokkan dalam satu nama.

Mendeklarasikan suatu fungsi Memanggil Fungsi Fungsi dengan argumen Cakupan variabel dalam Fungsi

### Bagaimana mendeklarasikan suatu Fungsi dan memanggilnya

Definisi fungsi berisi beberapa baris kode yang akan dieksekusi.

Fungsi berisi nama fungsi yang diapit `{}`.

Itu dapat dideklarasikan dengan dua cara

<pre>
function function_name {
# Commands or valid bash code
# multiple lines
}</pre>

<pre>
function function_name() {
  # Commands or valid bash code
  # multiple lines
}</pre>

**Cara meneruskan parameter ke suatu fungsi**

<pre>function_name "parameter1" "parameter2" "parameter3".. "parametern"</pre>

Parameter dapat diakses menggunakan $1 $2 $3.. $n

<pre>function function_name() {
# $1 represents first paramter
# $2 represents second paramter

# $n represents nth paramter
}</pre>

## Bash Tambahkan String

### Penambahan variabel sederhana

Mulailah dengan mendeklarasikan dua variabel string dalam skrip Bash, yang dapat dicetak ke konsol menggunakan echo dengan mengapit variabel dalam tanda kutip ganda.

<pre>string1="Hello, "
string2='Welcome to w3schools.'
echo "$string1 $string2 "</pre>

**Output**

<pre>Hello, Welcome to w3schools.</pre>

### Gunakan Operator Aritmatika Singkatan

Operator aritmatika singkat ( `+=`) biasanya digunakan dalam aritmatika untuk menambahkan nilai ke suatu variabel. Ini juga dapat digunakan untuk string untuk menambahkan string ke variabel.

**Misalnya**.

`a+=1`setara dengan `a=a+1`dalam hal angka.
`str+="test"`akan menjadi `str=str+"test"`dalam kasus string.

**Berikut adalah contoh kode**

<pre>nums="One Two"
nums+=" three"
echo "$nums"</pre>

**Output**

<pre>One Two three</pre>

### Gunakan perintah printf

`printf`digunakan untuk memformat string dengan berbagai opsi pemformatan yang kompleks. Kita dapat menggunakan `printf`perintah untuk menggabungkan `string`. Formatnya adalah `%s%s`,menambahkan dua variabel string.

<pre>str1="Hello, "
str2='Welcome to w3schools.'
output=$(printf "%s%s" "$str1" "$str2")

echo $output</pre>

### Menggunakan string di sini

`Here strings`adalah sintaks khusus untuk meneruskan string ke perintah dalam skrip Bash. Mereka digunakan untuk meneruskan string input tanpa menggunakan sumber lain, seperti file. Ini memungkinkan meneruskan string ke perintah Bash apa pun dari file atau baris perintah.

**Sintaksis**:

<pre>command <<< string</pre>

perintah: sah perintah `<<<`: adalah a`here string operator`

string adalah string masukan

**Ini sebuah contoh**

<pre>first="first "
second" second"
output="$first$(<<<" $second")"
echo $output</pre>

### Kesimpulan

- Penambahan variabel sederhana dan operator aritmatika ( `+=`) digunakan untuk penggabungan string yang dasar dan mudah.
- Jika Anda memerlukan pemrosesan string yang lebih kompleks bersamaan dengan penggabungan, `printf`disarankan.

## Bash Operator

Apa itu ooperator?
Operator adalah simbol dalam pemrograman yang melakukan operasi pada operan

**Sintaksis:**

<pre>operand1 operator operand2</pre>

Ada dua jenis operartor

- Operator Biner: Ini beroperasi pada dua operan seperti penjumlahan, pengurangan, perkalian, pembagian, dan modulus
- operator unary: Ini beroperasi pada operan tunggal seperti kenaikan dan penurunan

### Operator Aritmatika Bash

Operator aritmatika di Bash menyediakan operasi aritmatika seperti operator penjumlahan, pembagian, pengurangan, dan perkalian pembagian.

| Operator | Judul       | Keterangan                                 | Contoh            |
| -------- | ----------- | ------------------------------------------ | ----------------- |
| +        | Tambahan    | Penambahan dua atau lebih operan           | p+q=50            |
| -        | Pengurangan | Pengurangan dua atau lebih operan          | q-p=10            |
| \*       | Perkalian   | Perkalian dua atau lebih operan            | p\*q=600          |
| /        | Membagi     | Hasil bagi setelah pembagian nilai         | q/p=1.5           |
| %        | Modulus     | Kembalikan sisanya setelah pembagian nilai | q%p=10            |
| -expr    | Minus Unary | Kebalikan dari suatu ekspresi              | -(10-7) adalah -3 |
| ~/       | Divisi Int  | Mengembalikan nilai int pembagian          | (10~/7) adalah 1  |
| ++       | Kenaikan    | Tambahkan nilainya sebesar 1               | ++p=21            |
| --       | Pengurangan | Kurangi nilainya sebesar 1                 | --q=29            |

### Operator Penugasan

Operator penugasan digunakan untuk menetapkan nilai ke suatu variabel. Operasi dasarnya sama dengan (=)

| Operasi          | Simbol | Keterangan                           | Hasil                 |
| ---------------- | ------ | ------------------------------------ | --------------------- |
| Tambahkan Tugas  | `+=`   | Penambahan dan penugasan ke variabel | ((p += 3)) adalah 23  |
| Kurangi Tugas    | `-=`   | Kurangi dan tugaskan ke variabel     | ((p -= 3)) adalah 17  |
| Perkalian Tugas  | `*=`   | Perkalian dan penugasan ke variabel  | ((p \*= 2)) adalah 40 |
| Penugasan Divisi | `/=`   | Pembagian dan penugasan ke variabel  | ((p /= 5)) adalah 4   |

### Operator Bitwise

| Operasi                   | Simbol | Keterangan                                     | Hasil                  |
| ------------------------- | ------ | ---------------------------------------------- | ---------------------- |
| DAN                       | `&`    | Bitwise AND dari dua operan                    | $op1 & $op2 adalah 0   |
| DAN Setara                | `&=`   | Bitwise DAN Sama dengan dua operan             | $op1 & $op2 adalah 0   |
| ATAU                      | `\|`   | Bitwise OR dari dua operan                     | $op1 \| $op2 adalah 7  |
| XOR                       | `^`    | XOR bitwise dari dua operan                    | $op1 ^ $op2 adalah 7   |
| Pergeseran Kiri           | `<<`   | Pergeseran Kiri Bitwise dari dua operan        | $op1 << $op2 adalah 0  |
| Persamaan Pergeseran Kiri | `<<=`  | Pergeseran Kiri Bitwise Sama dengan dua operan | $op1 <<= $op2 adalah 7 |
| XOR                       | `^`    | XOR bitwise dari dua operan                    | $op1 ^ $op2 adalah 7   |
| XOR                       | `^=`   | Bitwise XOR Sama dengan dua operan             | $op1 ^= $op2 adalah 7  |

### Operator logika

Operator ini digunakan untuk melakukan operasi logika pada variabel/ekspresi/data.

- Operasi Simbol Keterangan Hasil
- Logis DAN `&&` Kembalikan nilai benar (status keluar = 0) jika kedua operan benar, jika tidak, kembalikan salah (status keluar bukan nol) $op1 &&& $op2 adalah 0
- Logis ATAU `||` Logis OR dari dua operan `$op1 & $op2 adalah 0`
- Logis TIDAK `\!` Balikkan nilai bersyarat. `$op1 s 7`

### Operator Perbandingan String

Operasi Keterangan

- `-z` Tali Kembalikan nilai benar jika string kosong, jika tidak salah.
- `-n` Tali KEMBALI benar, Jika string tidak kosong
- ` str1=``str2 ` kembalikan nilai true, jika `str1` dan `str2` sama
- ` str1!``=str2 ` mengembalikan nilai `true`, jika str1 dan `str2` tidak sama
- ` str1>``str2 ` kembali benar, jika `str1` mengurutkan sebelum `str2`
- ` str1<``str2 ` kembali benar, jika `str1` mengurutkan setelah `str2`

### Operator Perbandingan Numerik

**Berikut ini adalah operator Perbandingan.**

menggunakan operator -eq dalam `if fi`pernyataan kondisional

<pre>first=13
second=15

if [ "$first" -eq "$second" ]; then
  echo "Two numbers are equal";
fi</pre>

## Bash - Perbandingan Angka

membandingkan dua angka untuk sama atau tidak dalam pemrograman bash dan shell.

Angka dapat berupa bilangan bulat atau angka mengambang.

### Cara Memeriksa apakah dua angka sama atau tidak di Bash

Program ini mengambil nilai masukan dan memeriksa apakah dua nilai sama atau tidak

<pre>first=13
second=15
if (( first == second )); then
  echo "Two numbers are equal";
fi</pre>

**Berikut ini adalah operator Perbandingan**.

- `-eq`: setara

- Periksa apakah dua variabel sama
- `-ne`: Tidak sama

- Periksa apakah dua variabel tidak sama
- `-lt`: Kurang dari

Periksa apakah variabel pertama lebih kecil dari variabel kedua

- `-le`: Kurang dari sama

- Periksa apakah variabel pertama kurang dari sama dengan variabel kedua
- `-gt`: Lebih besar dari

- Periksa apakah variabel pertama lebih besar dari variabel kedua
- `-ge`: Lebih besar dari atau sama dengan

Bandingkan Periksa apakah variabel pertama lebih besar dari sama dengan variabel kedua

menggunakan operator -eq dalam `if fi`pernyataan kondisional

<pre>first=13
second=15

if [ "$first" -eq "$second" ]; then
  echo "Two numbers are equal";
fi</pre>

Anda juga dapat melakukannya dengan operator ternary.

<pre>first=13
second=15

echo $(( first == second ?  "equal": "not equal" ))</pre>

## Bash Check Directory

Mempelajari cara menentukan apakah suatu direktori ada dalam skrip Bash.

### Skrip Bash Periksa apakah direktori tersebut ada

Pada contoh di bawah, `if`blok digunakan untuk menguji ekspresi kondisional untuk keberadaan direktori.

### Periksa apakah Direktori Ada dan Cetak Pesan

Ekspresi kondisional menggunakan `-d`opsi untuk memeriksa apakah direktori tersebut ada.

### periksa direktori yang ada dan cetak pesannya.

Ekspresi kondisional berisi `-d`opsi dan jalur direktori. `-d`opsi yang memeriksa apakah direktori ada atau tidak.

**Contohh**

<pre>FOLDER=test

if [ -d "$FOLDER" ]; then
    echo "Directory Exists"
fi</pre>

### Bagaimana cara mkdir hanya jika direktori belum ada?

Dalam contoh ini, menggunakan blok kondisional `if-else`.

- Diperiksa apakah direktori tersebut ada menggunakan `-d`.
- `else` blok akan memiliki kode untuk tidak ada dan membuat direktori menggunakan jalur direktori

**Berikut kodenya**

<pre>FOLDER=test

if [ -d "$FOLDER" ]; then
    echo "Directory Exists"
else
    echo "Directory Exists"
    mkdir "$FOLDER"
fi</pre>

### Periksa keberadaan direktori menggunakan sintaks ternary

Alternatifnya, ekspresi kondisional ternary digunakan sebagai pengganti ekspresi kondisional if.

**Berikut adalah contoh ekspresi kondisional**

<pre>FOLDER=test
[ -d "$folder" ] && echo "folder exists" || echo "folder not exist"</pre>

### Periksa apakah ada beberapa direktori Terkadang, Kami ingin memeriksa apakah ada beberapa direktori.

<pre>FOLDER1=test1
FOLDER2=test2

if [ -d "$FOLDER1" ] && [ -d "$FOLDER2" ] then
   echo "Folder1 and Folder2 exist"
fi</pre>

### Periksa apakah direktori ada dan dapat ditulis serta dieksekusi

Dalam contoh ini, Kode memeriksa hal-hal di bawah ini

- foldernya ada atau tidak
- jika ada, Folder tersebut memiliki izin untuk menulis dan dieksekusi.
- Terakhir, Cetak pesan string

<pre>FOLDER=test

if [ -d "$FOLDER" -a -w -x "$FOLDER" ]
then
    echo "Directory exists, writable and executable"
fi</pre>

### Periksa file atau direktori yang ada

Terkadang, kami ingin memeriksa apakah file atau direktori tersebut ada. Opsi `-e` memeriksa file atau direktori untuk jalur yang diberikan ada atau tidak

<pre>FILE_DIRECTORY=test
if [ -e "$FILE_DIRECTORY" ]
then
    echo "file or directory of test exists."
fi</pre>

## Bash Nama File

Dalam skrip Bash, Anda mungkin perlu mengekstrak nama file dan ekstensi dan menyimpannya ke dalam variabel. Tutorial ini menunjukkan cara mencapai ini untuk file tertentu.

- Ekstrak nama file untuk path lengkap yang diberikan
- mendapatkan nama file lengkap

### Ekstrak nama file dengan ekstensi

Untuk mendapatkan nama file beserta ekstensinya, `basename`perintah dapat digunakan untuk menghapus direktori dan hanya mengembalikan nama `filename`untuk jalur tertentu, baik itu a `variable`atau string.

Misalnya, jika jalurnya adalah `/home/john/run.sh`, nama file yang dikembalikan adalah `run.sh`. Proses ini melibatkan pengambilan jalur lengkap dan mengekstraksi hanya `filename`dengan menghapus jalur. Hasilnya `filename`kemudian disimpan dalam variabel dan dicetak ke konsol.

nama dasar digunakan untuk menghapus direktori dan mengembalikan nama file untuk jalur yang diberikan. jalurnya adalah variabel atau string. Misalnya, jalurnya adalah `/home/john/run.sh`, dan nama file yang dikembalikan adalah. `run.sh` Dalam hal ini, jalur lengkap diberikan dan mengembalikan nama file dengan menghapus jalurnya.

Nama file disimpan ke variabel dan dicetak ke konsol.

<pre>file_path="/home/john/run.sh"
filename=$(basename "$file_path")
echo $filename</pre>

**Output**

<pre>run.sh</pre>

### Ekstrak nama file tanpa ekstensi

Untuk mendapatkan hanya nama file tanpa ekstensi, Anda dapat menggunakan sintaksis `${filename%.*}`.

Misalnya, pertimbangkan jalur `/home/john/run.sh` yang akan menjadi nama file yang dihasilkan `run.sh`.

Awalnya, `basename`perintah ini digunakan untuk menghilangkan direktori dan menghasilkan nama file untuk jalur yang ditentukan dan mengembalikan variabel, dan variabel ini kemudian digunakan bersama dengan sintaks ekspresi untuk menghapus ekstensi dari nama file.

Ekspresi ini secara efektif menghapus ekstensi dari nama file.

<pre>filepath="/home/john/run.sh"
filename=$(basename "$filepath")
echo $filename
echo "File Name: ${filename%.*}"</pre>

**Output**

<pre>File Name: run</pre>

Berikut adalah contoh komprehensif yang menunjukkan cara mendapatkan nama file dengan atau tanpa ekstensi file. Setelah menjalankan skrip di bawah ini, skrip tersebut akan dicetak

- file dengan ekstensi,
- hanya nama file tanpa ekstensi,
- dan ekstensinya saja.

**Contoh**

<pre>filepath="/home/username/run.sh"
filename=$(basename "$filepath")
echo "File :$filename"
echo "File Name: ${filename%.*}"
echo "File Extension: ${filename##*.}"</pre>

**Output**

<pre>File:run.sh
File Name:run
File Extension:sh</pre>

### Kesimpulan

Skrip ini menunjukkan berbagai pendekatan untuk menangani nama file dan ekstensi di lingkungan Bash.

## Bash Pisahkan String

Dalam beberapa kasus, saat bekerja dengan skrip bash, timbul kebutuhan untuk memisahkan string berdasarkan pembatas dan mengekstrak beberapa string untuk diproses lebih lanjut atau disimpan dalam variabel.

**Artikel ini membahas tiga metode**.

- Pisahkan string menggunakan perintah awk
- Gunakan variabel IFS
- Ekspansi Parameter dengan for loop

### Pisahkan string menggunakan perintah awk dalam skrip bash shell

Perintah tersebut `awk`, sebuah utilitas Linux yang kompatibel dengan semua distribusi bash dan shell, digunakan untuk membagi string berdasarkan `delimiter`.

Input diberikan menggunakan simbol pipa (|), dan contoh di bawah ini menunjukkan pemisahan string yang mengandung titik dua (` :`)

<pre>str="abc:def:ghi"
echo "$str" | awk -F':' '{print $1,$2,$3}'</pre>

**Output**

<pre>abc def ghi</pre>

### dibagi menggunakan variabel IFS

Di sini, string masukan terdiri dari elemen yang dipisahkan oleh `hyphens`. Variabel shell `IFS`(Pemisah Bidang Internal) diatur ke tanda hubung, dan string diiterasi menggunakan perulangan for.

Setiap elemen dicetak setelah tanda hubung dihilangkan.

<pre>input="one-two-three"
IFS='-' array=($input)
for element in "${array[@]}";
do
 echo $element;
 done</pre>

**Output:**

<pre>one
two
three</pre>

### Gunakan ekspansi Parameter dan loop

Perluasan parameter digunakan untuk mengubah nilai variabel berdasarkan opsi yang ditentukan. Dalam hal ini, variabel string diubah menjadi array. Array kemudian diiterasi menggunakan sintaks for loop, mencetak setiap elemen ke konsol:

<pre>msg="Welcome to my site."

array=($msg)


for item in "${array[@]}"; do
    echo "$item"
done</pre>

## Bash String Length

Panjang string ditentukan oleh jumlah karakter yang dikandungnya, dan umumnya mudah untuk memastikan panjangnya untuk teks normal.

Metode pertama melibatkan penggunaan `${#variable}` sintaksis untuk mendapatkan panjang variabel string

Dalam hal ini, jumlah karakter dalam variabel string.

<pre>msg="Hello World."
count=${#msg}

echo $count # 12</pre>

**Output:**

<pre>12</pre>

Metode kedua melibatkan penggunaan perintah wc -m, baik secara langsung dengan string atau melalui variabel.

<pre>echo -n 'Hello World.' | wc -m; # 12

result=`echo -n $msg | wc -m`
echo $result # 12

result1=`echo  $msg | wc -m`
echo $result1 # 12</pre>

Dalam contoh ini, `echo -n` "`string`"digunakan untuk mencetak string tanpa baris baru `( -n option)`. Operator |pipa mengarahkan output dari perintah sisi kiri ke perintah sisi kanan, dan `wc -m`menghitung jumlah karakter dalam sebuah string.

**Output:**

<p>12
12
12</p>

Menggunakan `expr`Perintah Metode lain melibatkan penggunaan exprperintah untuk mencari panjang string.

<pre>
msg="Hello World."

count=$(expr length "$msg")

echo $count # 12</pre>

Di sini, `${}`mewakili substitusi ekspresi, mensubstitusi nilai ekspresi ke dalam string. `expr`mengeksekusi `expressions`, dan `length`merupakan argumen yang diteruskan `expr`untuk menemukan panjang string.

`$(expr length "$msg")`mengembalikan jumlah karakter dalam string, ditetapkan ke variabel, nilai variabel dicetak ke konsol

- menggunakan perintah awk Awkmenyediakan cara lain untuk menghitung panjang string menggunakan ekspresi.

<pre>msg="Hello World."
count=${#msg}

echo $count # 12

count=$(echo -n "$msg" | awk '{print length}')
echo $count # 12</pre>

Dalam hal ini, `echo -n "$variable"`keluaran string tanpa baris baru, dan keluaran disalurkan `awk`menggunakan simbol pipa(` |`). Perintah `awk` `'{print length}'`menghitung dan mencetak panjang baris input.

Dengan menggabungkan metode di atas dalam sebuah ekspresi `${}`, Anda bisa mendapatkan panjang string.

### Kesimpulan

Posting ini telah membahas berbagai cara untuk menentukan panjang string di Bash. Pilihan pendekatan dapat bergantung pada preferensi Anda.

## Bash - Bashrc

Skrip bash atau shell .bashrc memuat ulang dan contoh lokasi untuk Membagi string menjadi beberapa string menggunakan contoh `awk` dan `ifs`.

File .bashrc adalah file skrip bash yang dijalankan dalam kasus berikut:

- menggunakan eksekusi skrip bash
- bash shell dibuka dan dimulai secara interaktif

File ini disembunyikan secara default karena file dimulai dengan . disembunyikan

### Di mana file bashrc di Linux?

File .bashrc adalah skrip yang dijalankan saat pengguna login. File ini terletak di direktori home pengguna.

Ini berisi variabel lingkungan dan preferensi pengguna yang akan dikonfigurasi dalam file ini.

### Bagaimana cara melihat file .bashrc?

Anda dapat menggunakan editor Vi atau Nano untuk melihat file bashrc.

**Berikut ini adalah sebuah perintah**

<pre>nano ~/.bashrc
nano ~/.bashrc</pre>

### Di mana file bashrc berada?

file bashrc terletak di dua tempat

- direktori home pengguna
- Direktori sistem

Dalam kasus direktori home pengguna, file ini disembunyikan secara default. Lokasinya adalah `~/.bashrctempat` ~ pengguna saat ini login di direktori home.

Dalam hal direktori Sistem, file ini terletak di `/etc/bash.bashrc`.

### Bagaimana cara memuat ulang pengaturan .bashrc tanpa keluar dan masuk kembali?

jika Anda membuat perubahan apa pun pada file .bashrc, Perubahan tidak akan langsung terlihat. Anda harus menutup dan memulai kembali sesi bash untuk melakukan perubahan.

**Bagaimana cara memuat ulang konfigurasi .bashrc tanpa login lagi? Jalankan perintah berikut di command prompt**.

<pre>source ~/.bashrc</pre>

**atau cara yang lebih pendek menggunakan perintah di bawah ini**

<pre>. ~/.bashrc</pre>

**atau jalankan bash lagi menggunakan perintah di bawah ini**

<pre>exec bash</pre>

perintah exec mengatur ulang sesi saat ini, dan memulai lagi.

## Bash - Operator Terner

**Contoh skrip bash atau shell untuk ekspresi Operator Ternary beserta contohnya**

Pemrograman Bash tidak memiliki dukungan untuk sintaks operator ternar
Operator ternary ditulis dalam bahasa Java

<pre>expression?value1:value2</pre>

Sintaksnya mirip dengan ekspresi kondisional if dan else. jika ekspresi benar, nilai1 dikembalikan, jika tidak, nilai2 dikembalikan.

### Cara menggunakan Operator ternary di Bash

Ada beberapa cara kita dapat menulis sintaksis sebagai pengganti sintaksis operator ternary.

Cara pertama, gunakan if-else dengan sintaks ekspresi.

<pre>AGE=25
if [ "$AGE" -eq 25 ]; then result="true"; else result="false"; fi
echo "$result" ;</pre>

**Cara kedua, gunakan ekspresi aritmatika menggunakan && dan || Sintaksnya adalah**

<pre>[expression1] && Expression2|| Expression3</pre>

jika ekspresi1 benar, Ekspresi2 dievaluasi, jika tidak, Ekspresi3 dievaluasi

**Berikut adalah contoh programnya**

<pre>[ $AGE == 25 ] && result="true" || result="false"
echo "$result" ;</pre>

Ada cara lain untuk menetapkan variabel, bukan ekspresi.

dengan menggunakan mari kita dapat menetapkan variabel berdasarkan hasil ekspresi kondisi

<pre>first=10
second=true
third=false
let result="(first==10)?second:third"

echo $result # true</pre>

## Bash - Huruf kecil

Misalnya, jika string inputnya adalah “Selamat Datang Halo Dunia”, outputnya akan menjadi “selamat datang di dunia”.

Ada beberapa cara untuk mencapai hal ini, bergantung pada jenis dan versi Bash.

- menggunakan perintah tr

Perintah `tr`, kependekan dari `translator`, adalah perintah Unix yang digunakan untuk mengonversi karakter dari satu format ke format lainnya.

Sintaksnya adalah sebagai berikut:

berikut adalah sintaksnya.

<pre>tr input_format output_format</pre>

Berikut skrip bash shell yang digunakan `tr`untuk mengonversi string menjadi huruf kecil:

<pre>message="Hello World, Welcome."
echo "$message" | tr '[:upper:]' '[:lower:]'</pre>

**Output:**

<pre>hello world, welcome.</pre>

Sebagai alternatif, Anda dapat menggunakan.

<pre>message="Hello World, Welcome."
echo "$message" | tr 'A-Z' 'a-z'</pre>

Catatan: `tr`berfungsi dengan `ASCII`dan tidak mendukung `UTF`karakter.

- menggunakan perintah awk

Untuk mengubah string menjadi huruf kecil menggunakan `awk`perintah, `tolower`fungsinya digabungkan dengan `awk`.

Hasilnya kemudian diteruskan ke perintah echo menggunakan operator pipa:

<pre>message="Hello World, Welcome"
echo "$message" | awk '{print tolower($0)}'</pre>

Metode ini paling baik untuk karakter `ASCII` dan `UTF`.

- Gunakan `Perl` di Bash Script Printing `lc`dengan `Perl`mengubah string menjadi huruf kecil.

`lc` adalah alias untuk huruf kecil.

<pre>echo "$message" | perl -ne 'print lc'</pre>

- gunakan ekspansi Parameter Bash 4.0 memperkenalkan utilitas manipulasi string bawaan. Untuk mengonversi string menjadi huruf kecil, cukup tambahkan dua `commas`ke string. Ini juga disebut sintaks perluasan parameter.

Sintaksnya adalah `${variable[options]}`.

Misalnya,

<pre>message="Hello World, Welcome"
echo "${message,,}"
echo "${message}"</pre>

<pre>msg="Hello World."
result="${msg,,}"
echo $result # hello world.</pre>

Di sini, `${msg,,}` gunakan `,,`opsi untuk mengonversi variabel menjadi huruf kecil.

Perhatikan bahwa ini berfungsi di Bash versi 4.0 dan lebih tinggi.

## Bash Huruf Besar

String huruf besar mengacu pada string yang berisi semua huruf dalam huruf besar.

Misalnya, jika string inputnya adalah “Selamat Datang Halo Dunia”, outputnya akan menjadi “SELAMAT DATANG DUNIA”.

Bergantung pada jenis dan versi bash, ada beberapa metode untuk mengonversi string menjadi huruf besar.

- menggunakan perintah tr

Perintah tersebut tr, yang dikenal sebagai translator, adalah perintah Unix yang digunakan untuk mengonversi karakter dari satu format ke format lainnya.

Sintaksnya adalah sebagai berikut:

<pre>tr input_format output_format</pre>

Berikut skrip shell untuk mengonversi ke huruf besar

<pre>message="This is a lowercase string converted to uppercase"
echo "$message" | tr '[:lower:]' '[:upper:]'</pre>

**Output:**

<pre>THIS IS A LOWERCASE STRING CONVERTED TO UPPERCASE</pre>

**Cara lain untuk mengganti kode di atas**

<pre>message="This is a lowercase string converted to uppercase"
echo "$message" | tr 'a-z' 'A-Z'</pre>

Catatan: `tr`berfungsi dengan `ASCII`dan tidak mendukung `UTF`karakter.

- menggunakan perintah awk

Untuk mengubah string menjadi huruf besar menggunakan `awk`perintah, `toupper`fungsinya digabungkan dengan `awk`. Hasilnya kemudian diteruskan ke perintah echo menggunakan operator pipa:

<pre>message="It is a lowercase string converted to uppercase."
echo "$message" | awk '{print toupper($0)}'</pre>

Yang terbaik adalah bekerja dengan `ASCII`dan `UTF`karakter.

dalam versi bash 4.0 `bash 4.0`menyediakan utilitas manipulasi string bawaan. Menambahkan dua tanda sirkumfleks `(^)` ke sebuah string akan membuat string menjadi string huruf besar

<pre>message="This is a lowercase string converted to uppercase"
echo "${message^^}"
echo "${message}"</pre>.

menggunakan Perl dalam skrip bash
`print uc`perintah di Perl mengubah string menjadi huruf besar

<pre>echo "$message" | perl -ne 'print uc'</pre>

- Gunakan sintaks perluasan parameter Bash 4.0 menyediakan utilitas manipulasi string bawaan. Menambahkan dua tanda sirkumfleks (^) ke sebuah string menjadikannya string huruf besar, juga disebut sintaks perluasan parameter.

Sintaksnya adalah `${variable[options]}`

variabel untuk dimodifikasi berdasarkan opsi. Opsi bersifat opsional yang berisi perluasan parameter

<pre>#!/bin/bash

# Input string
message="hello, world!"

# Convert to uppercase
result="${message^^}"

# Display the result
echo "Original: $message"
echo "Uppercase: $result"</pre>

Sintaks perluasan parameter mengubah string menjadi huruf besar. `${message^^}berisi ^^`opsi untuk mengubah string pesan variabel menjadi huruf besar.

## Bash Substring

Bash Cara memeriksa substring yang ada dalam string menggunakan operator perbandingan dan contoh ekspresi reguler.

### Menggunakan Operator Perbandingan untuk Memeriksa Substring ada atau tidak

- Tentukan variabel string yang berisi teks
- Gunakan pernyataan if untuk membandingkan string dengan substring yang diinginkan menggunakan operator kesetaraan ( `==`) dan wildcard (`*`).
- Terakhir, cetak string jika substring ditemukan.

<pre>mainstring='Welcome to w3schools'
if [[ $mainstring == *"w3schools"* ]]; then
  echo "w3schools exists in the main string"
fi</pre>

### Gunakan Ekspresi Reguler untuk Menemukan Substring

Operator `=~`memfasilitasi pencarian substring dalam string tertentu, digunakan dalam blok `if`.

**Contoh kode**:

<pre>mainstring='Welcome to w3schools'
if [[ $mainstring =~ "w3schools" ]]; then
  echo "w3schools exists in the main string"
fi</pre>

### Gunakan perintah grep

Perintah grep digunakan untuk mencari string tertentu, disalurkan ke string utama untuk perbandingan.

<pre>mainstring='Welcome to w3schools'

if echo "$mainstring" | grep -q "w3schools"; then
  echo "w3schools exists in the main string"
fi</pre>

Metode ini menawarkan pendekatan berbeda untuk memeriksa apakah suatu string berisi substring tertentu, sehingga memberikan fleksibilitas untuk kasus penggunaan yang berbeda.

## Bash Kumpulan Variabel

Periksa variabel disetel atau tidak disetel dalam file skrip bash dan shell dengan contoh kode

- Periksa variabel disetel atau tidak
- variabel kosong atau tidak kosong
- Periksa variabel apakah string kosong atau tidak

Berikut beberapa contoh penggunaan variabel untuk variabel`price`

| Deklarasi variabel      | Keterangan                                             |
| ----------------------- | ------------------------------------------------------ |
| harga;                  | Variabel tidak dideklarasikan dan tidak disetel        |
| harga=;                 | Variabel dideklarasikan dan tidak disetel              |
| harga=3000              | Variabel dideklarasikan, ditetapkan, dan tidak disetel |
| harga=(3000)            | Variabel dideklarasikan, ditetapkan, dan tidak disetel |
| harga tidak ditetapkan; | Variabel tidak dideklarasikan dan tidak disetel        |

### Bagaimana cara memeriksa apakah suatu variabel diatur dalam skrip bash?

Misalnya variabelnya diset artinya,

- Itu dideklarasikan dan ditetapkan dengan kosong atau tidak kosong.

Dalam contoh di bawah ini,

- `variable1`dideklarasikan tetapi kosong

- `variable2`tidak dideklarasikan dan tidak disetel.

<pre>#!/bin/bash
variable1=""
if [[  ${variable1+x}  ]]
then
  echo 'variable1 is set'
else
  echo 'variable1 is not set'
fi

if [[  ${variable2+x}  ]]
then
  echo 'variable2 is set'
else
  echo 'variable2 is not set'
fi
</pre>

**Oupput**

<pre>variable1 is set
variable2 is not set</pre>

Cara lain untuk memeriksa suatu variabel adalah dengan menyetel menggunakan `-v`opsi

<pre>variable1=""
if [ ! -v $variable1 ]
then
    echo "variable1 is unset"
else
    echo "variable1 is set"

fi</pre>

**Output**:

<pre>variable1 is unset</pre>

### Bagaimana cara memeriksa apakah variabel tidak disetel dalam skrip bash?

Misalnya variabelnya tidak disetel artinya

- Itu tidak ada dan tidak diumumkan.
  Dalam contoh di bawah ini,

- `variable1`dideklarasikan tetapi kosong
- `variable2`tidak dideklarasikan dan tidak disetel.

<pre>#!/bin/bash
variable1=""
if [[ ! ${variable1+x}  ]]
then
  echo 'variable1 is not set'
else
  echo 'variable1 is set'
fi

if [[ ! ${variable2+x}  ]]
then
  echo 'variable2 is not set or unset'
else
  echo 'variable2 is  set'
fi</pre>

**Output**:

<pre>variable1 is set
variable2 is not set or unset</pre>

### Cara mengecek variabel kosong atau tidak kosong

Tutorial ini memeriksa pemeriksaan variabel dibandingkan dengan spasi dan membungkus ekspresi ini di dalam `[[]]`.

<pre>variable1=""
if [[ $variable1 = "" ]]
then
  echo 'variable1 is empty'
else
  echo 'variable1 is not empty'
fi</pre>

Hal yang sama juga dapat ditulis menggunakan variabel dalam tanda kutip ganda yang dibungkus dalam tanda kurung tunggal `[]`.

<pre>variable1=""
if [ "$variable1" = "" ]
    then
    echo "variable1 is empty"
else
  echo 'variable1 is not empty'
fi</pre>

**Output**

<pre>variable1 is empty</pre>

Mari kita periksa juga untuk tidak mengosongkan menggunakan! operator.

Berikut adalah kode untuk `example checks if a variable is non-empty`.

SATU ARAH,

<pre>variable1=""
if [[ ! $variable1 = "" ]]
then
  echo 'variable1 is empty'
else
  echo 'variable1 is not empty'
fi</pre>

**Cara Lain**

<pre>variable1=""
if [ ! "$variable1" = "" ]
then
  echo 'variable1 is empty'
else
  echo 'variable1 is not empty'
fi</pre>

Opsi penggunaan -z lainnya untuk memeriksa variabel disetel dan kosong atau tidak kosong menggunakan kode di bawah ini

<pre>variable2=""
variable3="test"

if [ -z "$variable2" ]
then
    echo "variable2 is set and empty"
else
    echo "variable2 is set and nonempty"
fi

if [ -z "$variable3" ]
then
    echo "variable3 is set and empty"
else
    echo "variable3 is set and non-empty"
fi</pre>

**Output**:

<pre>variable2 is set and empty
variable3 is set and non-empty</pre>

## Bash Iterate Nos

Periksa variabel disetel atau tidak disetel kosong atau tidak kosong dengan string kosong atau tidak dalam file skrip bash dan shell

Dalam contoh ini, Hasilkan urutan rentang angka dan simpan dalam variabel.

Terkadang, Kami ingin membuat nama file dengan nama yang berisi angka yang dihasilkan dari urutan atau rentang angka.

### Hasilkan serangkaian angka dalam skrip bash

- menggunakan alat seq seq menghasilkan urutan angka.

<pre>number=4
for k in $(seq 1 $number); do echo $k; done</pre>

**Output**:

<pre>1
2
3
4</pre>

- Mengugunakan Perulanan For

<pre>number=5
for ((k=1;k<=number;k++)); do
    echo $k
done</pre>

**Output**

<pre>1
2
3
4
5</pre>

- Menggunakan While Loop

<pre>
number=5
k=1 ;
while [[ $k -le $number ]] ; do
    echo $k
    ((k = k + 1))
done</pre>

### Kesimpulan

`seq`lebih baik dibandingkan dengan `loop` `for` dan `while`
