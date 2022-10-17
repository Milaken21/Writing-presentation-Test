# Asynchronous Fetch
mengambil item data individual dari server untuk memperbarui bagian halaman web tanpa harus memuat seluruh halaman baru.

API utama di sini adalah Fetch API. memungkinkan JavaScript yang berjalan di halaman untuk membuat permintaan HTTP ke server untuk mengambil sumber daya tertentu. Saat server menyediakannya, JavaScript dapat menggunakan data untuk memperbarui halaman, biasanya dengan menggunakan API manipulasi DOM . Data yang diminta seringkali berupa JSON , yang merupakan format yang baik untuk mentransfer data terstruktur, tetapi bisa juga berupa HTML atau hanya teks.

# Fetch API
* Pertama, titik masuk ke Fetch API adalah fungsi global yang disebut fetch(), yang menggunakan URL sebagai parameter (dibutuhkan parameter opsional lain untuk setelan khusus, tetapi kami tidak menggunakannya di sini).
* Selanjutnya, fetch()adalah API asinkron yang mengembalikan file Promise. Jika Anda tidak tahu apa itu, baca modul tentang JavaScript asinkron , dan khususnya artikel tentang promise , lalu kembali ke sini. Anda akan menemukan artikel itu juga berbicara tentang fetch()API!
* Jadi karena fetch()mengembalikan promise, kami meneruskan fungsi ke then()metode promise yang dikembalikan. Metode ini akan dipanggil ketika permintaan HTTP telah menerima respons dari server. Di handler, kami memeriksa apakah permintaan berhasil, dan membuat kesalahan jika tidak. Jika tidak, kami memanggil response.text(), untuk mendapatkan isi respons sebagai teks.
* Ternyata itu response.text()juga tidak sinkron , jadi kami mengembalikan promise yang dikembalikannya, dan meneruskan fungsi ke then()metode promise baru ini. Fungsi ini akan dipanggil ketika teks respons siap, dan di dalamnya kita akan memperbarui blok kita dengan teks.
* Terakhir, kita merangkai sebuah catch()handler di bagian akhir, untuk menangkap error yang terjadi di salah satu fungsi asinkron yang kita panggil atau handler-nya.

# API XMLHttpRequest
Terkadang, terutama dalam kode yang lebih lama, Anda akan melihat API lain yang disebut XMLHttpRequest(sering disingkat sebagai "XHR") yang digunakan untuk membuat permintaan HTTP. Ini mendahului Fetch, dan benar-benar merupakan API pertama yang digunakan secara luas untuk mengimplementasikan AJAX. Kami menyarankan Anda menggunakan Fetch jika Anda bisa: ini adalah API yang lebih sederhana dan memiliki lebih banyak fitur daripada XMLHttpRequest. 
```
const request = new XMLHttpRequest();

try {
  request.open('GET', 'products.json');

  request.responseType = 'json';

  request.addEventListener('load', () => initialize(request.response));
  request.addEventListener('error', () => console.error('XHR error'));

  request.send();

} catch (error) {
  console.error(`XHR error ${request.status}`);
}
```
Ada lima tahap untuk ini:
1. Buat XMLHttpRequestobjek baru.
2. Panggil open()metodenya untuk menginisialisasi.
3. Tambahkan pendengar acara ke loadacaranya, yang diaktifkan saat respons berhasil diselesaikan. Di pendengar kita memanggil initialize()dengan data.
4. Tambahkan pendengar acara ke erroracaranya, yang diaktifkan saat permintaan mengalami kesalahan
5 Kirim permintaan.
Kita juga harus membungkus semuanya dalam blok try...catch , untuk menangani kesalahan yang dilontarkan oleh open()or send().

# Asyncrhonous
Pemrograman asinkron adalah teknik yang memungkinkan program Anda untuk memulai tugas yang berpotensi berjalan lama dan masih dapat responsif terhadap peristiwa lain saat tugas itu berjalan, daripada harus menunggu sampai tugas itu selesai. Setelah tugas itu selesai, program Anda disajikan dengan hasilnya.
# Synchronous Program
```
const name = 'Miriam';
const greeting = `Hello, my name is ${name}!`;
console.log(greeting);
// "Hello, my name is Miriam!"
```
1. Mendeklarasikan string yang disebut name.
2. Mendeklarasikan string lain yang disebut greeting, yang menggunakan name.
3. Menampilkan salam ke konsol JavaScript.
Pada setiap titik, browser menunggu baris untuk menyelesaikan pekerjaannya sebelum melanjutkan ke baris berikutnya. Ini harus dilakukan karena setiap baris tergantung pada pekerjaan yang dilakukan pada baris sebelumnya.
# Fungsi synchron yang berjalan lama
masalah dasar dengan fungsi sinkron yang berjalan lama. Yang kami butuhkan adalah cara agar program kami:

1. Mulai operasi yang berjalan lama dengan memanggil fungsi.
2. Suruh fungsi tersebut mulai beroperasi dan segera kembali, agar program kita tetap bisa responsif terhadap event-event lainnya.
3. Beritahu kami dengan hasil operasi ketika akhirnya selesai.

# Event Handlers
Event handlers merupakan bentuk pemrograman asinkron: menyediakan fungsi (event handlers) yang akan dipanggil, tidak segera, tetapi kapan pun peristiwa itu terjadi. Jika "peristiwa" adalah "operasi asinkron telah selesai", maka peristiwa tersebut dapat digunakan untuk memberi tahu pemanggil tentang hasil pemanggilan fungsi asinkron.

# Callbacks

Event handlers adalah jenis callback tertentu. Callback hanyalah fungsi yang diteruskan ke fungsi lain, dengan harapan bahwa panggilan balik akan dipanggil pada waktu yang tepat. Seperti yang baru saja kita lihat, callback dulunya merupakan cara utama penerapan fungsi asinkron dalam JavaScript.
```
function doStep1(init, callback) {
  const result = init + 1;
  callback(result);
}

function doStep2(init, callback) {
  const result = init + 2;
  callback(result);
}

function doStep3(init, callback) {
  const result = init + 3;
  callback(result);
}

function doOperation() {
  doStep1(0, (result1) => {
    doStep2(result1, (result2) => {
      doStep3(result2, (result3) => {
        console.log(`result: ${result3}`);
      });
    });
  });
}

doOperation();
```
Karena kita harus memanggil callback di dalam callback, kita mendapatkan doOperation()fungsi yang sangat bersarang, yang jauh lebih sulit untuk dibaca dan di-debug. Ini kadang-kadang disebut "callback hell" atau "pyramid of doom" (karena lekukannya terlihat seperti piramida di sisinya).

Saat kita membuat callback seperti ini, penanganan error juga bisa menjadi sangat sulit: sering kali Anda harus menangani error di setiap level "piramida", alih-alih hanya menangani error sekali di level teratas.

Karena alasan ini, sebagian besar API asinkron modern tidak menggunakan callback. Sebaliknya, dasar dari pemrograman asinkron dalam JavaScript adalah Promise

# Git and Github Lanjutan

Cara membuat Github Organization
1. Klik tanda plus di pojok kanan kemudian pilih new organization
2. Kemudian pilih yang free kemudia klik "create a free organization"
3. kemudia isi fill di set up organization
4. Setelah Organisasi selesai maka bisa invite teman se tim

# GIT STATUS
3 KONDISI PADA FILE GIT
* Modified : kondisi dimana revisi atau perubahan sudah dilakukan, tetapi belum ditandai (untracked) dan belum disimpan dalam version control.
* Staged : kondisi dimana revisi sudah ditandai (modified) namun belum disimpan di version control.
* Committed : kondisi dimana revisi sudah disimpan pada version control.

# GIT ADD
Setelah cek status dengan ‘git status’, selanjutnya kita ubah status ‘untrackted file’ dan ‘unmodified’ menjadi modified

Gunakan git add
```
git add index.html
```
atau
```
git add .
```
Tapi gimana kalau untracked file nya dalam jumlah besar? tetap bisa menggunakan perintah ``` git add . ```

# GIT COMMIT
Lakukan ‘git commit’ untuk save perubahan pada version control
```
git commit -m "Commit pertama"
```

# GIT LOG
Dari dua revisi yang sudah dilakukan kita dapat melihat catatal log dari revisi - revisi tersebut dengan menggunakan perintah berikut ini:
``` git log ```
Untuk git log yang lebih pendek, bisa menggunakan perintah berikut ini:
``` git log --oneline ```

Melihat log dari berbagai sisi.
1. Melihat log menggunakan nomor version/commit 
2. Melihat log file tertentu 
``` git log index.html ```
3. Melihat log berdasarkan author
``` git log --author='David Wiralda' ```

# GIT CHECKOUT, GIT RESET, GIT REVERT

Jika perubahan yang sedang dilakukan terjadi kesalahan dan kita ingin mengembalikan keadaan seperti sebelumnya maka itu bisa dilakukan 

# CEK PERUBAHAN
``` git diff ```

* Membatalkan Perubahan - Belum Stagged dan Belum Commited
``` git checkout index.html ```
* Membatalkan Perubahan - Sudah Stagged namun Belum Commited
``` git reset index.html ```

* Kondisi file sudah pada kondisi ‘Modified’ Selanjutnya kita lakukan proses yg sama sebelumnya. Menggunakan ‘git checkout’

* Membatalkan Perubahan - Sudah Stagged namun Belum Commited
``` git checkout index.html ```

* Kita bisa mengembalikan kondisi ke commit sebelumnya dari commit terakhir menggunakan nomor commit

* Mengembalikan Commit Pada File Tertentu
``` git reset index.html ```

* Mengembalikan Commit Untuk Semua File
Kita hanya perlu menggunakan nomor commit saja. Tidak perlu menambahkan spesifik file.
``` git checkout h3j22uy54j5h4uy54jh5 ```

* Jika ingin mengembalikan commit jauh ke bawah. Misal kita ingin kembali pada 3 commit sebelumnya
``` git checkout HEAD~3 index.html ```

# GIT REVERT
GIT Revert akan membatalkan semua perubahan yang ada tanpa menghapus commit terakhir. Jika menggunakan GIT Reset, commit terakhir akan hilang.
``` Git revert -n <nomer commit> ```

# GIT BRANCH
Fitur yang WAJIB digunakan jika berkolaborasi dengan developer atau dalam tim. Untuk menghindari conflict code yang dikembangkan. Kita tidak boleh berkolaborasi dalam project di satu branch yang sama!

Misalnya Bowo akan mengerjakan fitur A dan Gigih mengerjakan fitur B. Masing-masing fitur harus dibuat branch masing-masing. Tidak boleh mengganggu branch ‘master’ yang sudah terupdate

Untuk membuat branch, gunakan perintah berikut ini
``` git branch <branch> ```

Untuk menuju kedalam suatu branch tertentu. Gunakan perintah seperti berikut ini:
``` git checkout nama_branch ```

Untuk menghapus sebuah branch, gunakan perintah seperti berikut ini:
``` git branch -d <nama_branch> ```

# GIT MERGE
Setelah membuat branch baru, lalu lakukan commit.Saatnya kita menyatukan pekerjaan ke master file/branch utama yaitu branch MASTER

Untuk menyatukan branch cabang yang telah kita kembangkan. Gunakan perintah seperti berikut ini:
1. Harus checkout dahulu ke branch master
``` git checkout master ```
2. Lalu lakukan merge
``` git merge nama_branch ```

# Responsive Web Design
RWD atau responsive web design bertujuan agar website bisa di akses pada device apapun seprti smartphone, laptop, dan tablet.

# Setting up Chrome Dev Tools
Setiap Developer wajib menggunakan tools bawaan dari setiap browser yang memudahkan proses development website. pada browser chrome biasa disebut dengan chrome dev tools.

* Akses Chrome Dev Tools menggunakan shortcut
Mac ``` x + y + j ```
Windows ``` ctrl + shift + j ```

* Add Viewport in HTML
```
<meta name="viewport" content="width=device-width, initial-scale=1.8">
```
Meta Viewport required on mobile responsive


* Use Max-Width element
Panjang image jika tidak menggunakan max-width menjadi overflow karena mengikuti width real bawaan dari file image.

# Media Query
media query digunakan untuk membuat beberapa styles tergantung pada jenis device

Jenis Media Query
* Media query untuk responsive web design umumnya hanya menggunakan 2 jenis media query
* keduanya yaitu min-width dan max-width

ada 2 cara/pattern dalam menggunakan media query
1. membuat file css berbeda untuk masing masing device
2. menggabungka 1 file CSS untuk setting styling berbagai device

# Breakpoint
perubahan yang terjadi pada tampilan saat berganti device atau ukuran width

* Complex Breakpoint Media Query
jika kita menginginkan tampilan yang ingin diterapkana pada range ukuran device tertentu, kita bisa membuatnya menjadi range media query.

# SUMMARY
* Tidak ada aturan baku besaran width dan berapa banyak breakpoint yang harus dilakukan
* Responsive web design dilakukan sesuai kebutuhan konten kita. jika konten ditampilkan sudah tidak bisa diakses atau sulit dilihat pada width tertentu saatnya kamu menggunakan media query.


# Bootstrap

Cara simple menggunakan atau pasang bootstrap
1. Buka website bootstrap
2. Pilih download
3. Cari CDN kemudian tinggal copy linknya
4. kemudian pasang didalam head

# Layout
# Breakpoints
* Breakpoint adalah lebar yang dapat disesuaikan yang menentukan bagaimana tata letak responsif Anda berperilaku di seluruh perangkat atau ukuran viewport di Bootstrap.
* Memiliki beberapa breakpoints contoh medium dengan ukuran >=760px
* Setiap breakpoint dipilih untuk menampung container dengan lebar kelipatan 12 dengan nyaman. Breakpoint juga mewakili subset ukuran perangkat umum dan dimensi area pandang—tidak secara spesifik menargetkan setiap kasus penggunaan atau perangkat. Sebaliknya, rentang memberikan fondasi yang kuat dan konsisten untuk dibangun di hampir semua perangkat.
# Container
blok bangunan dasar Bootstrap yang berisi, melapisi, dan menyelaraskan konten Anda dalam perangkat atau area pandang tertentu.

Container adalah elemen tata letak paling dasar di Bootstrap dan diperlukan saat menggunakan sistem grid default kami . Wadah digunakan untuk menampung, melapisi, dan (terkadang) memusatkan konten di dalamnya. Meskipun container dapat disarangkan, sebagian besar tata letak tidak memerlukan container bersarang.

Bootstrap hadir dengan tiga wadah berbeda:
* .container, yang menetapkan a max-widthpada setiap breakpoint responsif
* .container-{breakpoint}, yaitu width: 100%sampai breakpoint yang ditentukan
* .container-fluid, yang width: 100%sama sekali breakpoints

# Grid System
Gunakan kisi flexbox mobile-first kami yang kuat untuk membangun tata letak dari semua bentuk dan ukuran berkat sistem dua belas kolom, enam tingkat responsif default, variabel Sass dan mixin, dan lusinan kelas yang telah ditentukan sebelumnya.

* CONTOH
Sistem grid Bootstrap menggunakan serangkaian wadah, baris, dan kolom untuk tata letak dan menyelaraskan konten. Itu dibangun dengan flexbox dan sepenuhnya responsif.

Bagaimana grid system bekerja
* Grid kami mendukung enam breakpoint responsif . Titik henti sementara didasarkan pada min-widthkueri media, yang berarti titik henti tersebut memengaruhi titik henti sementara itu dan semua yang ada di atasnya (misalnya, .col-sm-4berlaku untuk sm, md, lg, xl, dan xxl). Ini berarti Anda dapat mengontrol ukuran dan perilaku penampung dan kolom dengan setiap titik henti sementara
* Pusat wadah dan isi konten Anda secara horizontal. Gunakan .containeruntuk lebar piksel responsif, .container-fluiduntuk width: 100%semua area pandang dan perangkat, atau wadah responsif (misalnya, .container-md) untuk kombinasi lebar piksel dan lancar.
* Baris adalah pembungkus untuk kolom. Setiap kolom memiliki horizontal padding(disebut talang) untuk mengontrol ruang di antara mereka. Ini paddingkemudian dilawan pada baris dengan margin negatif untuk memastikan konten di kolom Anda sejajar secara visual di sisi kiri. Baris juga mendukung kelas pengubah untuk menerapkan ukuran kolom dan kelas selokan secara seragam untuk mengubah jarak konten Anda.
* Kolom sangat fleksibel. Ada 12 kolom template yang tersedia per baris, memungkinkan Anda untuk membuat kombinasi elemen yang berbeda yang mencakup sejumlah kolom. Kelas kolom menunjukkan jumlah kolom template yang akan direntang (mis., col-4rentang empat). widths diatur dalam persentase sehingga Anda selalu memiliki ukuran relatif yang sama.
* Kolom juga responsif dan dapat disesuaikan. Kelas selokan tersedia di semua titik henti sementara, dengan semua ukuran yang sama dengan margin dan spasi padding kami . Ubah talang horizontal dengan .gx-*kelas, talang vertikal dengan .gy-*, atau semua talang dengan .g-*kelas. .g-0juga tersedia untuk menghapus talang.
* Variabel Sass, peta, dan mixin memberi daya pada grid. Jika Anda tidak ingin menggunakan kelas grid yang telah ditentukan sebelumnya di Bootstrap, Anda dapat menggunakan Sass sumber grid kami untuk membuat markup semantik Anda sendiri. Kami juga menyertakan beberapa properti kustom CSS untuk menggunakan variabel Sass ini untuk fleksibilitas yang lebih besar bagi Anda.

# Columns
* Kolom dibangun di atas arsitektur flexbox grid. Flexbox berarti kami memiliki opsi untuk mengubah kolom individual dan memodifikasi grup kolom pada tingkat baris . Anda memilih bagaimana kolom tumbuh, menyusut, atau berubah.
* Saat membangun tata letak kisi, semua konten masuk dalam kolom. Hirarki kisi Bootstrap beralih dari wadah ke baris ke kolom ke konten Anda. Pada kesempatan yang jarang, Anda dapat menggabungkan konten dan kolom, tetapi perlu diketahui bahwa mungkin ada konsekuensi yang tidak diinginkan
* Bootstrap menyertakan kelas yang telah ditentukan sebelumnya untuk membuat tata letak yang cepat dan responsif. Dengan enam breakpoint dan selusin kolom di setiap tingkat kisi, kami memiliki lusinan kelas yang telah dibuat untuk Anda membuat tata letak yang diinginkan. Ini dapat dinonaktifkan melalui Sass jika Anda mau.

# Component
tinggal pilih component mana kemudian pasang ke website kita. Misal ingin menggunakan navbar
1. pilih navbar pada website bootstrap
2. kemudian copy syntax yang ada didalamnya
3. lalu paste kan pada html body












