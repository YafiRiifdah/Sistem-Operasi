<div align="center">
  <h1 style="text-align: center;font-weight: bold">Pratikum Operasi Input & Output Minggu 4<br>Sistem Operasi</h1>
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

## TUGAS PENDAHULUAN:

## Jawablah pertanyaan-pertanyaan di bawah ini :

1. Apa yang dimaksud redirection?
2. Apa yang dimaksud pipeline?
3. Apa yang dimaksud perintah di bawah ini :
    echo, cat, more, sort, grep, wc, cut, uniq
## Jawaban:
1. <b>Redirection (Pembelokan) :</b> 
Membelokkan strandar output suatu program ke file atau membelokkan standar input suatu program dari suatu file.

2. <b>Pipeline (Pipa):</b>
 Mekanisme pipa digunakan sebagai alat komunikasi antar proses.
 Input => Proses 1 => Output = Input => Proses 2 => Output
Proses 1 menghasilkan output yang selanjutnya digunakan sebagai input oleh Proses 2. Hubungan output input ini dinamakan pipa, yang menghubungkan Proses 1 dengan Proses 2 dan dinyatakan dengan symbol "|".
```
   Proses1 | Proses
```

3. yang dimaksud perintah di bawah ini :
<br><b>echo :</b> Menampilkan text 
<br><b>cat :</b> Melihat isi file 
<br><b>more :</b> Membuka file satu per satu 
<br><b>sort :</b> Digunakan untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter 
<br><b>grep :</b> Digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan.
<br><b>wc :</b> Digunakan untuk menghitung jumlah baris, kata dan karakter dari baris-baris masukan yang diberikan kepadanya. Untuk mengetahui berapa baris gunakan option -1. Untuk mengetahui berapa kata, gunakan option -w dan untuk mengetahui berapa karakter, gunakan option -c. Jika salah satu option tidak digunakan, maka tampilannya adalah jumlah baris, jumlah kata dan jumlah karakter .
<br><b>cut :</b> Digunakan untuk mengambil  kolom tertentu dan baris-baris masukannya, yang ditentukan pada opinion -c 
<br><b>uniq :</b> Digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, biasanya digabungkan dalam pipeline dengan sort.

<br>


## PERCOBAAN:

1. Login sebagai user.
2. Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
3. Selesaikan soal-soal latihan.


## Percobaan 1 : File descriptor

1. Output ke layar (standar output), input dari system (kernel)
    ```
    $ ps
    ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-1.png?raw=true)

2. Output ke layar (standar output), input dari keyboard (standard input)
   ```
    $ cat
    hallo, apa kabar
    hallo, apa kabar
    exit dengan ^d
    exit dengan ^d
    [Ctrl-d]
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-2.png?raw=true)

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
   ```
   $ mkdir mydir
   $ mkdir mydir **(Terdapat pesan error)**
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-3.png?raw=true)

## Percobaan 2 : Pembelokan (redirection)
1. Pembelokan standar output
   ```
    $ cat 1> myfile.txt
    Ini adalah teks yang saya simpan ke file myfile.txt
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-4.png?raw=true)

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
   ```
    $ cat 0< myfile.txt
    $ cat myfile.txt
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-5.png?raw=true)

3. Pembelokan standar error untuk disimpan di file
   ```
    $ mkdir mydir (Terdapat pesan error)
    $ mkdir mydir 2> myerror.txt
    $ cat myerror.txt
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-6.png?raw=true)

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
   ```
    $ ls filebaru (Terdapat pesan error)
    $ ls filebaru 2> out.txt
    $ cat out.txt
    $ ls filebaru 2> out.txt 2>&
    $ cat out.txt
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-7.png?raw=true)

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
   ```
   $ echo “mencoba menulis file” 1> baru
   $ cat filebaru 2> baru 1>&
   $ cat baru
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-8.png?raw=true)

6. Notasi >> (append)
   ```
   $ echo “kata pertama” > surat
   $ echo “kata kedua” >> surat
   $ echo “kata ketiga” >> surat
   $ cat surat
   $ echo “kata keempat” > surat
   $ cat surat
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-9.png?raw=true)

7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
   ```
   $ cat <<++
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   ++
   $ cat <<%%%
   Hallo, apa kabar?
   Baik-baik saja?
   Ok!
   %%%
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-10.png?raw=true)

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
  ```
  $ cat myfile.txt – surat
  ```
  ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-11.png?raw=true)

<br>

## Percobaan 3 : Pipa (pipeline)

1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
   ```
   $ who
   $ who | sort
   $ who | sort –r
   $ who > tmp
   $ sort tmp
   $ rm tmp
   $ ls –l /etc | more
   $ ls –l /etc | sort | more
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-12.png?raw=true)

   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-13.png?raw=true)

   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-14.png?raw=true)

2. Untuk membelokkan standart output ke file, digunakan operator ">"
   ```
   $ echo hello
   $ echo hello > output
   $ cat output
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-15.png?raw=true)

3. Untuk menambahkan output ke file digunakan operator ">>"
   ```
   $ echo bye >> output
   $ cat output
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-16.png?raw=true)

4. Untuk membelokkan standart input digunakan operator "<"
   ```
   $ cat < output
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-17.png?raw=true)

5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
   ```
   $ cat < output > out
   $ cat out
   $ cat < output >> out
   $ cat out
   $ cat < output > output
   $ cat output
   $ cat < out >> out (Proses tidak berhenti)
   [Ctrl-c]
   $ cat out
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-18.png?raw=true)

<br>

## Percobaan 4 : Filter
1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
   ```
    $ w –h | grep <user>
    $ grep <user> /etc/passwd
    $ ls /etc | wc
    $ ls /etc | wc –l
    $ cat > kelas1.txt
    Badu
    Zulkifli
    Yulizir
    Yudi
    Ade
    [Ctrl-d]
    $ cat > kelas2.txt
    Budi
    Gama
    Asep
    Muchlis
    [Ctrl-d]
    $ cat kelas1.txt kelas2.txt | sort
    $ cat kelas1.txt kelas2.txt > kelas.txt
    $ cat kelas.txt | sort | uniq
   ```
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-19.png?raw=true)
   
   ![App Screenshot](https://github.com/daffaerfiansyah/SysOp24-3123500006/blob/main/Minggu%204/Assets/Percobaan/IMG-20.png?raw=true)

<br>

## LATIHAN:

1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output   ke file baru.
2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya.
3. Urutkan file baru dengan cara membelokkan standard input.
4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
6. Urutkan kalimat berikut :
   ```
   Jakarta
   Bandung
   Surabaya
   Padang
   Palembang
   Lampung
   ```
  Dengan menggunakan notasi **here document (<@@@ ...@@@)** . [HINT](https://www.geeksforgeeks.org/how-to-use-here-document-in-bash-programming/)
  

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru.
8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
   ```
    $ cat > hello.txt
    dog cat
    cat duck
    dog chicken
    chicken duck
    chicken cat
    dog duck
    [Ctrl-d]
    $ cat hello.txt | sort | uniq
    $ cat hello.txt | grep “dog” | grep –v “cat”
   ```
## LAPORAN RESMI:

1. Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan tampilannya.
2. Kerjakan latihan diatas dan analisa hasilnya
3. Berikan kesimpulan dari praktikum ini.
