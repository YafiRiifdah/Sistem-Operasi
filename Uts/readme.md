<div align="center">
  <h1 style="text-align: center;font-weight: bold">UTS<br>Sistem Operasi</h1>
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

<h1 style="font-weight: bold">Fork: Parent - Child Process</h1>

## Soal 1
1. Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
2. Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan <code>fork()</code>.

### jawaban
1. Fork adalah salah satu konsep penting dalam sistem operasi yang memungkinkan sebuah proses untuk menghasilkan salinan atau replika dari dirinya sendiri. Dalam konteks bahasa pemrograman C, fungsi fork() digunakan untuk menciptakan proses baru yang identik dengan proses pemanggilnya. Proses baru yang dihasilkan disebut sebagai child process, sementara proses yang memanggilnya disebut sebagai parent process. Setelah proses child dibuat, keduanya dapat berjalan secara independen dan memiliki ruang alamat memori yang terpisah.

Implementasi konsep fork dalam bahasa pemrograman C memungkinkan penggunaan fungsi fork() yang disediakan oleh sistem operasi. Proses parent dapat menggunakan nilai yang dikembalikan oleh fork() untuk membedakan antara dirinya dan proses child. Jika nilai yang dikembalikan adalah nol, itu berarti proses child sedang berjalan, sedangkan jika nilai itu adalah ID proses child, itu berarti proses parent sedang berjalan. Dengan demikian, penggunaan fork() dalam bahasa C memungkinkan pembuatan proses baru dan pemisahan tugas antara parent dan child process.

<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork%20parent.jpeg">

<pre notranslate>
<code>#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t child_pid;

    // Memanggil fork()
    child_pid = fork();

    if (child_pid == 0) {
        // Kode untuk child process
        printf("Ini adalah child process dengan PID: %d\n", getpid());
    } else if (child_pid > 0) {
        // Kode untuk parent process
        printf("Ini adalah parent process dengan PID: %d\n", getpid());
        printf("Child process memiliki PID: %d\n", child_pid);
    } else {
        // Kasus jika fork() gagal
        perror("fork");
        return 1;
    }

    return 0;
}</code></pre>

menggunakan fungsi fork() untuk membuat proses baru. Proses parent akan mencetak PID dari proses child yang dibuat, sementara proses child akan mencetak pesan bahwa ia adalah child process berserta dengan PID-nya sendiri. Dengan demikian, konsep fork dalam bahasa C memungkinkan pemrogram untuk membuat aplikasi yang melakukan multitasking dan menjalankan tugas secara paralel.

<b>B.</b> Selanjutnya lakukan cloning https://github.com/ferryastika/operatingsystem.git
<img src="gambar clone giit"

<b>C.</b> Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program <code>fork01.c</code>, <code>Fork02.c</code>, <code>fork03.c</code>, <code>fork04.c</code>, <code>fork05.c</code>dan <code>fork06.c</code>.

<b>Listing Program</b> <code>Fork01.c</code>
<pre notranslate>
<code>
#include <iostream>
#include <.sys/types.h>
#include <.unistd.h>

using namespace std;

int main(void) {
    pid_t mypid;
    uid_t myuid;
    for (int i = 0; i < 3; i++) {
        mypid = getpid();
        cout << "I am process " << mypid << endl;
        cout << "My parent process ID is " << getppid() << endl;
        cout << "The owner of this process has uid " << getuid() << endl;

        // sleep adalah system call atau fungsi library
        // yang menghentikan proses ini dalam detik
        sleep(3);
    }
    return 0;
}
</code>
</pre>

Output Program
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork1.jpeg"></div>

<b>Analisa:</b> Program mencetak informasi tentang ID proses, ID proses induk, dan ID pengguna untuk proses tersebut dalam sebuah loop. Dalam setiap iterasi, nilai-nilai ini dicetak dan program menunggu selama 3 detik sebelum mencetak informasi untuk iterasi berikutnya. Dengan demikian, output program akan menampilkan informasi tentang tiga iterasi dari proses yang berjalan.

<b>Visualisasi</b>
<pre notranslate>
<code>Iterasi 1:
  I am process 1234
  |       |       |
  |       v       v
  |  My parent   The owner
  |  process ID   of this
  |     is       process has
  v   5678         uid 1000

Iterasi 2:
  I am process 1235
  |       |       |
  |       v       v
  |  My parent   The owner
  |  process ID   of this
  |     is       process has
  v   5678         uid 1000

Iterasi 3:
  I am process 1236
  |       |       |
  |       v       v
  |  My parent   The owner
  |  process ID   of this
  |     is       process has
  v   5678         uid 1000
</code>
</pre>

<b>Listing Program</b><code>Fork02.c</code>
<pre notranslate>
<code>using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>


/* getpid() adalah system call yg dideklarasikan pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t mypid;
	uid_t myuid;
	for (int i = 0; i < 3; i++) {
		mypid = getpid();
		cout << "I am process " << mypid << endl;
		cout << "My parent process ID is " << getppid() << endl;
		cout << "The owner of this process has uid " << getuid()
	<< endl;
/* sleep adalah system call atau fungsi library
yang menghentikan proses ini dalam detik
*/
	sleep(3);
	}
return 0;
}</code></pre>

Output Program
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork2.jpeg"></div>

<b>Analisa:</b> Program ini adalah contoh sederhana dari penggunaan fungsi sistem dalam bahasa C, khususnya dalam konteks sistem operasi Unix-like. Dalam program ini, kita menggunakan fungsi-fungsi sistem seperti getpid(), getppid(), dan getuid() untuk mendapatkan informasi tentang proses saat ini, proses induk, dan pemilik proses. Loop for digunakan untuk mencetak informasi tersebut dalam tiga iterasi. Dengan menggunakan fungsi sleep(3) di dalam loop, program menjeda eksekusi selama 3 detik setiap kali mencetak informasi. Ini memungkinkan kita untuk melihat bagaimana ID proses, ID proses induk, dan ID pengguna mungkin berubah setiap kali program dijalankan, serta bagaimana proses dapat menunggu dalam jangka waktu tertentu sebelum melanjutkan eksekusi selanjutnya. Dengan demikian, program memberikan pemahaman yang sederhana namun bermanfaat tentang cara kerja dasar sistem operasi Unix-like dalam hal pengelolaan proses dan akses informasi tentang mereka.

<b>Visualisasi</b>
<pre nostranslate>
<code>Parent Process ------------> Child Process (forked)
  |                           |
  v                           v
This is process ID [PID_Parent]   This is process ID [PID_Child]
In this process the value of x becomes 5 In this process the value of x becomes 5
  |                           |
  v                           v
[PID_Parent] increases x      [PID_Child] increases x
  |                           |
  v                           v
This is process ID [PID_Parent]   This is process ID [PID_Child]
In this process the value of x becomes 6 In this process the value of x becomes 6
  |                           |
  v                           v
[PID_Parent] increases x      [PID_Child] increases x
  |                           |
  v                           v
...
</code></pre>

<b>Listing Program</b><code>Fork03.c</code>
<pre notranslate>
<code>#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>


/* getpid() dan fork() adalah system call yg dideklarasikan
pada unistd.h.
Menghasilkan suatu nilai dengan type pid_t.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/
int main(void) {
	pid_t childpid;
	childpid = fork();
	for (int i = 0; i < 5; i++) {
		cout << "This is process " << getpid() << endl;
		sleep(2);
	}
	return 0;
}</code></pre>

Output Program
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork3.jpeg"></div>

<b>Analisa:</b>Program di atas menggunakan fungsi <code>fork()</code> untuk membuat child process baru. Setelah pemanggilan <code>fork()</code>, kedua proses, yaitu parent dan child, akan menjalankan loop for yang mencetak ID proses masing-masing <code>(getpid())</code> lima kali dengan jeda waktu 2 detik <code>(sleep(2))</code>. Karena kedua proses mengeksekusi loop yang sama, kita akan melihat pesan "This is process [PID]" dicetak secara bergantian oleh parent dan child setiap dua detik. Namun, perlu diperhatikan bahwa kedua proses tersebut memiliki ID proses yang berbeda, karena child process memiliki ID proses yang baru dibuat setelah pemanggilan <code>fork()</code>. Dengan demikian, program ini memberikan ilustrasi sederhana tentang bagaimana child process dapat dibuat dan berjalan secara bersamaan dengan parent process.

<b>Visualisasi:</b>
<pre notranslate>
<code>Parent Process ---------------> Child Process (forked)
   |                              |
   v                              v
This is process [PID_Parent]   This is process [PID_Child]
   |                              |
   v                              v
    |                             |
    v                             v
This is process [PID_Parent]   This is process [PID_Child]
   |                              |
   v                              v
    |                             |
    v                             v
This is process [PID_Parent]   This is process [PID_Child]
   |                              |
   v                              v
    |                             |
    v                             v
This is process [PID_Parent]   This is process [PID_Child]
   |                              |
   v                              v
    |                             |
    v                             v
This is process [PID_Parent]   This is process [PID_Child]
</code></pre>

<b>Listing Program:</b><code>Fork04</code>
<pre nostranslate><code>#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();
	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		cout << "My parent is " << getppid() << endl;
		/* keluar if akan menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid() << endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
		/* kode ini dieksekusi baik oleh proses parent dan child */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
		/* kode ini hanya dieksekusi oleh proses child */
		cout << "I am a child and I am quitting work now!"<< endl;
	}
	else {
		/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
	do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda bahwa proses child diterminasi */
		wait_result = wait(&status);
	} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}</code></pre>

Output Program:
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork4.jpeg"></div>

<b>Analisa:</b> Program ini merupakan contoh penggunaan fungsi <code>fork()</code> dalam sistem Unix-like untuk membuat child process. Setelah pemanggilan <code>fork(</code>), kedua proses, yaitu parent dan child, memiliki aliran eksekusi yang terpisah. Dalam parent process, hasil <code>fork()</code> akan mengembalikan PID (Process ID) dari child process yang baru dibuat, sedangkan dalam child process, hasil <code>fork()</code> akan mengembalikan nilai 0.

Pada blok if (child_pid == 0), kode di dalamnya hanya dieksekusi oleh child process, yang mencetak informasi tentang PID-nya sendiri dan PID parent-nya (getpid() dan getppid()). Sementara pada blok else if (child_pid > 0), kode di dalamnya hanya dieksekusi oleh parent process, yang mencetak informasi tentang PID-nya sendiri dan PID child-nya.

Setelah itu, keduanya mencetak pesan yang menunjukkan bahwa mereka adalah proses yang sehat dan bahagia. Jika proses yang sedang berjalan adalah child process, maka ia akan mencetak pesan bahwa ia telah selesai bekerja. Sedangkan jika proses yang sedang berjalan adalah parent process, maka ia akan menunggu child processnya untuk selesai bekerja dengan menggunakan fungsi wait(), dan kemudian mencetak pesan bahwa ia telah selesai.

Dengan demikian, program ini memberikan ilustrasi tentang bagaimana penggunaan fungsi <code>fork()</code> untuk membuat child process, serta bagaimana interaksi antara parent dan child process dalam sistem operasi Unix-like.

<b>Visualisasi:</b>
<pre notranslat>
<code>Parent Process ---------------> Child Process (forked)
   |                              |
   v                              v
I am the parent and my pid = [PID_Parent]     I am a child and my pid = [PID_Child]
My child has pid = [PID_Child]               My parent is [PID_Parent]
   |                                         |
   v                                         v
I am a happy, healthy process and my pid = [PID_Parent]  I am a happy, healthy process and my pid = [PID_Child]
   |                                                   |
   v                                                   v
I am a parent and I am going to wait for my child   I am a child and I am quitting work now!
   |                                                   |
   v                                                   v
I am a parent and I am quitting.                       (End)
</code></pre>

<b>Listing Program:</b><code>Fork05</code>
<pre notranslate>
<code>#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
  pid_t child_pid;
  int status; 
  pid_t wait_result;
  child_pid = fork();
  if (child_pid == 0) {
    /* kode ini hanya dieksekusi proses child */
    cout << "I am a child and my pid = " << getpid() << endl;
    execl("/bin/ls", "ls", "-l", "/home", NULL);
    /* jika execl berhasil kode ini tidak pernah digunakan */
    cout << "Could not execl file /bin/ls" << endl;
    exit(1);
    /* exit menghentikan hanya proses child */
   }
  else if (child_pid > 0) {
    /* kode ini hanya mengeksekusi proses parent */
   cout << "I am the parent and my pid = " << getpid() << endl;
   cout << "My child has pid = " << child_pid << endl;
  }
  else {
   cout << "The fork system call failed to create a new process" << endl;
   exit(1);
  }
  /* kode ini hanya dieksekusi oleh proses parent karena
  child mengeksekusi dari “/bin/ls” atau keluar */
   cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
   if (child_pid == 0) {
  /* kode ini tidak pernah dieksekusi */
   printf("This code will never be executed!\n");
  }
  else {
   /* kode ini hanya dieksekusi oleh proses parent */
    cout << "I am a parent and I am going to wait for my child" << endl;
    do {
      /* parent menunggu sinyal SIGCHLD mengirim tanda bila proses child diterminasi */
      wait_result = wait(&status);
    } while (wait_result != child_pid);
    cout << "I am a parent and I am quitting." << endl;
  }
  return 0;
}</code></pre>

Output Program:
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork5.jpeg"></div>
<img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork05.jpeg">
<b>Analisa:</b>
Program ini adalah contoh penggunaan fungsi <code>fork() </code>dan execl() dalam sistem Unix-like untuk membuat child process dan menjalankan program baru di dalamnya. Setelah pemanggilan <code>fork()</code>, parent process akan mencetak informasi tentang PID-nya sendiri dan PID child process yang baru dibuat, sedangkan child process akan mencetak informasi tentang PID-nya sendiri dan menjalankan program /bin/ls dengan menggunakan fungsi execl().

Dalam blok if (child_pid == 0), kode di dalamnya hanya dieksekusi oleh child process. Di sini, child process mencetak informasi tentang PID-nya sendiri, kemudian menjalankan program /bin/ls dengan argumen -l /home. Jika execl() berhasil, kode setelahnya tidak akan dieksekusi. Namun, jika execl() gagal, child process akan mencetak pesan kesalahan dan keluar dengan status 1.

Dalam blok else if (child_pid > 0), kode di dalamnya hanya dieksekusi oleh parent process, yang mencetak informasi tentang PID-nya sendiri dan PID child process yang baru dibuat.

Setelah itu, keduanya mencetak pesan bahwa mereka adalah proses yang sehat dan bahagia. Jika proses yang sedang berjalan adalah parent process, maka ia akan menunggu child process selesai bekerja dengan menggunakan fungsi wait(), dan kemudian mencetak pesan bahwa ia telah selesai.

<b>Visualisasi:</b>
<pre notranslate>
<code>Parent Process ---------------> Child Process (forked)
   |                              |
   v                              v
I am the parent and my pid = [PID_Parent]     I am a child and my pid = [PID_Child]
My child has pid = [PID_Child]               (New process: /bin/ls -l /home)
   |                                         |
   v                                         v
I am a happy, healthy process and my pid = [PID_Parent]  I am a child process executing /bin/ls
   |                                                   |
   v                                                   v
I am a parent and I am going to wait for my child   (End)
   |                                                   |
   v                                                   v
I am a parent and I am quitting.                       (End)
</code></pre>

<b>Listing Program:</b><code>Fork06</code>
<pre notranslate>
<code>#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>
#include <sys/wait.h>
/* pid_t fork() dideklarasikan pada unistd.h.
pid_t adalah type khusus untuk process id yg ekuivalen dg int
*/

int main(void) {
	pid_t child_pid;
	int status;
	pid_t wait_result;
	child_pid = fork();


	if (child_pid == 0) {
		/* kode ini hanya dieksekusi proses child */
		cout << "I am a child and my pid = " << getpid() << endl;
		execl("fork03", "goose", NULL);
		/* jika execl berhasil kode ini tidak pernah digunakan */
		cout << "Could not execl file fork3" << endl;
		exit(1);
		/* exit menghentikan hanya proses child */
	}
	else if (child_pid > 0) {
		/* kode ini hanya mengeksekusi proses parent */
		cout << "I am the parent and my pid = " << getpid()<< endl;
		cout << "My child has pid = " << child_pid << endl;
	}
	else {
		cout << "The fork system call failed to create a new process" << endl;
		exit(1);
	}
	/* kode ini hanya dieksekusi oleh proses parent karena
	child mengeksekusi dari “fork3” atau keluar */
		cout << "I am a happy, healthy process and my pid = " << getpid() << endl;
		if (child_pid == 0) {
	/* kode ini tidak pernah dieksekusi */
		printf("This code will never be executed!\n");
	}
	else {
	/* kode ini hanya dieksekusi oleh proses parent */
		cout << "I am a parent and I am going to wait for my child" << endl;
		do {
		/* parent menunggu sinyal SIGCHLD mengirim tanda
		bila proses child diterminasi */
			wait_result = wait(&status);
		} while (wait_result != child_pid);
		cout << "I am a parent and I am quitting." << endl;
	}
	return 0;
}</code></pre>

Output Program:
<div><img src="https://github.com/YafiRiifdah/SysOp_3123500001/blob/main/Uts/Image/fork6.jpeg"></div>

<b>Analisa:</b>
Program ini adalah contoh penggunaan fungsi <code>fork()</code> dan execl() dalam sistem Unix-like untuk membuat child process dan menjalankan program baru di dalamnya. Setelah pemanggilan <code>fork()</code>, parent process akan mencetak informasi tentang PID-nya sendiri dan PID child process yang baru dibuat, sedangkan child process akan mencetak informasi tentang PID-nya sendiri dan menjalankan program baru dengan nama "fork03" dengan argumen "goose" menggunakan fungsi execl().

Dalam blok if (child_pid == 0), kode di dalamnya hanya dieksekusi oleh child process. Di sini, child process mencetak informasi tentang PID-nya sendiri, kemudian menjalankan program baru dengan nama "fork03" dan argumen "goose" menggunakan execl(). Jika execl() berhasil, kode setelahnya tidak akan dieksekusi. Namun, jika execl() gagal, child process akan mencetak pesan kesalahan dan keluar dengan status 1.

Dalam blok else if (child_pid > 0), kode di dalamnya hanya dieksekusi oleh parent process, yang mencetak informasi tentang PID-nya sendiri dan PID child process yang baru dibuat.

Setelah itu, keduanya mencetak pesan bahwa mereka adalah proses yang sehat dan bahagia. Jika proses yang sedang berjalan adalah parent process, maka ia akan menunggu child process selesai bekerja dengan menggunakan fungsi wait(), dan kemudian mencetak pesan bahwa ia telah selesai.

Dengan demikian, program ini memberikan ilustrasi tentang bagaimana penggunaan fungsi <code>fork()</code> untuk membuat child process, serta bagaimana child process dapat menjalankan program baru di dalamnya menggunakan execl().

<b>Visualisasi</b>
<pre notranslate>
<code>Parent Process ---------------> Child Process (forked)
   |                              |
   v                              v
I am the parent and my pid = [PID_Parent]     I am a child and my pid = [PID_Child]
My child has pid = [PID_Child]               (New process: fork03 "goose")
   |                                         |
   v                                         v
I am a happy, healthy process and my pid = [PID_Parent]  I am a child process executing fork03 "goose"
   |                                                   |
   v                                                   v
I am a parent and I am going to wait for my child   (End)
   |                                                   |
   v                                                   v
I am a parent and I am quitting.                       (End)
</code></pre>

2. Buatlah program perkalian 2 matriks [4 x 4] dalam bahasa C yang memanfaatkan <code>fork().</code>


