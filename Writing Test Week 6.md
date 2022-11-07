# BACK END DEVELOPMENT
* Secara teknologi, Back-end adalah segala macam teknologi yang ada di sisi server dari sebuah website atau aplikasi. 
* Back-end developers dapat memilih dari sekian banyak bahasa pemrograman mulai dari C++, Javascript, java, phyton dsb ,tergantung pada jenis aplikasi apa yang dibuat.
* Server adalah sebuah jaringan komputer yang menyediakan jenis layanan tertentu (service) pada komputer lain. Server dilengkapi dengan sistem operasi khusus, yang disebut sebagai Sistem Operasi Jaringan/Network Operating System. Secara sederhana, server bekerja atas permintaan dari sebuah klien.
* Database dapat didefinisikan sebagai kumpulan data yang disimpan secara sistematis di dalam komputer yang dapat diolah dan dimanipulasi. Database adalah kumpulan informasi yang disimpan didalam komputer secara sistematik dan saling berelasi. Database bisa juga disebut sebagai gudang penyimpanan data untuk diolah lebih lanjut. Untuk membuat Database diperlukan sebuah software yang dinamakan dengan DBMS(Database Management System)
* APIs: Application Programming Interfaces. API adalah sekumpulan instruksi program dan protokol yang digunakan untuk membangun aplikasi perangkat lunak. REST API bertugas sebagai penghubung/perantara antara Front-End dan Back-end untuk saling bertukar informasi(request dan response).
* MERN adalah salah satu kombinasi teknologi antara front-end dan back-end untuk membuat aplikasi website. MERN adalah singkatan dari MongoDB, Express, React, dan NodeJS. Teknologi Full-stack yang menggunakan 1 bahasa yaitu Javascript. Segala kegiatan pengembangan menggunakan bahasa Javascript, Mendukung arsitektur MVC (Model View Controller) untuk membuat proses pengembangan lebih lancar dan terstruktur, Dengan semua teknologi menggunakan Javascript, maka developer hanya perlu menguasai Javascript dan JSON, Open source framework dengan dukungan komunitas yang besar dan baik.

# MYSQL BASIC
## Apa Itu Database?
Database adalah kumpulan terorganisir dari informasi terstruktur, atau data, biasanya disimpan secara elektronik dalam sistem komputer. Sebuah database biasanya dikendalikan oleh sistem manajemen database (DBMS). Bersama-sama, data dan DBMS, bersama dengan aplikasi yang terkait dengannya, disebut sebagai sistem basis data, sering disingkat menjadi basis data saja.

Data dalam tipe database paling umum yang beroperasi saat ini biasanya dimodelkan dalam baris dan kolom dalam serangkaian tabel untuk membuat pemrosesan dan kueri data menjadi efisien. Data kemudian dapat dengan mudah diakses, dikelola, dimodifikasi, diperbarui, dikendalikan, dan diatur. Sebagian besar database menggunakan bahasa kueri terstruktur (SQL) untuk menulis dan meminta data.
## Database Management System (DBMS)
Data dalam tipe database paling umum yang beroperasi saat ini biasanya dimodelkan dalam baris dan kolom dalam tabel untuk membuat data efisien dan kueri. Data kemudian dapat dengan mudah diakses, dikelola, dikendalikan, dikendalikan, dan diatur. sebagian besar database menggunakan bahasa kueri terstruktur (SQL) untuk menulis dan meminta data.

## Apa itu MySQL?
MySQL adalah sistem manajemen basis data relasional open source berbasis SQL. Itu dirancang dan dioptimalkan untuk aplikasi web dan dapat berjalan di platform apa pun. Sebagai persyaratan baru dan berbeda muncul dengan internet, MySQL menjadi platform pilihan untuk pengembang web dan aplikasi berbasis web.

## Kenapa Harus Belajar MySQL?
* Propabilitas: MySQL dapat berjalan stabil pada berbagai sistem operasi seperti Windows, Linux, MacOS dll.
* Open Source : MySQL didistribusikan sebagai open source sehingga dapat digunakan secara gratis.
* Multi User : MySQL dapat digunakan oleh beberapa pengguna dalam waktu yang bersamaan tanpa mengalami masalah / konflik.

## Data Type MySQL
### NUMBER
Tipe data Number adalah data yang berisi kumpulan karakter angka
* int : Tipe data untuk angka bulat ex : 1, 22, 99
* Float : Tipe data untuk angka menggunakan koma 
* Decimal : tipe data angka pecahan (desimal), dimana jumlah angka pecahan (angka di belakang koma) sudah di tentukan dari awal.

### STRING
Tipe data string adalah tipe data berupa kumpulan karakter termasuk karakter simbol
* Char : tipe data string dengan fixed length dan memori sesuai panjang yang didefinisikan
* Varchar : tipe data string dengan penyimpanan karakter yang fleksibel max 255
* Text : Tipe data string dengan penyimpanan yang lebih panjang dari varchar 
* Enum : merupakan tipe data yang khusus untuk kolom dimana nilai datanya sudah kita tentukan sebelumnya. 

### BOOLEAN
Tipe ini hanya menyimpan 2 tipe data yaitu TRUE dan FALSE, dan dapat di convert menjadi int dengan representasi TRUE = 1, dan FALSE = 0

### DATE TIME
Tipe ini merupakan tipe data untuk menyimpan tanggal dan waktu
* DATE : Tipe data untuk menyimpan tanggal 'CCYY-MM-DD'
* DATETIME : Tipe data untuk menyimpan tanggal dan waktu 'CCYY-MM-DD hh:mm:ss'
* TIME : Tipe data untuk menyimpan waktu 'hh:mm:ss'
* timestamp : Time data untuk menyimpan tanggal dan waktu dan juga UTC nya atau timezone 'CCYY-MM-DD hh:mm:ss +00:00'

### DEFAULT
Tipe data untuk set default value jika tidak di assign dengan value

### NULL
Tipe data kosong atau tipe data yang belum di assign dengan value / data

## KEY
### PRIMARY KEY
Primary Key disebut juga dengan Kunci Primer. Kunci Primer tersebut dipilih sebagai identifikasi untuk membedakan satu baris dengan baris lainnya dalam suatu tabel. Pada dasarnya, setiap tabel hanya memiliki satu primary key saja.

Bentuk perintah dasar untuk membuat Primary Key dalam SQL adalah :
```
Colum data_type1 PRIMARY KEY
```

### Foreign Key
foreign key dapat diartikan sebagai kunci asing. Definisi tersebut juga berlaku dalam pengolahan relasional database. Kunci asing (Foreign Key) adalah sebuah atribut atau gabungan atribut yang terdapat dalam suatu tabel yang digunakan untuk menciptakan hubungan (relasi) antara dua tabel

## Case Study
Database sebuah Book Store. Key point dalam sebuah Book Store Application adalah mencatat setiap transaksi pembelian buku oleh customer Setiap transaksi pembelian buku harus tersimpan data sebagai berikut : Tanggal transaksi, id transaksi, buku

## SQL COMMAND
### Database Command
* Command ini digunakan untuk menunjukkan seluruh list database di mysql kita
```
SHOW DATABASES;
```
* Command ini digunakan untuk membuat database baru 
```
CREATE DATABASE bookstore;
```
* Command ini digunakan untuk menggunakan database yang sudah ada
```
USE bookstore;
```
* Command ini digunakan untuk menghapus / menghilangkan database yang dipilih dari MySQL kita
```
DROP DATABASES bookstore;
```

### Table Command
Setelah masuk ke database yang dipilih, kita bisa menggunakan command untuk memodifikasi table di database tersebut, salah satunya adalah SHOW, untuk melihat semua ini table di database
```
SHOW TABLES;
```
membuat table baru di database tersebut dengan nama “books”. Sintaks yang dibuat menggunakan CREATE TABLE [name] dan memberikan definisi tiap kolom di table tersebut.
``` 
CREATE TABLE books {
    id INT(10) AUTO_INCREMENT PRIMARY KEY,
    author1 VARCHAR(100) NOT NULL,
    author2 VARCHAR(100),
    author3 VARCHAR(100),
    title VARCHAR(100) NOT NULL,
    description TEXT,
    place_sell CHAR(3),
    stock INT DEFAULT(0),
    creation_date TIMESTAMP DEFAULT CURRENT_TIMESTAP ON UPDATE CURRENT_TIMESTAMP
};
```
menggunakan DROP untuk menghapus table yang diinginkan jika ingin dihapus.
```
DROP TABLES books;
```

menambah atau menghilangkap kolom di table yang dipilih, kita bisa menggunakan ALTER dan menggunakan ADD untuk menambah kolom atau DROP COLUMN untuk menghapus kolom seperti contoh diatas.
```
ALTER TABLE books
ADO price INT,
    Status ENUM('available','out of stock','limited');

ALTER TABLE books
DROP COLUMN place_sell;
```

### INSERT INTO 
menambah atau menghilangkap kolom di table yang dipilih, kita bisa menggunakan ALTER dan menggunakan ADD untuk menambah kolom atau DROP COLUMN untuk menghapus kolom seperti contoh diatas.
```
INSERT INTO books
    (id, author1, author2, author3, title, description, stock, creation_date, price, status)
    VALUES (1,'jaya','agung','setya','buku dongeng', 'ini adalah buku ....', 10, '2021-10-10 10:10:10', 50000, 'available');
```
menambah lebih dari 1 atau multiple kita dapat menggunakan query INSERT INTO lebih dari 1 assign values
```
NSERT INTO books
    (id, author1, author2, author3, title, description, stock, creation_date, price, status)
    VALUES 
        (2,'jaya','rendi','','buku 2', 'ini adalah buku ....', 10, '2021-10-10 10:10:10', 50000, 'available', 100),
        (3,'jaya','rendi','','buku 3', 'ini adalah buku ....', 10, '2021-10-10 10:10:10', 40000, 'available', 25),
        (4,'jaya','rendi','','buku 4', 'ini adalah buku ....', 10, '2021-10-10 10:10:10', 45000, 'available', 50);
```

### SELECT
Command SELECT digunakan untuk melakukan query melihat isi seluruh data di table yang dipilih
```
SELECT * FROM books;
```
 Dapat melakukan query untuk beberapa kolom yang ingin dilihat seperti query diatas, jadi kita ingin melihat id, author1, author2, author3 di table books
```
SELECT id, author1, author2, author3 FROM books;
```
menggunakan alias / AS untuk menggunakan mengubah nama kolom agar output kolomnya sesuai dengan yang kita inginkan
```
SELECT id AS ID, author1 AS A1, author2 AS A2, author3 AS A3 FROM books;
```

### WHERE
Query WHERE digunakan untuk mencari data dengan kondisi tertentu dengan command WHERE [column_name] = condition . Contoh diatas kita melakukan query dengan id = 1
```
SELECT*FROM books WHERE id=1;
```
menggunakan WHERE lebih dari 1 parameter kondisi menggunakan IN. Contoh diatas kita query dengan kondisi id = 1 dan 2. 
```
SELECT*FROM books WHERE id IN (1,2);

### AND, OR, NOT
mengkolaborasikan WHERE menggunakan kondisi lebih dari  1 menggunakan AND, OR dan NOT. Contoh dibawah kita menggunakan AND untuk mencari kondisi id = 1 dan author1 = ‘jaya’ maka kita akan memunculkan row dengan 2 kondisi tersebut.
```
SELECT*FROM books WHERE id = 1 and author1 ='jaya';
```
menggunakan OR untuk mencari query dengan kondisi salah satu. Contoh dibawah kita akan mencari row dengan kondisi id = 1 atau author1 = ‘eddy’. Maka kita akan muncul 2 row dengan salah satu kondisi yang di declare.
```
SELECT*FROM books WHERE id = 1 and author1 ='eddy';
```
menggunakan NOT untuk mencari query yang tidak ada dalam kondisi yang di definisikan. Contoh dibawah kita mencari query yang tidak mengandung id = 1, maka muncul 3 data dengan id yang tidak sama dengan 1
```
SELECT*FROM books WHERE NOT id = 1;

### ORDER BY
command yang bisa kita gunakan untuk melakukan ordering menggunakan ORDER BY dengan menggunakan 2 kondisi yaitu ASC dan DESC. Struktur commandnya adalah ORDER BY [column_name] ASC / DESC.
```
SELECT*FROM books WHERE NOT id =1
ORDER BY id DESC;
```

### GROUP BY
``` 
SELECT * FROM books WHERE NOT id=1
GROUP BY id;
```

### LIMIT
Command LIMIT digunakan untuk membatasi berapa query yang akan dimunculkan dengan urutan dari atas. Contoh diatas adalah kita query dan memunculkan hanya 2 data.
```
SELECT * FROM books
LIMIT 2;
```

### UPDATE
Command UPDATE digunakan untuk melakukan perbaruan data di table. Contoh dIBAWAH adalah kita melakukan update data author1 dan title di row id = 1.
```
UPDATE books
SET author1='pratama', title='buku 1'
WHERE id=1;
```

### DELETE
Command DELETE digunakan untuk melakukan penghapusan data. Contoh diBAWAH kita melakukan penghapusan data di id = 1. ketika ingin melakukan delete jangan lupa menggunakan WHERE agar semua data tidak terhapus
```
DELETE FROM books
WHERE id = 1;
```

## DATABASE NORMALIZATION
Merupakan teknik analisis data yang mengorganisasikan atribut-atribut data dengan cara mengelompokkan sehingga terbentuk entitas yang non-redundant, stabil, dan fleksible. 
### Tujuan database normalization
- Menghilangkan redundan data pada database.
- Memudahkan juka ada perubahan struktur table database.
- Memperkecil pengaruh jika ada perubahan dari struktur table database.

### Efek jika tidak melakukan database normalization
- INSERT Anomali : Situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
- DELETE Anomali : Penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
- UPDATE Anomali : Situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.

### Bentuk Database Normalization
* First Normal Form (1NF)
    - Menghilangkan multiple value pada sebuah kolom table database
    - Sebuah table memenuhi kaidah 1NF jika :
        - Setiap kolom bernilai tunggal (single value)
        - Setiap kolom memiliki nama yang unik
        - Urutan penyimpanan data tidak menjadi masalah

* Second Normal Form
    - Harus sudah dalam bentuk 1NF untuk mendapatkan 2NF
    - Menghapus beberapa subset data yang ada pada tabel dan menempatkan mereka pada tabel terpisah.

* Third Normal Form
Menghilangkan seluruh atribut atau field yang tidak berhubungan dengan primary key. Dengan demikian tidak ada ketergantungan transitif pada setiap kandidat key.

Masih ada banyak bentuk database normalisasi, diantaranya  EKNF, BCNF, 4NF, 5NF, DKNF, 6NF

## Keys di SQL
* Super key : Kumpulan dari satu atau lebih dari satu key yang dapat digunakan untuk mengidentifikasi record secara unik dalam sebuah tabel.
* Candidate Key : kumpulan satu atau lebih fields/columns yang dapat mengidentifikasi record secara unik dalam tabel. Bisa jadi ada beberapa Candidate Keys di dalam satu tabel Setiap Candidate Key bisa digunakan sebagai Primary Key. Candidate Key adalah super key yang tidak mempunyai value yang berulang
* Primary Key : kumpulan satu atau lebih fields/columns dari sebuah tabel yang secara unik mengidentifikasi sebuah record dalam tabel database. Valuenya tidak boleh berupa null ataupun duplicate value. Hanya boleh salah satu Candidate Key yang bisa menjadi Primary Key.
* Alternate Key : key yang bisa digunakan menjadi primary key. Pada dasarnya, Key ini merupakan candidate key yang tidak dijadikan  primary key.
* Unique key : Kumpulan dari satu atau lebih fields/columns di sebuah table database yang secara unik mengidentifikasi sebuah record dalam table database tersebut. Hampir sama dengan Primary key, namun value dari Unique Key bisa berupa satu buah null value di dalam sebuah table database, dan Unique Key tidak bisa memiliki duplicate values
* Foreign Key : Field di sebuah table database yang menjadi Primary Key di table database lain. Value dari Foreign key bisa menerima multiple null dan duplicate values.

## Join Multiple Tables
Mengambil records dari dua atau lebih table database yang memiliki relationship dan akan di sajikan dalam single result set.

### JOIN
* Semua baris akan diambil dari kedua table yang akan di JOIN, selama columns cocok dengan kondisi yang sudah di tentukan.
* Memungkinkan baris dari salah satu tabel muncul di hasil jika dan hanya jika kedua tabel memenuhi kondisi yang ditentukan dalam klausa ON.
```
SELECT column_name(s)
From table1
INNER JOIN table2
ON table1.column_name = table2.colomn_name;
```

### LEFT JOIN
* Pada JOIN ini, semua records dari table di sisi kiri JOIN statement akan di pilih.
* Jika record yang di pilih dari table kiri tidak memiliki record yang cocok pada table JOIN yang kanan, maka record tersebut masih dipilih, dan kolom pada table yang kanan akan bernilai NULL. 
```
SELECT column_name(s)
From table1
LEFT JOIN table2
ON table1.column_name = table2.colomn_name;
```

### RIGHT JOIN
Pada JOIN ini, semua records dari table di sisi kiri JOIN statement akan di pilih, bahkan jika table di sebelah kiri tidak memiliki record yang cocok.
```
SELECT column_name(s)
From table1
RIGHT JOIN table2
ON table1.column_name = table2.colomn_name;
```

## Aggregate Functions
Mengambil satu nilai setelah melakukan perhitungan pada sekumpulan nilai
### MAX
fungsi mengembalikan nilai terbesar dari kolom yang dipilih.
```
SELECT MAX (column_name)
FROM table_name
WHERE condition
```

### MIN
fungsi mengembalikan nilai terkecil dari kolom yang dipilih.
```
SELECT MIN (column_name)
FROM table_name
WHERE condition
```

### SUM
fungsi mengembalikan jumlah total kolom numerik.
```
SELECT SUM (column_name)
FROM table_name
WHERE condition
```

### COUNT
fungsi mengembalikan jumlah baris yang cocok dengan kriteria yang ditentukan.
```
SELECT COUNT (column_name)
FROM table_name
WHERE condition
```

### AVG
fungsi mengembalikan nilai rata-rata kolom numerik
```
SELECT AVG (column_name)
FROM table_name
WHERE condition
```

## UNION
- Digunakan untuk menggabungkan kumpulan hasil dari dua atau lebih pernyataan SELECT.
- Setiap pernyataan SELECT dalam UNION harus memiliki jumlah kolom yang sama
- Kolom juga harus memiliki tipe data yang serupa
- Kolom dalam setiap pernyataan SELECT juga harus dalam urutan yang sama
```
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

## HAVING
HAVING ditambahkan ke SQL karena kata kunci WHERE tidak dapat digunakan dengan aggregate functions.
```
SELECT column_name(s)
FROM table_name
WHERE table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

## LIKE & Wilcards
- Operator LIKE digunakan dalam klausa WHERE untuk mencari pola tertentu dalam kolom.
- Karakter wildcard digunakan untuk menggantikan satu atau lebih karakter dalam sebuah string.
```
SELECT column1, column2, ...
FROM table_name
WHERE column LIKE patters;
```

# Authentication & Authorization in Express
## AUTENTICATION
Otentikasi adalah verifikasi siapa Anda. Misalnya, katakanlah Anda pergi ke konser. Di pintu depan, penjaga keamanan meminta untuk melihat tiket dan ID Anda untuk memverifikasi bahwa nama di ID Anda cocok dengan nama di tiket Anda.
Otentikasi bergantung pada satu atau lebih faktor untuk memverifikasi identitas, dan faktor-faktor ini datang dalam tiga jenis utama:
* Pengetahuan adalah sesuatu yang Anda ketahui, seperti nama pengguna dan kata sandi.
* Kepemilikan adalah sesuatu yang Anda miliki, seperti kartu keamanan atau perangkat seluler
* Inheren adalah sesuatu tentang Anda, yang umumnya mengacu pada data biometrik seperti sidik jari.
Otentikasi yang bergantung pada satu faktor, seperti kombinasi nama pengguna/sandi sederhana, disebut Otentikasi Satu Faktor, dan menjadi semakin tidak aman.

## AUTORIZATION
* Otorisasi adalah verifikasi atas apa yang boleh Anda lakukan. Kembali ke contoh konser kami, setelah penjaga keamanan mengautentikasi Anda, Anda kemudian memberikan tiket Anda ke penjaga keamanan lain yang kemudian hanya mengizinkan Anda masuk ke Penerimaan Umum (bukan bagian VIP). 
* Otorisasi sangat penting untuk keamanan web, dan bertanggung jawab atas segala hal mulai dari mencegah pengguna memodifikasi akun satu sama lain, melindungi aset back-end dari penyerang, hingga memberikan akses terbatas ke layanan eksternal.
* Otorisasi yang baik akan memungkinkan Anda membatasi pengguna dan layanan untuk hak istimewa yang mereka butuhkan; hanya karena seorang pengguna berwenang untuk mengelola satu grup tidak berarti mereka harus dapat mengelola semua grup, misalnya.

## ENCRYPTION
Salah satu alat inti untuk menegakkan otentikasi dan otorisasi adalah enkripsi. Enkripsi adalah proses mengubah data menjadi format yang tidak dapat dibaca kecuali Anda memiliki kunci yang benar untuk mendekripsinya. Enkripsi datang dalam dua jenis utama:
* Symmetric encryption
* Asymmetric encryption

### Detail Autentikasi
Tanggapan terhadap perintah autentikasi dapat dikategorikan ke dalam:
* Knowledge-Based: “Something You Know” contoh password, pin etc
* Possession-Based: “Something You Have” contoh phone or smart card
* Inherence-Based: “Something You Are” contoh fingerprint

## Web Session
Sesi web mengacu pada serangkaian interaksi pengguna selama jangka waktu tertentu. Data sesi disimpan di sisi server dan dikaitkan dengan ID sesi.
Pikirkan sesi sebagai memori jangka pendek untuk aplikasi web. Pada latihan berikutnya, kami akan menjelaskan di mana pengidentifikasi sesi ini disimpan sehingga browser (klien) dapat terus mengambil data sesi yang sama di antara pemuatan halaman yang berbeda.

## Session & Cookie
Agak kikuk bagi klien untuk mengingat untuk menempelkan ID sesi ke setiap permintaan. Karena itu, ID sesi sering disimpan di sisi klien dalam bentuk cookie sesi.
Cookie adalah potongan kecil data — file teks berukuran maksimal 4kb — browser menyimpan yang secara otomatis dikirim dengan permintaan HTTP ke aplikasi web. Cookie disetel oleh header respons HTTP dalam pasangan nilai kunci:
```
Set-Cookie: key=Velue
```
```
Set-Cookie: sessionID=34jgL79b
```
Ini kira-kira bagaimana sesi diimplementasikan dengan cookie:
1. Seorang pengguna pergi ke sebuah situs. Server web membuat sesi dan ID sesi.
2. Dalam respons server, ini memberi tahu browser untuk menyimpan cookie dengan ID sesi (tidak boleh menyertakan informasi pribadi apa pun).
3. Cookie ID sesi secara otomatis dilampirkan ke setiap permintaan HTTP berikutnya ke server.
4. Saat server membaca cookie ID sesi yang dikirim dengan permintaan HTTP berikutnya, server akan mengembalikan data sesi yang terkait dengan ID tersebut.
5. Proses berlanjut selama sesi aktif.
6. Cookie sesi dan ID sesi kedaluwarsa setelah pengguna menutup browser, logout, atau durasi sesi yang telah ditentukan (yaitu satu jam) berlalu.

## Cookie Security
Cookie sering kali menyimpan informasi sensitif, terutama saat digunakan dalam manajemen sesi. Cookie juga digunakan untuk menyimpan preferensi atau riwayat pribadi pengguna, yang juga harus tetap aman. 

Langkah pertama untuk mengamankan cookie dapat menambahkan tanggal kedaluwarsa atau durasi sehingga cookie tidak bertahan lebih lama dari yang dibutuhkan.Kami dapat menentukan informasi tersebut melalui header Set-Cookie dalam respons HTTP seperti:
```
Set-Cookie: Key=Value, expirea=monday, 29-Nov-2021 07:30:10 GMT
```
Atribut HttpOnly untuk header Set-Cookie memastikan bahwa data cookie tidak dapat diakses oleh skrip yang menjalankan sisi klien. Ini membantu mencegah serangan Cross-Site Scripting (XSS) yang mencoba mencuri cookie sesi dan mengambil alih milik korban. sesi, yang sangat umum.
```
Set-Cookie: Key=Value, expirea=monday, 29-Nov-2021 07:30:10 GMT; HTTPOnly
```

## Token Based Authentication using JWT
Token Web JSON adalah objek JSON mandiri yang secara kompak dan aman mengirimkan informasi antara dua pihak. Mereka aman karena ditandatangani secara digital menggunakan rahasia atau pasangan kunci publik/pribadi.
Sebagai pengingat, JSON, atau Notasi Objek JavaScript, pada dasarnya adalah versi objek Javascript yang sedikit lebih ketat.

Objek JSON harus diapit kurung kurawal dan dapat berisi satu atau lebih pasangan nilai kunci.
```
{
    "name": "Dave",
    "age" : 20
    "country": "Indonesia"
}
```
komponen JWT Header, Payload, dan Signature.

### JWT Header
Header JWT berisi jenis token yang kami buat dan algoritma penandatanganan yang akan digunakan.

Jenis: Jenis token ini akan selalu "JWT". Internet Assigned Numbers Authority, atau IANA, mengoordinasikan sumber daya protokol internet di seluruh dunia. Jenis "JWT" ​​sejajar dengan jenis media "application/jwt".

Algoritma: Penandatanganan, atau hashing, algoritma yang digunakan mungkin berbeda. ES256".
```
{
    "alg": "HS256",
    "typ": "JWT"
}
```

### JWT Payload
Payload JWT berisi klaim tentang suatu entitas. Ada tiga jenis klaim yang dapat dikandung oleh muatan JWT:
* Klaim Terdaftar: Ini adalah jenis klaim yang telah ditentukan sebelumnya yang dapat digunakan siapa saja di JWT.
* Klaim Publik: Ini adalah jenis klaim khusus yang dibuat oleh pengembang dan dapat digunakan secara publik.
* Klaim Pribadi: Ini adalah jenis klaim khusus yang tidak terdaftar atau publik.
```
{
    'sub': '1234567890',
    'name': 'Terra',
    'admin': false,
    'iat': 1620924478,
    'exp': 1620939187
}
```

### JWT Signature
Tanda tangan JWT digunakan untuk memverifikasi bahwa JWT tidak dirusak atau diubah. Itu dapat dibuat dengan mengambil header yang dikodekan, muatan yang dikodekan, rahasia, dan menggunakan algoritma hashing untuk membuat hash dari elemen-elemen tersebut.

Rahasianya adalah kunci simetris yang diketahui oleh pengirim dan penerima token ini.

Sekarang kami telah menyimpan informasi pengguna kami di JWT kami, apa yang kami lakukan dengannya?Bagaimana kami menggunakan informasi di JWT kami saat berkomunikasi dengan server kami?
1. Pengguna masuk ke situs web dan informasi mereka dikirim ke server.
2. Server membuat JWT dengan rahasia
3. JWT dikembalikan ke browser
4. Pengguna membuat permintaan lain, dan browser mengirimkan JWT kembali ke server di header Otorisasi menggunakan skema Bearer.
5. Dengan JWT kami yang baru dibuat, ini akan terlihat seperti:
6. Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkhhcmluZSBDb29wZXIiLCJhZG1pbiI6ZmFsc2UsImlhdCI6MTYyMDkyNDQ3OCwiZXhwIjoxNjIwOTM5MTg3fQ.3B-FLgPETrExxlDKW30AoU7KGE6xuZodw79TQR8_mwM
7. Server memverifikasi tanda tangan JWT dan mendapatkan informasi pengguna dari JWT.
8. Server akan mengirimkan respon kembali ke browser.

Untuk menjaganya tetap aman, Anda harus selalu menyimpan JWT di dalam cookie httpOnly Ini adalah jenis cookie khusus yang hanya dikirim dalam permintaan HTTP ke server.

## Password Authentication (Bcrypt)
Saat mempraktikkan konsep baru, kita mungkin menyimpan kata sandi plaintext dalam database lokal, tetapi ini sangat tidak aman. Seseorang tidak boleh melakukan ini di lingkungan produksi. Ada banyak fungsi hashing kriptografi untuk dipilih, seperti SHA-3 atau MD -5 Algoritma SHA-3 dan MD-5 dikenal cukup cepat.

Sayangnya, semakin cepat fungsinya, semakin cepat peretas dapat mengambil kata sandi hash melalui serangan brute force. Jadi, menggunakan fungsi yang lebih lambat dalam hashing kata sandi sebenarnya dapat melindungi pengguna Anda. Kita dapat melakukannya dengan menggunakan algoritme dan pustaka bcrypt. bcrypt adalah algoritma hashing

Fungsi hash hanya berfungsi satu arah, yang berarti bahwa sekali nilai di-hash tidak dapat di-unhash, artinya Anda tidak dapat dengan mudah mengambil kata sandi plaintext tanpa mengetahui salt, rounds, dan key (password)

Ini berbeda dengan enkripsi, karena, jika Anda mengetahui algoritma mana yang digunakan untuk mengenkripsi suatu nilai, Anda dapat menggunakan algoritma yang sama untuk mendekripsinya.

### Hast + Salt
Salt adalah nilai acak yang ditambahkan ke input fungsi hashing untuk membuat setiap hash kata sandi unik bahkan dalam contoh dua pengguna memilih kata sandi yang sama.

Salt membantu kami mengurangi serangan tabel hash dengan memaksa penyerang untuk menghitung ulang mereka menggunakan garam untuk setiap pengguna. bcrypt adalah algoritma hashing + salt

# Javascript Authentication and with Passport JS
## Passport JS
* Passport JS adalah middleware authentication untuk Node.JS. Passport JS sangat fleksibel dan modular.
* Passport dapat dengan mudah digunakan ke aplikasi web berbasis Express.
* Passport juga mendukung otentikasi menggunakan nama pengguna dan kata sandi, Facebook, Twitter dan lainnya.

## JSON Web Token
JSON Web Token adalah sebuah JSON Object yang didefinisikan dalam RFC 7519 sebagai cara aman untuk mewakili sekumpulan informasi antara dua pihak.

## Redirects
Redirect biasanya digunakan untuk melanjutkan setelah authentication request.
```
app.post('/login',
    passport.authenticate('local', { successRedirect: '/', filureRedirect:'login'})
    );
```

## Flash Messages
Redirect biasanya dikombinasikan dengan Flash Messages, untuk menampilkan status informasi kepada User.
```
app.post('/login',
    passport.authenticate('local', { successRedirect: '/', filureRedirect:'login', failureFlash: true })
    );
```

## Disable Session
Pada server API biasanya membutuhkan kredensial untuk diberikan dengan setiap permintaan.
```
app.get('/api/users/me'
    passport.authenticatel('basic', { session: false}),
    function(req, ews){
        res.json({ id: req.user.id, username: req.user.username });
    })
 ```

 ## Strategies
Passport menggunakan “Strategy” untuk mengotentikasi permintaan. “Strategy” dapat memverifikasi nama pengguna dan kata sandi. Otentikasi yang didelegasikan menggunakan OAuth atau otentikasi gabungan.



