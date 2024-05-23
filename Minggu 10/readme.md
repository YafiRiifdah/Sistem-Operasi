<div align="center">
  <h1 style="text-align: center;font-weight: bold">Praktikum 10<br>Praktek Sistem Operasi</h1>
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

<div align="center">
  <h1 class="text-align: center;font-weight: bold">Praktikum 10<br>Sistem Operasi</h1>
  <h3 class="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
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
- [Esai Threads](#threads)
    - [Multithreading Models](#MultithreadingModels)
    - [Multicore Programming](#Multicoreprogramming)
    - [Thread Libraries](#Threadlibraries)
    - [Implicit Threading](#Implicittreading)
    - [Threading Issues](#Threadingissues)
    - [Operating System Examples](#Threadingissues)
- [Soal dan Jawaban Seputar Materi Threads](#soaldanjawaban)
- [Referensi](#referensi)

## Threads

### Multithread Server Architecture 

![App Screenshot](image/1.png)

#### Benefits

- Responsivenessx
    - Multithreading dalam aplikasi interaktif memungkinkan suatu program untuk terus berjalan meskipun sebagian dari program tersebut diblokir atau menjalankan operasi yang panjang, sehingga meningkatkan daya tanggap terhadap pengguna. Dalam lingkungan non multi-thread, server mendengarkan port untuk beberapa permintaan dan ketika permintaan itu datang, server memproses permintaan tersebut dan kemudian melanjutkan mendengarkan permintaan lain. Waktu yang dibutuhkan saat memproses permintaan membuat pengguna lain tidak perlu menunggu
- Resource Sharing
    - thread berbagi sumber daya proses, lebih mudah daripada memori bersama atau pengiriman pesan
    - proses dapat berbagi resources hanya melalui teknik seperti
        - Message passing
        - shared memory
    
        - Teknik-teknik tersebut harus diatur secara eksplisit oleh programmer. Namun, thread berbagi memori dan sumber daya dari proses yang menjadi miliknya secara default. Manfaat berbagi kode dan data adalah memungkinkan aplikasi memiliki beberapa rangkaian aktivitas dalam ruang alamat yang sama
- Economy
    - lebih murah daripada pembuatan proses, pergantian thread lebih rendah overhead daripada context switch
    - mengalokasikan memory dan resources untuk pembuatan proses itu adalah pekerjaan yang mahal dalam segi waktu dan ruang, sehingga lebih murah dan ekonomis untuk membuat dan context switch threads.
- Scalability
    - proses dapat memanfaatkan arsitektur multiprosesor
    - Proses single threaded hanya dapat berjalan pada satu prosesor terlepas dari berapa banyak prosesor yang tersedia. Multi-threading pada multiple CPU meningkatkan paralelisme.

### Multicore Programming

**Multicore** atau sistem **multiprocessor** memberikan tekanan pada pemrogram, tantangannya meliputi:

- Multicore atau multiprosesor menambahkan tantangan baru seperti:

- Dividing Activities: Memecah tugas-tugas menjadi bagian-bagian yang dapat berjalan secara paralel.
Balance: Menjaga keseimbangan beban kerja di antara core-core.
- Data Splitting: Memisahkan data sehingga dapat diproses secara paralel.
- Data Dependency: Mengelola ketergantungan data antar thread.
- Testing and Debugging: Menguji dan debugging program yang berjalan secara paralel lebih kompleks.

    Ketika berbagai sub-tugas yang lebih kecil sedang dieksekusi secara paralel, maka pengujian dan debugging pada tugas-tugas konkuren seperti itu lebih sulit daripada pengujian dan debugging aplikasi berbasis single threaded.

***Parallelism*** menyiratkan suatu sistem dapat melakukan lebih dari satu tugas secara bersamaan

### Amdahl Law

Rumus Hukum Amdahl adalah rumus yang dapat digunakan untuk menentukan peningkatan kecepatan maksimum yang dapat dicapai sistem hanya dengan meningkatkan komponen tertentu. Misalnya, peningkatan kinerja keseluruhan sistem dengan prosesor yang lebih cepat akan dibatasi oleh kecepatan RAM, sehingga peningkatan kinerja keseluruhan sistem akan dibatasi oleh komponen sistem yang tidak ditingkatkan.

Dalam rumus ini, "Waktu Total" adalah jumlah waktu yang diperlukan untuk menyelesaikan seluruh tugas, dan "Waktu yang Tidak Dapat Ditingkatkan" adalah jumlah waktu yang diperlukan untuk menyelesaikan bagian sistem yang tidak dapat ditingkatkan.

Hukum Amdahl sangat membantu dalam memahami kendala kinerja sistem. Anda dapat menggunakannya untuk membuat keputusan tentang metode terbaik untuk meningkatkan kinerja sistem.

### User Threads dan Kernel Threads

**User threads** -adalah threads yang dikelola oleh pustaka (library) dalam ruang pengguna (user space). Mereka tidak memerlukan dukungan dari kernel untuk manajemen threads.
Tiga library thread utama:

Karakteristik utama User Threads:

- Pembuatan dan Manajemen Cepat: Karena manajemen dilakukan di ruang pengguna, pembuatan, penghancuran, dan penjadwalan threads biasanya lebih cepat dan tidak melibatkan overhead dari panggilan sistem ke kernel.

- Tidak Diketahui oleh Kernel: Kernel tidak mengetahui tentang user threads. Kernel hanya mengelola satu konteks eksekusi untuk setiap proses, terlepas dari berapa banyak user threads yang mungkin berjalan dalam proses itu.

- Non-preemptive Scheduling: Penjadwalan user threads biasanya non-preemptive, artinya sebuah thread harus menyerahkan kontrol secara eksplisit agar thread lain bisa berjalan.

- Platform Independence: User threads bisa diimplementasikan pada sistem operasi yang berbeda tanpa mengandalkan fitur spesifik dari kernel.

**Kernel threads** - Kernel Threads adalah threads yang dikelola secara langsung oleh kernel sistem operasi. Setiap kernel thread diketahui dan diatur oleh kernel.

Karakteristik utama Kernel Threads:

- Preemptive Scheduling: Kernel dapat melakukan penjadwalan preemptive pada kernel threads, memungkinkan satu thread untuk dihentikan sementara dan thread lain dijalankan.

- Penjadwalan oleh Kernel: Kernel mengelola penjadwalan dan pengelolaan semua kernel threads. Ini berarti kernel memiliki kendali penuh atas penggunaan CPU oleh threads.

- Dukungan untuk Multiprocessing: Kernel threads dapat memanfaatkan prosesor multipel karena kernel dapat menjadwalkan threads untuk berjalan secara paralel pada prosesor yang berbeda.

| **Karakteristik**               | **User Threads**                                                                                          | **Kernel Threads**                                                                                         |
|---------------------------------|------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Manajemen**                   | Dilakukan di ruang pengguna (user space) melalui pustaka/thread library.                                    | Dilakukan oleh kernel sistem operasi.                                                                       |
| **Pengetahuan Kernel**          | Kernel tidak mengetahui keberadaan user threads.                                                           | Kernel mengetahui dan mengelola kernel threads.                                                             |
| **Penjadwalan (Scheduling)**    | Non-preemptive, dilakukan oleh pustaka threads; thread harus menyerahkan kontrol secara eksplisit.         | Preemptive, dilakukan oleh kernel; kernel dapat menghentikan sementara thread dan menjalankan thread lain.  |
| **Pembuatan dan Penghancuran**  | Cepat, karena tidak memerlukan panggilan sistem (system call).                                              | Lebih lambat, karena melibatkan panggilan sistem dan manajemen oleh kernel.                                  |
| **Operasi Blocking**            | Jika satu thread terblokir, semua threads dalam proses tersebut juga terblokir.                             | Hanya thread yang terblokir yang berhenti; thread lain dapat terus berjalan.                                 |
| **Dukungan Multiprocessing**    | Tidak bisa memanfaatkan prosesor multipel secara efisien karena semua user threads dipetakan ke satu kernel thread. | Dapat memanfaatkan prosesor multipel dengan baik karena kernel dapat menjadwalkan thread pada prosesor berbeda. |
| **Portabilitas**                | Lebih portabel, dapat diimplementasikan tanpa dukungan spesifik dari kernel.                                | Kurang portabel, tergantung pada dukungan dari sistem operasi tertentu.                                      |
| **Overhead**                    | Rendah, karena manajemen dilakukan di ruang pengguna tanpa panggilan ke kernel.                             | Lebih tinggi, karena melibatkan interaksi dengan kernel dan konteks switching yang lebih berat.             |
| **Penggunaan**                  | Cocok untuk aplikasi yang membutuhkan manajemen threads cepat dan tidak banyak operasi blocking.            | Cocok untuk aplikasi yang membutuhkan penanganan operasi blocking yang baik dan penggunaan multiprosesor.   |


### Multithreading Models

1. Many-to-One
2. One-to-One
3. Many-to-Many

#### Many-to-One
![App Screenshot](image/2.png)

Many-to-One adalah salah satu model pemetaan thread di mana banyak user threads dipetakan ke satu kernel thread. Model ini memiliki beberapa karakteristik khusus yang membedakannya dari model pemetaan thread lainnya.

#### Deskripsi
- **User Threads ke Kernel Thread**: Dalam model ini, beberapa user threads di dalam suatu proses dipetakan ke satu kernel thread tunggal. Kernel hanya melihat satu thread yang mewakili seluruh proses, meskipun banyak user threads berjalan di ruang pengguna.
- **Pustaka Threads**: Manajemen user threads dilakukan oleh pustaka threads di ruang pengguna tanpa intervensi langsung dari kernel.

#### Karakteristik Utama
1. **Penjadwalan (Scheduling)**:
   - Penjadwalan user threads dilakukan sepenuhnya oleh pustaka threads di ruang pengguna.
   - Kernel hanya menjadwalkan satu kernel thread yang mewakili seluruh proses.

2. **Operasi Blocking**:
   - Jika satu user thread melakukan operasi blocking (misalnya, melakukan I/O yang memblokir), seluruh proses akan terblokir karena kernel hanya mengenali satu kernel thread.
   - Hal ini dapat mengurangi efisiensi dalam menangani operasi blocking.

3. **Kinerja**:
   - Manajemen user threads sangat cepat karena tidak memerlukan panggilan sistem (system call) ke kernel.
   - Pembuatan, penghancuran, dan switching antara user threads dapat dilakukan dengan overhead yang sangat rendah.

4. **Dukungan Multiprocessing**:
   - Tidak dapat memanfaatkan prosesor multipel secara efisien karena kernel hanya melihat satu thread per proses. Semua user threads dalam proses tersebut akan berjalan pada satu prosesor saja.

5. **Portabilitas**:
   - Model ini sangat portabel karena dapat diimplementasikan di berbagai sistem operasi tanpa memerlukan dukungan khusus dari kernel.

#### Keuntungan
- **Cepat dan Efisien**: Karena semua operasi thread dilakukan di ruang pengguna tanpa perlu panggilan sistem ke kernel, operasi seperti pembuatan dan switching thread sangat cepat.
- **Portabilitas Tinggi**: Tidak tergantung pada dukungan thread dari kernel, sehingga dapat digunakan di banyak platform yang berbeda.

#### Kelemahan
- **Operasi Blocking**: Satu thread yang terblokir dapat memblokir seluruh proses, menghambat kinerja aplikasi yang membutuhkan banyak operasi I/O atau operasi blocking lainnya.
- **Utilisasi Prosesor**: Tidak dapat memanfaatkan prosesor multipel karena semua threads dalam satu proses akan berjalan pada satu prosesor yang sama.

#### Contoh Implementasi
- **Green Threads**: Contoh terkenal dari model many-to-one adalah Green Threads yang digunakan di beberapa implementasi awal bahasa pemrograman Java. Green Threads adalah implementasi user threads di mana semua threads dijalankan oleh satu kernel thread.


#### One-to-One Model
![App Scrennshot](image/3.jpg)
### Deskripsi
- **User Threads ke Kernel Threads**: Dalam model ini, setiap user thread dipetakan ke satu kernel thread. Kernel mengetahui dan mengelola setiap thread yang dibuat oleh aplikasi.
- **Manajemen oleh Kernel**: Kernel bertanggung jawab untuk penjadwalan dan manajemen semua threads, baik user threads maupun kernel threads.

#### Karakteristik Utama
1. **Penjadwalan (Scheduling)**:
   - Penjadwalan dilakukan oleh kernel, memungkinkan penjadwalan preemptive di mana kernel dapat menghentikan sementara satu thread dan menjalankan thread lain.

2. **Operasi Blocking**:
   - Jika satu thread terblokir, kernel dapat menjadwalkan thread lain dalam proses tersebut untuk berjalan, sehingga tidak menghambat keseluruhan proses.

3. **Kinerja**:
   - Pembuatan dan pengelolaan threads memerlukan panggilan sistem (system calls) yang dapat meningkatkan overhead dibandingkan dengan user threads.
   - Switching antara threads lebih berat dibandingkan dengan user threads karena melibatkan switching konteks di tingkat kernel.

4. **Dukungan Multiprocessing**:
   - Dapat memanfaatkan prosesor multipel dengan baik karena kernel dapat menjadwalkan threads pada prosesor yang berbeda, memungkinkan eksekusi paralel yang efektif.

5. **Portabilitas**:
   - Kurang portabel dibandingkan user threads karena memerlukan dukungan dari sistem operasi yang mendukung kernel threads.

#### Keuntungan
- **Penanganan Blocking yang Baik**: Karena kernel dapat menjadwalkan thread lain saat satu thread terblokir, model ini lebih efisien dalam menangani operasi blocking.
- **Utilisasi Prosesor yang Efisien**: Dapat memanfaatkan prosesor multipel dengan baik, meningkatkan kinerja aplikasi pada sistem multiprosesor.

#### Kelemahan
- **Overhead Lebih Tinggi**: Pembuatan, penghancuran, dan switching threads melibatkan panggilan sistem dan konteks switching di tingkat kernel, yang dapat meningkatkan overhead.
- **Ketergantungan pada Sistem Operasi**: Memerlukan dukungan dari kernel, sehingga kurang portabel dibandingkan dengan user threads.

#### Contoh Implementasi
- **POSIX Threads (pthreads)**: Banyak implementasi POSIX threads menggunakan model one-to-one, di mana setiap pthread dipetakan ke kernel thread.



#### Many-to-Many Model
![App Screenshot](image/4.jpg)

#### Deskripsi
- **User Threads ke Kernel Threads**: Dalam model ini, banyak user threads dipetakan ke banyak kernel threads. Tidak ada pemetaan satu-ke-satu yang ketat; sebaliknya, ada fleksibilitas dalam bagaimana user threads dipetakan ke kernel threads.
- **Manajemen Campuran**: Manajemen thread dilakukan baik di ruang pengguna (untuk user threads) maupun di tingkat kernel (untuk kernel threads).

#### Karakteristik Utama
1. **Penjadwalan (Scheduling)**:
   - Penjadwalan user threads dilakukan di ruang pengguna, sementara kernel mengelola penjadwalan kernel threads.
   - User threads dapat dijadwalkan secara fleksibel ke kernel threads yang tersedia, memungkinkan efisiensi yang lebih tinggi.

2. **Operasi Blocking**:
   - Jika satu user thread terblokir, kernel dapat menjadwalkan user thread lain pada kernel thread yang berbeda, sehingga tidak menghambat keseluruhan proses.
   - Kombinasi ini memungkinkan penanganan blocking yang lebih efisien dibandingkan dengan model many-to-one.

3. **Kinerja**:
   - Manajemen user threads cepat karena banyak operasi dapat dilakukan tanpa panggilan sistem.
   - Overhead lebih rendah dibandingkan dengan model one-to-one karena tidak setiap user thread membutuhkan kernel thread sendiri.

4. **Dukungan Multiprocessing**:
   - Dapat memanfaatkan prosesor multipel dengan baik karena kernel threads dapat dijadwalkan pada prosesor yang berbeda.
   - User threads dapat dieksekusi secara paralel pada berbagai kernel threads.

5. **Portabilitas**:
   - Lebih portabel dibandingkan dengan model one-to-one, namun masih memerlukan dukungan dari sistem operasi untuk kernel threads.

#### Keuntungan
- **Fleksibilitas Tinggi**: Kombinasi manajemen user threads dan kernel threads memberikan fleksibilitas tinggi dalam penjadwalan dan manajemen threads.
- **Penanganan Blocking yang Baik**: Kemampuan kernel untuk menjadwalkan user threads lain saat satu thread terblokir meningkatkan efisiensi.
- **Utilisasi Prosesor yang Efisien**: Dapat memanfaatkan prosesor multipel secara efektif, memungkinkan eksekusi paralel yang optimal.

#### Kelemahan
- **Kompleksitas Manajemen**: Model ini lebih kompleks untuk diimplementasikan dan dikelola dibandingkan dengan model lainnya.
- **Ketergantungan pada Sistem Operasi**: Masih memerlukan dukungan dari sistem operasi untuk kernel threads, meskipun lebih fleksibel dibandingkan dengan model one-to-one.

#### Contoh Implementasi
- **Modern Implementations of POSIX Threads**: Beberapa implementasi modern dari POSIX threads menggunakan pendekatan many-to-many untuk memanfaatkan fleksibilitas dan efisiensi yang ditawarkan oleh model ini.

### Threads Library

#### Deskripsi

- **Apa itu Threads Library?**: Threads library adalah kumpulan fungsi dan rutinitas yang memungkinkan pengembang membuat, mengelola, dan mensinkronisasi threads dalam aplikasi. Library ini menyediakan abstraksi yang memudahkan pengelolaan threading di ruang pengguna tanpa perlu berinteraksi langsung dengan kernel.

#### Fungsi Utama
1. **Pembuatan Thread (Thread Creation)**:
   - Fungsi untuk membuat thread baru, yang menjalankan fungsi atau rutinitas tertentu secara paralel dengan thread utama dan threads lainnya dalam aplikasi.

2. **Sinkronisasi Thread (Thread Synchronization)**:
   - Fungsi untuk mengelola akses ke sumber daya bersama antara threads, seperti mutexes (mutual exclusions), semaphores, dan barriers, untuk mencegah kondisi balapan (race conditions) dan deadlocks.

3. **Penjadwalan Thread (Thread Scheduling)**:
   - Fungsi untuk mengatur kapan dan dalam urutan apa threads dijalankan. Ini bisa melibatkan penundaan eksekusi thread (sleep), menunggu thread lain selesai (join), dan mekanisme lainnya untuk koordinasi antar threads.

4. **Manajemen Thread (Thread Management)**:
   - Fungsi untuk mengatur properti threads, seperti prioritas, afinitas CPU, dan penghancuran thread saat tidak lagi diperlukan.

#### Contoh Threads Library

1. **POSIX Threads (pthreads)**:
   - **Deskripsi**: Implementasi threading yang mengikuti standar POSIX (Portable Operating System Interface). Pthreads menyediakan API yang kaya untuk pembuatan, sinkronisasi, dan manajemen threads.
   - **Penggunaan**:
     ```c
     #include <pthread.h>

     void* myThreadFunction(void* arg) {
         // Do something in thread
         return NULL;
     }

     int main() {
         pthread_t thread;
         pthread_create(&thread, NULL, myThreadFunction, NULL);
         pthread_join(thread, NULL);
         return 0;
     }
     ```

2. **Java Threads**:
   - **Deskripsi**: Java memiliki dukungan bawaan untuk threading melalui kelas `Thread` dan interface `Runnable`. Manajemen threads di Java dilakukan sepenuhnya di level bahasa, memudahkan pengembangan aplikasi multithreading.
   - **Penggunaan**:
     ```java
     public class MyThread extends Thread {
         public void run() {
             // Do something in thread
         }
     }

     public class Main {
         public static void main(String[] args) {
             MyThread thread = new MyThread();
             thread.start();
             try {
                 thread.join();
             } catch (InterruptedException e) {
                 e.printStackTrace();
             }
         }
     }
     ```

3. **Python Threads**:
   - **Deskripsi**: Python menyediakan modul `threading` yang memungkinkan pembuatan dan manajemen threads dalam aplikasi Python.
   - **Penggunaan**:
     ```python
     import threading

     def my_thread_function():
         # Do something in thread
         pass

     thread = threading.Thread(target=my_thread_function)
     thread.start()
     thread.join()
     ```

#### Keuntungan
- **Paralelisme**: Memungkinkan eksekusi paralel dari beberapa tugas, meningkatkan efisiensi dan kinerja aplikasi.
- **Responsivitas**: Membantu menjaga responsivitas aplikasi, terutama dalam aplikasi GUI atau server yang menangani banyak klien secara bersamaan.
- **Utilisasi Prosesor**: Memanfaatkan kemampuan multiprosesor dan multicore untuk eksekusi yang lebih cepat dan efisien.

#### Kelemahan
- **Kompleksitas**: Menambahkan kompleksitas ke dalam program, membuat debugging dan pengujian lebih sulit.
- **Kondisi Balapan**: Risiko kondisi balapan, deadlocks, dan masalah sinkronisasi lainnya yang memerlukan penanganan hati-hati.
- **Overhead**: Pembuatan dan manajemen threads menambah overhead ke dalam aplikasi, yang bisa mempengaruhi kinerja jika tidak dikelola dengan baik.

### POSIX Threads (pthreads)

#### Deskripsi
- **Apa itu POSIX Threads (pthreads)?**: POSIX Threads atau pthreads adalah sebuah standar untuk threading yang ditetapkan oleh POSIX (Portable Operating System Interface). Pthreads menyediakan antarmuka pemrograman yang memungkinkan pengembang untuk membuat dan mengelola threads, serta melakukan sinkronisasi antar threads dalam aplikasi.

#### Fungsi Utama
1. **Pembuatan Thread (Thread Creation)**:
   - `pthread_create`: Membuat thread baru yang menjalankan fungsi tertentu secara paralel dengan thread lain dalam proses.

2. **Sinkronisasi Thread (Thread Synchronization)**:
   - `pthread_mutex_init`, `pthread_mutex_lock`, `pthread_mutex_unlock`: Mengelola mutexes untuk melindungi akses ke sumber daya bersama.
   - `pthread_cond_wait`, `pthread_cond_signal`: Mengelola kondisi variabel untuk sinkronisasi yang lebih kompleks antara threads.

3. **Penjadwalan Thread (Thread Scheduling)**:
   - `pthread_join`: Menunggu thread lain selesai sebelum melanjutkan eksekusi.
   - `pthread_detach`: Menandai thread untuk pembersihan otomatis setelah selesai eksekusi.

4. **Manajemen Thread (Thread Management)**:
   - `pthread_attr_init`, `pthread_attr_setdetachstate`: Mengatur atribut threads, seperti status detach dan prioritas.

#### Contoh Penggunaan
Berikut adalah contoh sederhana penggunaan pthreads dalam bahasa C:

```c
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

void* myThreadFunction(void* arg) {
    printf("Hello from thread!\n");
    return NULL;
}

int main() {
    pthread_t thread;
    int result;

    // Membuat thread baru
    result = pthread_create(&thread, NULL, myThreadFunction, NULL);
    if (result) {
        printf("Error creating thread: %d\n", result);
        exit(-1);
    }

    // Menunggu thread selesai
    result = pthread_join(thread, NULL);
    if (result) {
        printf("Error joining thread: %d\n", result);
        exit(-1);
    }

    printf("Thread has finished executing.\n");
    return 0;
}
```


### Java Threads

#### Deskripsi
- **Apa itu Java Threads?**: Java Threads adalah mekanisme threading bawaan dalam bahasa pemrograman Java yang memungkinkan pengembang membuat, mengelola, dan menyinkronkan threads dalam aplikasi. Java menyediakan dukungan threading melalui kelas `Thread` dan interface `Runnable`.

### Fungsi Utama
1. **Pembuatan Thread (Thread Creation)**:
   - **Menggunakan Kelas `Thread`**: Membuat subclass dari `Thread` dan mengoverride metode `run`.
   - **Menggunakan Interface `Runnable`**: Mengimplementasikan interface `Runnable` dan menjalankan objek yang dihasilkan dalam sebuah `Thread`.

2. **Sinkronisasi Thread (Thread Synchronization)**:
   - **Synchronized Methods**: Metode yang disinkronkan menggunakan kata kunci `synchronized` untuk mengamankan akses ke sumber daya bersama.
   - **Synchronized Blocks**: Blok kode yang disinkronkan menggunakan kata kunci `synchronized` untuk mengamankan akses ke objek tertentu.
   - **Wait and Notify**: Metode `wait()`, `notify()`, dan `notifyAll()` digunakan untuk komunikasi antar threads.

3. **Penjadwalan Thread (Thread Scheduling)**:
   - **Metode `join`**: Menunggu thread lain selesai sebelum melanjutkan eksekusi.
   - **Metode `sleep`**: Menunda eksekusi thread untuk waktu tertentu.
   - **Metode `yield`**: Memberikan kesempatan kepada threads lain untuk dieksekusi.

4. **Manajemen Thread (Thread Management)**:
   - **Set and Get Thread Priority**: Mengatur dan mendapatkan prioritas thread menggunakan metode `setPriority` dan `getPriority`.
   - **Set and Check Daemon Status**: Menandai thread sebagai daemon menggunakan metode `setDaemon`.

#### Contoh Penggunaan
Berikut adalah contoh sederhana penggunaan threading dalam Java:

#### Menggunakan Kelas `Thread`
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Hello from thread!");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start();
        try {
            thread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Thread has finished executing.");
    }
}

```

#### Menggunakan Interface `Runnable`

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Hello from thread!");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start();
        try {
            thread.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("Thread has finished executing.");
    }
}
```
### Implicit Threading

#### Deskripsi
- **Apa itu Implicit Threading?**: Implicit Threading adalah model pemrograman dimana sistem secara otomatis mengelola dan memanfaatkan threads tanpa perlu intervensi langsung dari pengembang. Dalam model ini, pengembang mengimplementasikan kode yang bersifat paralel atau bisa dieksekusi secara paralel, dan sistem secara otomatis menangani pembuatan, penjadwalan, dan manajemen threads untuk eksekusi paralel.

#### Karakteristik Utama
1. **Otomatis**: Threads secara otomatis dibuat, dijadwalkan, dan dimanajemen oleh sistem operasi atau lingkungan runtime, tanpa perlu intervensi langsung dari pengembang.
2. **Transparansi**: Pengembang tidak perlu memiliki pengetahuan mendalam tentang mekanisme threading, karena threading dilakukan secara transparan di latar belakang.
3. **Kemudahan Penggunaan**: Model ini dapat meningkatkan kemudahan penggunaan karena pengembang tidak perlu mengelola secara eksplisit pembuatan dan penjadwalan threads.
4. **Efisiensi**: Implicit threading dapat meningkatkan efisiensi dalam eksekusi aplikasi yang bersifat paralel karena sistem dapat mengoptimalkan penggunaan sumber daya secara dinamis.

#### Contoh Implementasi
1. **Vectorization in MATLAB**: MATLAB menerapkan implicit threading melalui vektorisasi, di mana operasi matematika pada vektor dan matriks secara otomatis diterapkan pada semua elemen secara paralel tanpa intervensi pengguna.
2. **OpenMP in C/C++**: OpenMP adalah sebuah API yang memungkinkan implementasi paralelisme secara implisit dalam program C/C++ dengan menambahkan direktif pragma ke kode sumber. Sistem kompilasi kemudian secara otomatis membuat dan mengelola threads sesuai dengan direktif tersebut.

#### Keuntungan
- **Kemudahan Penggunaan**: Menghilangkan kompleksitas manajemen threads, membuatnya lebih mudah bagi pengembang untuk membuat aplikasi paralel.
- **Transparansi**: Pengembang tidak perlu memiliki pengetahuan mendalam tentang threading, karena threading dilakukan secara transparan di latar belakang.
- **Efisiensi**: Dapat meningkatkan efisiensi dalam eksekusi aplikasi yang bersifat paralel karena sistem dapat mengoptimalkan penggunaan sumber daya secara dinamis.

#### Kelemahan
- **Kontrol yang Terbatas**: Pengembang mungkin kehilangan beberapa tingkat kontrol atas manajemen threads dan penjadwalan.
- **Ketergantungan pada Implementasi**: Implicit threading bergantung pada implementasi sistem atau lingkungan runtime, yang bisa berbeda-beda dalam tingkat efisiensi dan kinerja.

### Thread Pools

#### Deskripsi
- **Apa itu Thread Pools?**: Thread pools adalah kumpulan thread yang siap digunakan untuk menangani tugas-tugas tertentu dalam sebuah aplikasi. Thread pools memungkinkan pengembang untuk mengontrol jumlah thread yang dibuat dan dielola secara efisien, serta mengurangi overhead yang terkait dengan pembuatan dan penghancuran thread berulang-ulang.

#### Fungsi Utama
1. **Pembuatan Thread Pool (Thread Pool Creation)**:
   - Membuat thread pool dengan jumlah thread yang tetap sebelum aplikasi dimulai atau ketika diperlukan.
   - Menyediakan antarmuka untuk menambahkan tugas ke dalam antrian thread pool.

2. **Manajemen Thread Pool (Thread Pool Management)**:
   - Mengelola siklus hidup thread dalam pool, seperti pembuatan, penundaan, dan penghentian thread.
   - Mengoptimalkan penggunaan sumber daya dengan menentukan jumlah thread yang sesuai untuk menangani beban kerja tertentu.

3. **Penjadwalan Tugas (Task Scheduling)**:
   - Menjadwalkan tugas-tugas yang masuk ke dalam thread pool untuk dieksekusi oleh thread yang tersedia.
   - Memastikan bahwa tugas-tugas diproses secara paralel atau secara berurutan sesuai kebutuhan aplikasi.

4. **Penanganan Kesalahan (Error Handling)**:
   - Mengelola penanganan kesalahan yang terjadi selama eksekusi tugas, seperti menangkap dan melaporkan kesalahan agar dapat ditangani dengan benar.

#### Keuntungan
- **Efisiensi**: Mengurangi overhead yang terkait dengan pembuatan dan penghancuran thread dengan menggunakan thread yang sudah ada dalam pool.
- **Skalabilitas**: Memungkinkan aplikasi untuk menangani beban kerja yang berubah-ubah dengan mengatur jumlah thread dalam pool secara dinamis.
- **Kemudahan Penggunaan**: Menyediakan antarmuka yang mudah digunakan untuk menambahkan tugas ke dalam antrian thread pool tanpa perlu mengelola thread secara eksplisit.

#### Kelemahan
- **Pemilihan Jumlah Thread yang Tepat**: Memilih jumlah thread yang tepat untuk thread pool bisa menjadi tantangan, karena terlalu sedikit dapat menyebabkan penundaan dalam pemrosesan tugas, sedangkan terlalu banyak dapat menyebabkan overhead dan penggunaan sumber daya yang berlebihan.
- **Potensi Kebuntuan (Deadlocks)**: Deadlocks dapat terjadi jika ada tugas yang saling bergantung satu sama lain dan menunggu hasil dari tugas lainnya dalam thread pool.

#### Contoh Implementasi
1. **Java Executor Framework**: Java menyediakan Executor Framework yang merupakan implementasi dari thread pools. Pengembang dapat menggunakan kelas-kelas seperti `ExecutorService` dan `ThreadPoolExecutor` untuk membuat dan mengelola thread pools dalam aplikasi Java.


### OpenMP

#### Deskripsi
- **Apa itu OpenMP?**: OpenMP (Open Multi-Processing) adalah sebuah API (Application Programming Interface) yang memungkinkan pengembang untuk menambahkan paralelisme ke dalam aplikasi mereka dengan menggunakan model pemrograman shared memory multiprocessing. OpenMP menyediakan direktif pragma yang dapat disisipkan ke dalam kode sumber C, C++, dan Fortran untuk mendefinisikan bagian-bagian dari kode yang dapat dieksekusi secara paralel.

#### Fungsi Utama
1. **Paralelisme Loop**: Memungkinkan loop iteratif untuk dieksekusi secara paralel dengan menggunakan direktif pragma seperti `#pragma omp parallel for`.
2. **Paralelisme Task**: Memungkinkan tugas-tugas independen untuk dieksekusi secara paralel dengan menggunakan direktif pragma seperti `#pragma omp parallel sections`.
3. **Synchronization**: Menyediakan berbagai mekanisme sinkronisasi, seperti `critical`, `atomic`, `barrier`, dan `flush`, untuk menghindari kondisi balapan (race conditions) dan deadlock antar threads.
4. **Variabel Lingkungan**: Memungkinkan pengaturan variabel lingkungan OpenMP, seperti jumlah thread dan mode dinamis atau statis, untuk mengontrol perilaku paralelisme.

#### Keuntungan
- **Sederhana**: Mudah diimplementasikan karena menggunakan direktif pragma yang dapat disisipkan ke dalam kode sumber yang sudah ada.
- **Portabel**: Dapat digunakan pada berbagai platform dan arsitektur hardware yang mendukung OpenMP.
- **Efisien**: Mengurangi kompleksitas dan overhead yang terkait dengan pengelolaan threads secara manual.

### Contoh Penggunaan
#### C/C++
```c
#include <omp.h>
#include <stdio.h>

int main() {
    #pragma omp parallel
    {
        int thread_id = omp_get_thread_num();
        printf("Hello, world! from thread %d\n", thread_id);
    }
    return 0;
}
```

### Grand Central Dispatch (GCD)

#### Deskripsi
- **Apa itu Grand Central Dispatch (GCD)?**: Grand Central Dispatch (GCD) adalah sebuah framework yang dikembangkan oleh Apple untuk mengelola konkurensi pada platform macOS, iOS, dan watchOS. GCD memungkinkan pengembang untuk menangani tugas-tugas paralel dan asynchronous dengan mudah, tanpa perlu mengelola secara langsung pembuatan dan penjadwalan threads.

#### Fungsi Utama
1. **Dispatch Queues**: GCD mengelola eksekusi tugas-tugas dalam dispatch queues, yang dapat bersifat serial atau concurrent.
2. **Dispatch Groups**: Mengelompokkan beberapa tugas dalam satu dispatch group untuk menunggu selesai bersama-sama.
3. **Semaphores**: Menyediakan mekanisme semaphores untuk sinkronisasi tugas-tugas yang berjalan secara asynchronous.
4. **Dispatch Sources**: Mengamati kejadian-kejadian seperti perubahan file, timer, atau koneksi jaringan, dan mengeksekusi tugas-tugas terkait saat kejadian tersebut terjadi.

#### Keuntungan
- **Sederhana**: Memiliki antarmuka yang sederhana dan mudah digunakan.
- **Efisien**: Mengelola sumber daya threads secara otomatis, sehingga mengurangi overhead yang terkait dengan manajemen threads secara manual.
- **Portabel**: Dapat digunakan pada berbagai platform yang didukung oleh Apple, termasuk macOS, iOS, dan watchOS.

#### Contoh Penggunaan
#### Objective-C

```objective-c
dispatch_queue_t queue = dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0);
dispatch_async(queue, ^{
    // Tugas yang dieksekusi secara asynchronous
    NSLog(@"Hello from background thread!");
    dispatch_async(dispatch_get_main_queue(), ^{
        // Update UI di main thread
        NSLog(@"Updating UI in main thread");
    });
});
```

### Threading Issues

#### Definisi
**Threading issues** adalah masalah-masalah yang muncul ketika mengembangkan atau menggunakan aplikasi yang menggunakan multiple threads atau threads concurrency. Dalam lingkungan multithreading, ada beberapa masalah yang umumnya dihadapi oleh pengembang.

#### Masalah Umum Threading
1. **Race Conditions**: Terjadi ketika dua atau lebih threads mencoba untuk mengakses dan memodifikasi data bersama pada saat yang sama tanpa sinkronisasi yang memadai. Hal ini dapat mengakibatkan hasil yang tidak terduga atau tidak konsisten.
   
2. **Deadlocks**: Terjadi ketika dua atau lebih threads saling menunggu satu sama lain untuk melepaskan sumber daya yang mereka miliki. Kondisi ini dapat membuat semua threads terjebak dalam siklus tunggu tak terbatas dan tidak ada yang dapat melanjutkan eksekusi.

3. **Starvation**: Terjadi ketika satu atau beberapa threads dalam sistem tidak dapat mendapatkan akses ke sumber daya atau pemrosesan CPU karena terus menerus dikalahkan oleh threads lain yang lebih prioritas atau lebih sering mendapatkan akses ke sumber daya tersebut.

4. **Priority Inversion**: Terjadi ketika sebuah thread dengan prioritas rendah mendapatkan akses ke sumber daya yang dibutuhkan oleh thread dengan prioritas tinggi, sehingga menyebabkan penundaan tidak wajar dalam eksekusi thread dengan prioritas tinggi.

5. **Data Races**: Terjadi ketika dua atau lebih threads mengakses dan memodifikasi variabel bersama tanpa pengamanan yang memadai, yang dapat mengakibatkan hasil yang tidak terduga atau tidak konsisten.

6. **Memory Consistency Errors**: Terjadi ketika perubahan yang dilakukan oleh satu thread terlihat oleh thread lain dalam urutan yang tidak diinginkan atau sebaliknya. Hal ini dapat menyebabkan perilaku yang tidak terduga atau tidak konsisten dalam aplikasi.

#### Penanganan Threading Issues
Untuk mengatasi masalah threading, pengembang dapat menggunakan teknik sinkronisasi seperti mutexes, semaphores, dan locks, serta mengikuti praktik pengembangan yang baik seperti desain thread-safe dan menghindari pembagian data bersama antara threads sebanyak mungkin. Memahami dan mengelola threading issues dengan baik adalah kunci untuk mengembangkan aplikasi yang stabil, responsif, dan dapat diandalkan dalam lingkungan multithreading.


#### Signal Handling

- Sinyal **signal** digunakan pada sistem UNIX untuk memberitahukan suatu proses bahwa suatu peristiwa tertentu telah terjadi.
- Sebuah **penangan sinyal** digunakan untuk memproses sinyal
    - Sinyal dihasilkan oleh suatu peristiwa tertentu
    - Sinyal dikirimkan ke sebuah proses
    - Sinyal ditangani oleh salah satu dari dua penangan sinyal:
        - Default
        - Ditentukan pengguna
- Setiap sinyal memiliki **Pengendali default** yang dijalankan kernel saat menangani sinyal
- **Penanganan sinyal yang ditentukan pengguna** dapat menggantikan default
- Untuk single-threaded, sinyal dikirim ke proses

Ke mana sinyal harus dikirimkan untuk multi-threaded?

- Mengirimkan sinyal ke utas yang menggunakan sinyal tersebut
- Mengirimkan sinyal ke setiap utas dalam proses
- Mengirimkan sinyal ke utas tertentu dalam proses
- Menetapkan thread tertentu untuk menerima semua sinyal untuk proses

Dalam program multithreaded, sinyal dapat menjadi rumit. Tidak seperti single-threaded apps di mana sinyal menuju ke seluruh proses, multithreading membuat target menjadi tidak jelas.

Ada dua jenis sinyal:

- Synchronous: Dikirim ke thread yang menyebabkannya (seperti kesalahan program).
- Asynchronous: Dapat datang secara tidak terduga dari luar program (seperti sinyal penghentian).

Sinyal Asynchronous merupakan tantangan dalam multithreading karena tidak jelas thread mana yang harus menerimanya. Pada sistem Unix, thread dapat menentukan sinyal mana yang mereka inginkan, tetapi OS pada akhirnya memutuskan pengirimannya.

Windows menggunakan Panggilan Prosedur Asinkron (APC) sebagai pengganti sinyal. Tidak seperti Unix di mana sebuah thread memilih sinyalnya, semua thread dalam proses Windows dapat menerima APC.

### Thread Cancellation

#### Definisi
**Thread cancellation** adalah proses dimana sebuah thread dihentikan atau dibatalkan secara paksa saat sedang berjalan. Proses ini dapat dilakukan secara eksternal oleh sistem operasi atau secara internal oleh thread itu sendiri.

#### Jenis Thread Cancellation
1. **Asynchronous Cancellation**: Thread dapat dibatalkan kapan saja oleh sistem operasi tanpa perlu izin dari thread tersebut. Hal ini dapat menyebabkan sumber daya yang dikelola oleh thread tidak dibebaskan dengan benar, menyebabkan kebocoran memori atau kerusakan data.
   
2. **Deferred (Synchronous) Cancellation**: Thread memeriksa status pembatalan secara berkala atau pada titik-titik tertentu dalam eksekusi. Jika pembatalan diminta, thread menyelesaikan pekerjaan yang sedang dilakukan, membersihkan sumber daya yang digunakan, dan kemudian menghentikan dirinya sendiri dengan aman.

#### Keamanan dan Masalah
- **Keamanan**: Thread cancellation bisa berpotensi tidak aman jika tidak dikelola dengan hati-hati. Hal ini dapat mengakibatkan kebocoran memori, deadlock, atau kondisi balapan (race conditions).
   
- **Dampak pada Keamanan**: Pemilihan metode pembatalan yang tidak aman atau penggunaan yang tidak tepat dapat menyebabkan masalah keamanan pada aplikasi.

#### Strategi Penanganan
- **Asynchronous Cancellation**: Menggunakan teknik penguncian dan sinkronisasi untuk memastikan bahwa sumber daya dibersihkan dengan benar jika thread dibatalkan secara asinkron.
   
- **Deferred (Synchronous) Cancellation**: Menyediakan titik-titik pembatalan yang aman dalam kode sumber untuk memastikan bahwa thread dapat dihentikan dengan benar dan sumber daya yang digunakan dapat dibebaskan.

<img src="image/6.jpg" alt="Alt teks" width="600"/>


### Thread-Local Storage

#### Definisi
**Thread Local Storage (TLS)** adalah mekanisme dalam pemrograman koncurrent yang memungkinkan setiap thread dalam program untuk memiliki salinan dari variabel lokal yang berbeda, sehingga setiap thread dapat memiliki salinan variabel yang independen dari thread lainnya.

#### Fungsi Utama
1. **Isolasi Data**: Thread-local storage memungkinkan data disimpan dalam variabel lokal thread untuk tetap bersifat terisolasi dan tidak dapat diakses oleh thread lain. Hal ini berguna untuk menyimpan informasi yang spesifik untuk setiap thread, seperti penghitung atau konteks eksekusi.

2. **Pengurangan Konflik**: Dengan menggunakan variabel lokal untuk setiap thread, thread-local storage mengurangi kemungkinan konflik akses ke data antar thread, yang dapat mengurangi kompleksitas sinkronisasi dan meningkatkan kinerja aplikasi.

3. **Efisiensi**: Thread-local storage dapat meningkatkan efisiensi dalam aplikasi multithreaded dengan mengurangi overhead yang terkait dengan sinkronisasi akses ke data bersama antar thread.

#### Penggunaan Umum
1. **Penghitung Thread**: Variabel thread-local sering digunakan untuk menyimpan penghitung atau statistik yang spesifik untuk setiap thread, seperti jumlah tugas yang telah diselesaikan oleh setiap thread dalam pool thread.

2. **Konteks Eksekusi**: Thread-local storage juga digunakan untuk menyimpan konteks eksekusi yang spesifik untuk setiap thread, seperti ID sesi atau koneksi database yang ditetapkan untuk setiap thread dalam server aplikasi.

#### Implementasi
1. **Thread-Local Storage API**: Banyak bahasa pemrograman menyediakan API khusus untuk mendukung thread-local storage, seperti `ThreadLocal` class dalam Java atau `thread_local` storage specifier dalam C++11.

2. **Thread-Specific Data (TSD)**: Beberapa sistem operasi menyediakan mekanisme native untuk mengimplementasikan thread-local storage, seperti Thread-Specific Data (TSD) dalam POSIX Threads (pthread) untuk C/C++.

#### Keuntungan
- **Isolasi Data**: Memungkinkan setiap thread untuk memiliki salinan independen dari variabel lokal, yang membantu menghindari konflik akses data antar thread.
- **Pengurangan Konflik**: Mengurangi kompleksitas sinkronisasi antar thread dan meningkatkan kinerja aplikasi dengan mengurangi konflik akses data bersama.
- **Efisiensi**: Meningkatkan efisiensi aplikasi multithreaded dengan mengurangi overhead yang terkait dengan sinkronisasi akses ke data bersama.

![App Screenshhot](image/7.png)

### Scheduler Activations

#### Definisi
**Scheduler activations** adalah sebuah teknik dalam sistem operasi yang bertujuan untuk meningkatkan kinerja dalam manajemen threads. Teknik ini memungkinkan thread untuk berinteraksi secara langsung dengan scheduler dalam sistem operasi.

#### Fungsi Utama
1. **Thread-Driven Scheduling**: Scheduler activations mengizinkan setiap thread untuk berkomunikasi secara langsung dengan scheduler dalam sistem operasi. Hal ini memungkinkan thread untuk mengontrol penjadwalan dan manajemen sumber daya secara lebih efektif.

2. **Dynamic Resource Management**: Teknik ini memungkinkan thread untuk dinamis mengatur jumlah dan jenis sumber daya yang mereka butuhkan, seperti CPU time, memory, dan I/O resources, berdasarkan kebutuhan aplikasi.

3. **Perbaikan Kinerja**: Scheduler activations dapat meningkatkan kinerja sistem operasi dalam manajemen threads dengan mengurangi overhead yang terkait dengan sinkronisasi dan komunikasi antara thread dan scheduler.

#### Implementasi
1. **Kernel-Level Implementation**: Beberapa sistem operasi menerapkan scheduler activations di tingkat kernel, memungkinkan thread untuk berkomunikasi langsung dengan scheduler kernel melalui antarmuka yang diberikan.

2. **User-Level Implementation**: Ada juga implementasi scheduler activations di tingkat user-space, di mana library atau runtime environment menangani interaksi antara thread dan scheduler.

#### Keuntungan
- **Thread-Driven Scheduling**: Memungkinkan thread untuk berkomunikasi langsung dengan scheduler, meningkatkan kontrol dan kinerja dalam manajemen threads.
- **Dynamic Resource Management**: Thread dapat dinamis mengatur sumber daya yang dibutuhkan berdasarkan kebutuhan aplikasi.
- **Perbaikan Kinerja**: Meningkatkan kinerja sistem operasi dalam manajemen threads dengan mengurangi overhead sinkronisasi dan komunikasi.

<img src="image/8.png" alt="Alt teks" width="500"/>


### Windows Threads

#### Definisi
**Windows Threads** merujuk pada implementasi threads dalam lingkungan sistem operasi Windows. Threads di Windows dapat dibuat dan dikelola menggunakan berbagai API yang disediakan oleh sistem operasi, seperti Win32 API atau Windows Runtime API (untuk aplikasi Universal Windows Platform).

#### Fitur Utama
1. **Thread Creation**: Windows menyediakan fungsi-fungsi API, seperti `CreateThread` dalam Win32 API atau `ThreadPool.RunAsync` dalam Windows Runtime API, untuk membuat threads dalam aplikasi.

2. **Thread Synchronization**: Windows menyediakan berbagai mekanisme sinkronisasi, seperti mutexes, semaphores, dan event objects, yang dapat digunakan untuk mengkoordinasikan akses ke sumber daya bersama antar threads.

3. **Thread Termination**: Windows menyediakan fungsi-fungsi API, seperti `ExitThread` dalam Win32 API atau `Thread.Abort` dalam Windows Runtime API, untuk menghentikan eksekusi thread.

4. **Thread Priority**: Windows mendukung pengaturan prioritas untuk threads, yang memungkinkan pengembang untuk menentukan urutan eksekusi dan alokasi sumber daya berdasarkan kebutuhan aplikasi.

#### Implementasi
1. **Win32 API**: Untuk aplikasi desktop tradisional, threads dapat dibuat dan dikelola menggunakan fungsi-fungsi API dalam Win32 API, seperti `CreateThread`, `WaitForSingleObject`, dan sebagainya.

2. **Windows Runtime API**: Untuk aplikasi Universal Windows Platform (UWP), threads dapat dibuat dan dikelola menggunakan API dalam Windows Runtime, seperti `ThreadPool.RunAsync`, `CoreApplication.MainView.CoreWindow.Dispatcher.RunAsync`, dan sebagainya.

#### Keuntungan
- **Fleksibilitas**: Windows menyediakan berbagai API untuk membuat, mengelola, dan berinteraksi dengan threads, memungkinkan pengembang untuk memilih yang paling sesuai dengan kebutuhan aplikasi.
- **Kinerja**: Dengan dukungan untuk pengaturan prioritas dan sinkronisasi yang efisien, threads di Windows dapat dioptimalkan untuk kinerja yang baik.

<img src="image/9.png" alt="Alt teks" width="500"/>


### Linux Threads

#### Definisi
**Linux Threads** merujuk pada implementasi threads dalam sistem operasi Linux. Thread di Linux dapat dibuat dan dikelola menggunakan POSIX Threads (pthreads) API, yang merupakan standar de facto untuk threading dalam lingkungan Unix dan Unix-like.

#### Fitur Utama
1. **POSIX Threads (pthreads)**: Linux menyediakan implementasi standar POSIX Threads, yang memungkinkan pembuatan, pengelolaan, dan sinkronisasi threads dalam aplikasi.

2. **Thread Creation**: Threads dapat dibuat menggunakan fungsi `pthread_create`, yang memungkinkan pengembang untuk menentukan fungsi yang akan dieksekusi oleh thread baru.

3. **Thread Synchronization**: Linux menyediakan berbagai mekanisme sinkronisasi untuk koordinasi akses ke sumber daya bersama antar threads, termasuk mutexes, conditions, dan semaphores.

4. **Thread Termination**: Threads dapat dihentikan menggunakan fungsi `pthread_exit`, yang memungkinkan thread untuk mengembalikan nilai atau status eksekusi ketika dihentikan.

#### Implementasi
1. **POSIX Threads API**: Threads di Linux dibuat dan dikelola menggunakan POSIX Threads API, yang terdiri dari fungsi-fungsi seperti `pthread_create`, `pthread_join`, `pthread_mutex_init`, dan sebagainya.

#### Keuntungan
- **Portabilitas**: Kode yang menggunakan POSIX Threads API dapat dipindahkan dengan mudah antara sistem operasi yang mendukung standar POSIX, seperti Linux, macOS, dan Unix-like lainnya.
- **Fleksibilitas**: POSIX Threads API menyediakan berbagai mekanisme untuk membuat, mengelola, dan berinteraksi dengan threads, memberikan fleksibilitas dalam pengembangan aplikasi multithreaded.

![App Screenshot](image/10.jpg)

## Pertanyaan dan Jawaban seputar Threads

### Soal 1
Apa yang dimaksud dengan thread dalam konteks pemrograman?

### Jawaban 1
Thread adalah unit kecil dari sebuah proses yang dapat dieksekusi secara independen. Thread memiliki kemampuan untuk menjalankan kode secara bersamaan dengan thread lain dalam suatu proses, dan dapat memiliki sumber daya komputasi yang terpisah seperti register, stack, dan counter program.

---

### Soal 2
Apa perbedaan antara proses dan thread dalam sistem operasi?

### Jawaban 2
Proses adalah sebuah program yang sedang dijalankan oleh sistem operasi. Proses memiliki alamat memori, ruang lingkup variabel, dan sumber daya sistem yang terpisah. Thread, di sisi lain, adalah unit kecil dari sebuah proses yang dapat dieksekusi secara independen. Thread berbagi memori dan sumber daya sistem dengan thread lain dalam proses yang sama.

---

### Soal 3
Apa keuntungan menggunakan threading dalam pengembangan perangkat lunak?

### Jawaban 3
Beberapa keuntungan menggunakan threading dalam pengembangan perangkat lunak antara lain:
1. Meningkatkan responsivitas aplikasi dengan memungkinkan eksekusi tugas secara bersamaan.
2. Meningkatkan kinerja aplikasi dengan memanfaatkan multiple core processor secara efisien.
3. Meningkatkan skalabilitas aplikasi dengan memungkinkan aplikasi menangani jumlah permintaan yang lebih besar.
4. Meningkatkan pengalaman pengguna dengan menjalankan tugas-tugas latar belakang tanpa mengganggu interaksi pengguna.

---

### Soal 4
Apa yang dimaksud dengan deadlock dalam konteks threading?

### Jawaban 4
Deadlock adalah kondisi di mana dua atau lebih thread saling menunggu satu sama lain untuk melepaskan sumber daya yang mereka pegang, sehingga tidak ada thread yang dapat melanjutkan eksekusinya. Kondisi ini dapat terjadi ketika thread menahan sumber daya yang diperlukan oleh thread lain dan dalam waktu yang bersamaan menunggu sumber daya yang diperlukan dari thread lainnya.

---

### Soal 5
Bagaimana cara mencegah race condition dalam pengembangan aplikasi multithreading?

### Jawaban 5
Beberapa cara mencegah race condition dalam pengembangan aplikasi multithreading antara lain:
1. Menggunakan teknik sinkronisasi seperti mutexes, locks, dan semaphores untuk mengontrol akses ke data bersama.
2. Menghindari pembacaan dan penulisan data bersamaan dari beberapa thread.
3. Memastikan bahwa bagian kritis kode yang melibatkan operasi bersama di-proteksi menggunakan mekanisme sinkronisasi yang sesuai.
4. Menggunakan aturan-aturan desain thread-safe dalam pengembangan aplikasi, seperti mengisolasi variabel yang bersifat shared dan membatasi akses ke data bersama.

---

### Soal 6
Apa yang dimaksud dengan thread pool?

### Jawaban 6
Thread pool adalah sebuah kumpulan dari thread-thread yang telah dipreparasi sebelumnya dan siap untuk mengeksekusi tugas-tugas yang diberikan. Thread pool memungkinkan penggunaan ulang thread yang ada, mengurangi overhead pembuatan dan penghancuran thread, serta meningkatkan kinerja aplikasi dengan mengurangi waktu inisialisasi thread.


## Referensi

- https://www.geeksforgeeks.org/benefits-of-multithreading-in-operating-system/
- https://www.geeksforgeeks.org/difference-between-concurrency-and-parallelism/
- https://www.geeksforgeeks.org/challanges-in-programming-for-multicore-system/
- https://www.geeksforgeeks.org/difference-between-user-level-thread-and-kernel-level-thread/
- https://www.geeksforgeeks.org/multi-threading-models-in-process-management/
- https://www.geeksforgeeks.org/posix-threads-in-os/
- https://www.geeksforgeeks.org/java-threads/
- https://www.geeksforgeeks.org/threading-issues/