# WEB SERVER & RESTFUL API
Web server terdiri dari 2 komponen penting:
* hardware
Di sisi perangkat keras, server web adalah komputer yang menyimpan perangkat lunak server web dan file komponen situs web. (misalnya, dokumen HTML, gambar, lembar gaya CSS, dan file JavaScript) Server web terhubung ke Internet dan mendukung pertukaran data fisik dengan perangkat lain yang terhubung ke web.
* Software
Di sisi perangkat lunak, server web mencakup beberapa bagian yang mengontrol bagaimana pengguna web mengakses file yang dihosting. Minimal, ini adalah server HTTP. Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web). Server HTTP dapat diakses melalui nama domain situs web yang disimpannya, dan mengirimkan konten situs web yang dihosting ini ke perangkat pengguna akhir.
![image.png]( {https://drive.google.com/file/d/1n1dJyG-0xuzNcQt42s16JyRyvjk5WPUI/view?usp=share_link} )

## Static Web Server 
Server web statis, atau tumpukan, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kami menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser Anda.
## Dynamic Web Server
A dynamic web server consists of a static web server plus extra software, most commonly an application server and a database. We call it "dynamic" because the application server updates the hosted files before sending content to your browser via the HTTP server

## Server Side Programming
* Apa itu Pemrograman Sisi Server
Server web menunggu pesan permintaan klien, memprosesnya saat tiba, dan membalas browser web dengan pesan respons HTTP. Respons berisi baris status yang menunjukkan apakah permintaan berhasil atau tidak (mis. "HTTP/1.1 200 OK" untuk berhasil).

Isi respons yang berhasil atas permintaan akan berisi sumber daya yang diminta (misalnya halaman HTML baru, atau gambar, dll...), yang kemudian dapat ditampilkan oleh browser web.
### static sites
Diagram pada slide berikutnya menunjukkan arsitektur server web dasar untuk situs statis (situs statis adalah situs yang mengembalikan konten hard-coded yang sama dari server setiap kali sumber daya tertentu diminta). Saat pengguna ingin menavigasi ke halaman, browser mengirimkan permintaan "GET" HTTP yang menentukan URL-nya.
![image.png](https://drive.google.com/file/d/1BjIw9Pi3TugswVB5s1Wrmh6mJJ_YS7ms/view?usp=share_link)

### Dynamic Sites
Situs web dinamis adalah situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan. Di situs web dinamis, halaman HTML biasanya dibuat dengan memasukkan data dari database ke dalam placeholder di template HTML (ini adalah cara yang jauh lebih efisien untuk menyimpan konten dalam jumlah besar daripada menggunakan situs web statis).

Situs dinamis dapat mengembalikan data yang berbeda untuk URL berdasarkan informasi yang diberikan oleh pengguna atau preferensi yang disimpan dan dapat melakukan operasi lain sebagai bagian dari pengembalian respons (misalnya, mengirim pemberitahuan).

Sebagian besar kode untuk mendukung situs web dinamis harus dijalankan di server. Membuat kode ini dikenal sebagai "pemrograman sisi server" (atau terkadang "skrip back-end").
![image.png](https://drive.google.com/file/d/1tUYeAyX_WoqjJLXxFpA4yE21cClNS57R/view?usp=share_link)
* Penjelasan
1. Permintaan untuk sumber daya statis ditangani dengan cara yang sama seperti untuk situs statis (sumber daya statis adalah file apa pun yang tidak berubah —biasanya: CSS, JavaScript, Gambar, file PDF yang dibuat sebelumnya, dll.).
2. Diagram sederhana dari server web yang menggunakan pemrograman sisi server untuk mendapatkan informasi dari database dan membuat HTML dari template. Ini adalah diagram yang sama seperti pada gambaran umum Client-Server. Permintaan untuk sumber daya dinamis malah diteruskan ke kode sisi server (ditunjukkan dalam diagram sebagai Aplikasi Web).
3. Untuk "permintaan dinamis" server menafsirkan permintaan, membaca informasi yang diperlukan dari database.
4. Menggabungkan data yang diambil dengan template HTML
5. dan mengirimkan kembali respons yang berisi HTML yang dihasilkan (5,6)

## The different of Static and Dynamic Site
1. Mereka memiliki tujuan dan perhatian yang berbeda.
2. Mereka umumnya tidak menggunakan bahasa pemrograman yang sama (pengecualiannya adalah JavaScript, yang dapat digunakan di sisi server dan klien).
3. Mereka berjalan di dalam lingkungan sistem operasi yang berbeda.

## Apa yang bisa kita lakukan di sisi server?
1. Penyimpanan dan pengiriman informasi yang efisien
2. Pengalaman pengguna yang disesuaikan
3. Akses terkontrol ke konten
4. Simpan informasi sesi/status
5. Pemberitahuan dan komunikasi
6. Analisis data

## Apa REST ITU?
REST, or REpresentational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain. Sistem yang sesuai dengan REST, sering disebut sistem RESTful, dicirikan oleh bagaimana mereka tidak memiliki kewarganegaraan dan memisahkan masalah klien dan server.

Dalam gaya arsitektur REST, implementasi klien dan implementasi server dapat dilakukan secara independen tanpa saling mengetahui satu sama lain. Ini berarti bahwa kode di sisi klien dapat diubah setiap saat tanpa mempengaruhi operasi server, dan kode di sisi server dapat diubah tanpa mempengaruhi operasi klien.
Dengan menggunakan antarmuka REST, klien yang berbeda mencapai titik akhir REST yang sama, melakukan tindakan yang sama, dan menerima respons yang sama. Klien dapat berupa platform web, platform seluler, atau platform desktop.

## Komunikasi antara Klien dan Server
### Membuat Request
REST mengharuskan klien membuat permintaan ke server untuk mengambil atau mengubah data di server. Permintaan umumnya terdiri dari:
1. kata kerja HTTP, yang mendefinisikan jenis operasi apa yang harus dilakukan
2. header, yang memungkinkan klien untuk menyampaikan informasi tentang permintaan 
3. jalan menuju sumber daya
4. badan pesan opsional yang berisi data

### HTTP VERBS
1. GET — mengambil sumber daya tertentu (berdasarkan id) atau kumpulan sumber daya
2. POST — buat sumber daya baru
3. PUT — perbarui sumber daya tertentu (berdasarkan id)
4. DELETE — menghapus sumber daya tertentu dengan id

## Headers and Accept Parameters
Di header permintaan, klien mengirimkan jenis konten yang dapat diterimanya dari server. Ini disebut Accept Field, dan ini memastikan bahwa server tidak mengirim data yang tidak dapat dipahami atau diproses oleh klien. Opsi untuk tipe konten adalah Tipe MIME (atau Ekstensi Surat Internet Serbaguna)
Tipe lain dan subtipe yang umum digunakan:
1. gambar — gambar/png, gambar/jpeg, gambar/gif
2. audio — audio/wav, audio/mpeg
3. video — video/mp4, video/ogg
4. aplikasi — aplikasi/json, aplikasi/pdf, aplikasi/xml, aplikasi/octet-stream

### Contoh
Misalnya, klien yang mengakses sumber daya dengan id 23 di sumber artikel di server mungkin mengirim permintaan GET seperti ini:

GET /articles/23
Accept: text/html, application/xhtml

Accept header field dalam hal ini mengatakan bahwa klien akan menerima konten dalam teks/html atau aplikasi/xhtml.

## PATHS
Permintaan harus berisi jalur ke sumber daya tempat operasi harus dilakukan. Dalam RESTful API, jalur harus dirancang untuk membantu klien mengetahui apa yang sedang terjadi.

## Mengirim Response
### Content Types
Misalnya, ketika klien mengakses sumber daya dengan id 23 di sumber artikel dengan Permintaan GET ini:

```
GET /articles/23 HTTP/1.1
Accept: text/html, application/xhtml
```

Server mungkin mengirim kembali konten dengan header respons:

```
HTTP/1.1 200 (OK)
Content-Type: text/html
```

### Response codes
Tanggapan dari server berisi kode status untuk memperingatkan klien tentang informasi tentang keberhasilan operasi. Sebagai pengembang, Anda tidak perlu mengetahui setiap kode status (ada banyak kode status), tetapi Anda harus mengetahui kode yang paling umum dan cara penggunaannya.
1. 200 (OK) Ini adalah respons standar untuk permintaan HTTP yang berhasil.
2. 201 (CREATED) Ini adalah respons standar untuk permintaan HTTP yang menghasilkan item yang berhasil dibuat.
3. 204 (NO CONTENT) Ini adalah respons standar untuk permintaan HTTP yang berhasil, di mana tidak ada yang dikembalikan di badan respons.
4. 400 (BAD REQUEST) Permintaan tidak dapat diproses karena sintaks permintaan yang buruk, ukuran yang berlebihan, atau kesalahan klien lainnya.
5. 403 (FORBIDDEN) Klien tidak memiliki izin untuk mengakses sumber daya ini.
6. 404 (NOT FOUND) Sumber daya tidak dapat ditemukan saat ini. Mungkin sudah dihapus, atau belum ada.
7. 500 (INTERNAL SERVER ERROR) Jawaban umum untuk kegagalan tak terduga jika tidak ada informasi lebih spesifik yang tersedia.

* Response Codes
1. GET — return 200 (OK)
2. POST — return 201 (CREATED)
3. PUT — return 200 (OK)
4. DELETE — return 204 (NO CONTENT) Jika operasi gagal, kembalikan kode status paling spesifik yang mungkin terkait dengan masalah yang ditemui.

#### Contoh
Jika kita ingin melihat semua pelanggan, permintaannya akan terlihat seperti ini:
```
GET http://skilvul-store.com/customers
Accept: application/json
```

Header respons yang mungkin akan terlihat seperti dan diikuti oleh data pelanggan yang diminta dalam format application/json.
```
Status Code: 200 (OK)
Content-type: application/json
```

membuat pelanggan baru dengan memposting data
```
POST http://skilvul-store.com/customers
Body:
{
    "customers": {
        "nama" = "Tarra",
        "email" = terra@coding.com"
    }
}
```

Server kemudian menghasilkan id untuk objek itu dan mengembalikannya kembali ke klien, dengan header seperti:

```
201 (CREATED)
Content-type: application/json
```

Kami dapat memperbarui pelanggan itu dengan PUT data baru dan Header respons yang mungkin akan memiliki Kode Status: 200 (OK), untuk memberi tahu klien bahwa item dengan id 123 telah dimodifikasi.
``` 
PUT http://skilvul-store.com/customers/123
Body:
{
    "customers": {
        "nama" = "Tarra Skilvul",
        "email" = terra@skilvul.com"
    }
}
```

# Intro & Essential Node JS
## Apa itu NodeJS?
Node.js adalah open-source, lintas platform, back-end yang berjalan pada mesin V8 dan mengeksekusi kode JavaScript di luar browser web. Node.js memungkinkan pengembang menggunakan JavaScript untuk menulis alat baris perintah dan untuk skrip sisi server—menjalankan skrip sisi server untuk menghasilkan konten halaman web dinamis sebelum halaman dikirim ke browser web pengguna.

![image.png](https://www.google.com/url?sa=i&url=https%3A%2F%2Ftwitter.com%2Fsimform%2Fstatus%2F1315213896282669056&psig=AOvVaw3WZlYFA2Q654lSrDcsezht&ust=1667303941976000&source=images&cd=vfe&ved=0CA0QjRxqFwoTCPCOyMmzivsCFQAAAAAdAAAAABAD)

## Arsitektur Node JS 
### Single Thread
Thread dalam ilmu komputer adalah eksekusi menjalankan beberapa tugas atau program secara bersamaan. Setiap unit yang mampu mengeksekusi kode disebut thread. Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.Javascript menggunakan call stack untuk melakukan manajemen single thread. Ketika terdapat perintah baru maka akan ditambahkan (push) dan akan di keluarkan ketika perintahnya sudah selasai (pop).

### Event Loop
Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread

Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi.

Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.

### Server side scripting
Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. 
Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”. 
``` >console.log("Hello World");
Hello World
```

## Javascript For Node JS
### Arrow Expression
Arrow expression merupakan fitur terbaru dari javascript, yaitu mempermudah membuat sintaks function menggunakan “=>” 
```
// non arrow function
function countLength(val1, val2) {
    return val1.length + val2.length
}

// using arrow function
const countLengthChar + (val1, val2) => return vall.length + val2.length
```

### Asynchronous
Asynchronous merupakan konsep yang paling penting dari javascript. Pada dasarnya, javascript mengeksekusi code secara single thread dan berurutan baris per baris yang disebut dengan synchronous. Sedangkan asynchronous memungkinkan mengeksekusi code tanpa berurutan dengan cara “skip” code dan melanjutkan eksekusi code selanjutnya. Konsep ini menungkinkan code kita tidak terjadi blocking dan lebih efisien.
```
console.log('Hello');
setTimeout(() => { console.log('Javascript')},100)// tunda selama 100 miliseconds
console.log('Coder');

/*--------
Output :
Hello!
Coder
Javascript
---------*/
```

### JSON
JSON atau Javascript Object Notation merupakan format yang digunakan untuk menyimpan dan mengirim data menggunakan konsep object di javascript. JSON dapat digunakan di hampir semua bahasa pemrograman sehingga sangat cocok untuk dipelajari
```
{"users": [
    {"username" : "Anton", "lokasi" : "Bandung"},
    {"username" : "Budi", "lokasi" : "Semarang"},
    {"username" : "Nana", "lokasi" : "Surabaya"},
    {"username" : "Jamal", "lokasi" : "Tangerang"},
]}
```

# Node JS for Back end Development
## Build In Module Node JS
### console
Console merupakan module bawaan dari javascript yang ada di node JS untuk digunakan sebagai debug atau menampilkan code secara interface
``` console.log("this is a console module from javascript")```
### process
Process adalah modules yang digunakan untuk menampilkan dan mengontrol prosess Node JS yang sedang dijalankan.
```
const process = require ('process');
const env = proces.env

env.foo = 'bar';
console.log(env.foo);

//'bar'
```

### OS
OS module merupakan module yang digunakan untuk menyediakan informasi terkait sistem operasi komputer yang digunakan user.
`
var os = require('05');
console.log("Platform: " + os.platform());
console.log("Architecture: " + os.arch());
`
### Util
Module Util merupakan alat bantu / utilities untuk mendukung kebutuhan internal API di Node JS
`
const util = require('util');
const debuglog = util.debuglog('foo');

debuglog('hello from foo [%d]', 123);

// FOO 3245: hello from foo [123]`

### Events
` const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
myEmitter.on('event',() => {
    console.log('an event occured!');
});
myEmitter.emit('event');
`

### Errors
Errors merupakan modules yang dapat digunakan untuk mendefinisikan error di Node JS sehingga lebih informatif. Kita juga dapat menghandle error menggunakan try catch
` 
// Throws with a ReferenceError because z is not defined.
try {
    const m = 1;
    const n = n + z;
} catch (err) {
    // handle the error here
}`

### Buffer
Buffer merupakan modules yang digunakan untuk mengakses, mengelola dan mengubah tipe data raw atau tipe data bytes.
` 
import { Buffer } from 'buffer';
const buf = buffer.from('hello world', 'utf8');

console.log(buf.toString('hex'));
//Prints: 68656c6c66f20776f726c64
console.log(buf.toString('base64'));
//Prints: aGVsbG8gd29ybGQ=
`

### File System
Fs atau “file system” merupakan module yang dapat membantu berinteraksi dengan file yang ada diluar code. FS paling sering digunakan untuk membaca file dengan ekstensi .txt, .csv, dan .json
' 
import { readFileSync } from 'fs';
readFileSync ('<directory>');`

### Timers
Timers merupakan modules yang digunakan untuk melakukan scheduling atau mengatur waktu pemanggilan fungsi yang dapat diatur di waktu tertentu
`
import {
    setTimeout,
} from 'timers/promises' ;

const res = await setTimeout(100, 'result');

console.log(res); //Prints 'Result'`

## Membuat Web Server Dengan Node JS
### Node JS Web Server
Node.js memiliki built-in modul yang disebut HTTP, built-in modul ini memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP).

Modul HTTP dapat membuat server HTTP yang mendengarkan port server dan memberikan respons kembali ke klien.
- Untuk menggunakan modul HTTP, gunakan require()
- Gunakan method createServer() untuk membuat server HTTP
-Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port 8080.
`
//import http build-in module
const http = require('http');

//create a server object:
http.createServer(function(req, res) {
    res.write('Hello Skilvul!');
    res.end();
}) listen(8080); // the server object listens on port 8080`

### Menambahkan HTTP Header
- Kita bisa menggunakan method res.writeHead() untuk menambahkan header HTTP.
- Argumen pertama dari method res.writeHead() adalah status code, 200 berarti semuanya OK
- Argumen kedua adalah objek yang berisi header respons.
- Contoh : 
Jika respons dari server HTTP seharusnya ditampilkan sebagai HTML, maka kita harus menambahkan header HTTP dengan tipe konten yang benar
`
const http = require('http');

http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type' : 'text/html'});
    res.write('Hello Skilvul!');
    res.end
}).listen(8080);`

- Respons yang dikembalikan dari HTTP web server bisa dalam berbagai format.
- Contohnya, Kita bisa mengembalikan response dalam format JSON dan HTML, namun kita juga dapat mengembalikan format teks lain seperti XML dan CSV.
- Selain itu web server dapat mengembalikan data non-teks seperti PDF, file zip, audio, dan video.
- Format ini harus ditambahkan kedalam HTTP Header.

### Membaca Query String
- Callback function pada method http.createServer() memiliki argumen req yang mewakili request dari klien, sebagai objek (objek http.IncomingMessage).
- Objek ini memiliki sebuah properti yang disebut "url" yang menyimpan informasi url yang sedang mengakses.
`
const http = require('http');

http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type' : 'text/html'});
    res.write('Hello Skilvul!');
    res.end
}).listen(8080);`
- Ketika server di jalankan, kemudian kita akses dari browser ke url : http://localhost:8080/skilvul
maka akan tampil tulisan skilvul.
- Ketika server di jalankan, kemudian kita akses dari browser ke url : http://localhost:8080/javascript
maka akan tampil tulisan javascript.

### Split Query String
- Ada build-in module yang bisa kita gunakan untuk split query string menjadi beberapa bagian yang dapat dibaca.
- Build-in modulenya adalah URL Module.

# Express JS 
##### Back End Web Application framework
## Apa Itu Express JS?
Express.js, atau hanya Express, adalah kerangka aplikasi web back end untuk Node.js, dirilis sebagai perangkat lunak sumber terbuka dan gratis di bawah Lisensi MIT. Ini dirancang untuk membangun aplikasi web dan API. Ini telah disebut sebagai kerangka kerja server standar de facto untuk Node.js.
## Apa itu Back End Web Application?
Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API. Kelebihan dari framework ini terletak pada fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.
## Apa Itu Rest API?
RESTful API / REST API merupakan penerapan dari API (Application Programming Interface). 

Sedangkan REST (Representional State Transfer) adalah sebuah arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi. Dengan tujuannya untuk menjadikan sistem memiliki performa yang baik, cepat dan mudah untuk di kembangkan (scale) terutama dalam pertukaran dan komunikasi data.

* RESTFUL API memiliki 4 komponen penting yaitu
- URL Design
- HTTP Verbs
- HTTP Response Code
- Format Response

## Basic Syntax ExpressJS
`
const express = require ('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
    res.send('Hello World!')
})

app.listen(port, () => {
    console.log('Example app listening at http://localhost:${port}`)
})`
Contoh diatas adalah basic syntax dari express JS. Kita akan menggunakan module express kemudian yang berisi routing dan listen

## Basic Routes
Routes adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan

### Routes
Kita bisa menjalankan aplikasi sederhana kita dengan cara menggunakan “node”. Dan aplikasi kita akan berjalan di alamat ‘http://localhost:3000’

Kemudian kita dapat mengaksesnya di website dan menambah route yang akan kita akses yaitu “/”
### method
Kita dapat menggunakan method yang dalam REST API seperti POST, PUT, PATCH dan DELETE
`
app.Post('/posting', (req, res) => {
    res.end("posting succes!!!")
})
`
`
app.Delete('/deleting', (req, res) => {
    res.end("deleting succes!!!")
})
`
### Response 
Di dalam route kita dapat mengirim response menggunakan parameter dari route express.js yaitu “res.Send()” untuk mengirim plain text ketika kita mengakses route tersebut. Terdapat banyak response yang bisa kita buat selain yang dicontohkan.
`
app.get('/hello', (req, res) => {
    res.json({
        name : "budi", 
        age : 23,
        greeting: "hallo salam kenal"
    })
})
`
Kita dapat mengirim response berupa output json yang biasa dipakai untuk back end application. Dengan menggunakan output json maka kita dapat mengirim data yang mudah diakses 

### Status Code
Dalam pengaplikasian back end application, kita sangat perlu memberikan status code sebagai informasi apakah route yang kita akses berjalan sebagaimana mestinya dan tidak terjadi error.

### Query
Query merupakan parameter yang digunakan untuk membantu menentukan tindakan yang lebih spesifik daripada hanya sekedar router biasa. Biasanya query ditaruh di akhir route dengan memberikan informasi diawali dengan “?” kemudian tedapat key dan data yang dapat ditindak lanjuti. Ex : “?q=hello&age=23” 
`
app.get('/hello', (req, res) => {
    let name = req.query.name
    let age = req.query.age

    res.status(200).json({
        name : name,
        age : age,
        greeting: "Hallo Salam Kenal"
    })
})
`
Di ExpressJS kita juga dapat membaca query menggunakan req.query, kemudian informasi tersebut dapat kita olah atau kita kembaliakan lagi seperti contoh

### Nested Route
Nested route digunakan ketika terdapat banyak route yang memiliki nama yang sama atau ingin membuat route yang lebih mendalam

## Express Middleware
### Apa itu middleware?
- Middleware function adalah sebuah fungsi yang memiliki akses ke object request (req), object response (res), dan sebuah fungsi next didalam request-response cycle.
- Fungsi next biasanya di berikan nama variable nex

### Bagaimana cara middleware bekerja?
- Untuk memahami cara kerja middleware, bayangkan Anda memiliki stan minuman lemon di mana pelanggan membawa lemon mereka sendiri dan Anda membuat minuman lemon dari buah yang di bawa langsung oleh pelanggan.
- Anda bertanggung jawab untuk mengevaluasi asal dan kesegaran buah lemon, membuang lemon di bawah standar, dan, akhirnya, membuat minuman lemonnya.
- Untuk mengurangi beban kerja Anda, Anda mempekerjakan seorang pekerja — kita akan memanggilnya Larry — yang bertugas untuk memastikan lemon ditanam secara organik dan tanpa bahan kimia berbahaya.
- Dalam analogi ini, Larry adalah middleware yang berfungsi antara Anda dan pelanggan Anda.
- Sekarang Anda mendapat untung, jadi Anda mempekerjakan dua karyawan lain, Curly dan Moe.
- Larry akan memeriksa asal buah lemon dan memberikan buah lemon yang ditanam secara organik kepada Curly.
- Kemudian, Curly yang membuang lemon busuk dan menyerahkan lemon yang bagus kepada Moe.
- Selanjutnya, Moe akan memverifikasi kesegaran buah lemon dan memberikan buah lemon segar kepada Anda.
- Sekarang Anda dapat fokus untuk membuat minuman lemon dan meningkatkan keuntungan Anda, tanpa perlu memikirkan pekerjaan filtering buah lemon.
- Dari ilustrasi diatas, kita bisa menganalogikan bahwa buah lemon yang di - bawa sendiri oleh pelanggan adalah sebuah HTTP request, dan stan minuman lemon adalah sebuah server.
- Anda akan memeriksa asal buah lemon yang di bawa langsung oleh pelanggan, sama seperti yang Anda lakukan dengan sebuah HTTP request, sebelum menerima atau menolak sebuah HTTP request.
- Tidak semua HTTP Request itu bagus dan benar, jadi server masih perlu melakukan filtering request.
- Karyawan Anda - Larry, Curly, dan Moe – bisa di ibaratkan seperti middleware function untuk stan  minuman lemon Anda.
- Jika pada tahap mana pun middleware function menentukan bahwa suatu HTTP Request adalah request yang buruk dan salah, maka middleware function memiliki kemampuan untuk menghentikan request-response cycle.
- Berlaku juga sebaliknya, jika middleware function menentukan suatu HTTP Request baik dan benar, maka middleware function memiliki kemampuan untuk melanjutkan request-response cycle ke proses selanjutnya.
- Setelah sebuah HTTP Request melewati semua middleware yang ada di aplikasi, HTTP Request tersebut akan mencapai handler function — yang, dalam kasus contoh ilustrasi ini, adalah Anda yang menjual minuman lemon (atau, lebih khusus lagi, proses membuat minuman lemon).
- Setelah sebuah HTTP Request melewati semua middleware yang ada di aplikasi Anda, HTTP Request tersebut akan mencapai handler function — yang, dalam kasus contoh ilustrasi ini, adalah Anda yang menjual minuman lemon (atau, lebih khusus lagi, proses membuat minuman lemon).
- Ini hanya contoh sederhana. Dalam skenario nyata, Kita mungkin perlu menggunakan beberapa middlewares untuk melakukan satu tugas, seperti melakukan pencatatan setiap HTTP Request ataupun melakukan validasi inputan user.

### Apa Saja Yang Bisa Dilakukan Oleh Function Middleware?
#### Menjalankan kode apapun
- Sebuah function middleware bisa digunakan untuk mengeksekusi kode apapun untuk suatu tujuan tertentu.
- Sebagai contoh, kita akan membuat sebuah middleware function yang akan mencetak tulisan “Halo Skilvul, request diterima!” Ketika sebuah HTTP Request masuk kedalam middleware function ini. 
- Middleware Function ini akan diberi nama dengan skilvulLogger.
` const skilvulLogger = function (req, res, next) {
    console.log('Halo Skilvul, request diterima!')
    next()
}`
#### Memodifikasi Object Request dan Object Response.
- Sebuah function middleware bisa digunakan untuk memodifikasi Object Request dan Object Response.
- Sebagai contoh, kita akan membuat sebuah middleware function yang akan menambahkan informasi request time pada object request.
- Middleware Function ini akan diberi nama dengan addRequestTime.
` const addRequestTime = function (req, res, next) {
    req.requestTime = Date.now()
    next()
}`
#### Menghentikan request-response cycle.
- Sebuah function middleware bisa digunakan untuk menghentikan request-response cycle.
- Sebagai contoh, kita akan membuat sebuah middleware function yang akan menghentikan request-response cycle.
- Middleware Function ini akan diberi nama dengan stopHere.
- Request tidak akan pernah sampai ke handler function, karena middleware telah menghentikan request-response cycle dengan res.send() dan tidak memanggil next()
`
const stopHere = function (req, res, next) {
    res.send('<p>request stop from middleware</p>')
}`
#### Melanjutkan ke middleware function selanjutnya atau ke handler function dalam suatu request response cycle.
- Sebuah function middleware bisa digunakan untuk melanjutkan ke middleware function selanjutnya / ke handler function.
- Sebenarnya kita sudah melakukannya pada contoh-contoh sebelumnya, yaitu dengan cara memanggil function next() pada sebuah middleware function.
- Jika sebuah middleware function tidak mengakhiri request-response cycle, maka middleware tersebut harus memanggil function next() untuk melanjutkan request ke middleware function selanjutnya / ke handler function.
- Apabila hal tersebut tidak dilakukan (memanggil function next()), maka request akan tetap dalam kondisi menggantung (tidak mengembalikan response) sampai terjadinya error timeout.

## Jenis Express Middleware Berdasarkan Cara Penggunaan
### Application Level Middleware
- Application Level Middleware adalah sebuh function middleware yang melekat ke instance object Application Express.
- Penggunaannya dengan cara memanggil method app.use().
- Application Level Middleware akan di jalankan setiap kali Express Application menerima sebuah HTTP Request.
`
const addRequestTime = function (req, res, next) {
    req.requestTime = Date.now()
    next()
}

app.user(addRequestTime)`

### Router Level Middleware
- Router Level Middleware adalah sebuh function middleware yang cara kerjanya sama persis dengan application level middleware, yang menjadikan perbedaan adalah middleware function ini melekat ke instance object Router Express.
- Penggunaannya dengan cara memanggil method express.Router().
- Router Level Middleware hanya akan di jalankan setiap kali sebuah Express Router yang menggunakan middleware ini menerima sebuah HTTP Request, sedangan pada Router yang lain tidak akan dijalankan.

### Error Handling Middleware
- Error Handling mengacu kepada bagaimana cara sebuah Express Application menangkap dan memproses error yang terjadi, baik itu berupa kesalahan yang synchronous maupun asynchronous.
- Express Application sudah menyediakan error handle function default, sehingga kita tidak perlu lagi membuat sendiri functionnya.
- Error handle function default milik Express Application hanyalah kerangka functionnya saja, kita tetap harus menuliskan di dalam function ini bagaimana sebuah error akan di handle.
- Error Handling Middleware digunakan pada Application Level Middleware
`
const express = require("express")
const app = express()

const errorHandling = function(err, req, res, next) {
    console.error(err.stack)
    res.status(500).send('Something broke!')
}

app.use(errorHandling)`
Sebuah error handling middleware function harus memberikan 4 (empat) buah argument (err, req, res, next) agar bisa di deteksi oleh Express Application sebagai error handling middleware, sekalipun kita tidak akan pernah menggunakan function next dalam error handling middleware ini.

Jika hal ini tidak dilakukan, maka Express Application tidak akan mengenali middleware function ini sebagai error handling middleware, dan akan memperlakukan middleware ini sebagai Application Level Middleware seperti biasa.

## Jenis Express Middleware Berdasarkan Source Middleware Function
### Express Build-in Middleware
#### express.static
- Adalah salah satu build-in middleware function yang disediakan oleh Express JS.
- Middleware function ini memungkinkan sebuah express application melayani asset statis berupa file, seperti file HTML, gambar, video, dokumen, dan sebagainya.
#### express.json()
- Adalah salah satu build-in middleware function yang disediakan oleh Express JS.
- Middleware function ini memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format JSON.
- Middleware function ini tersedia di Express JS versi 4.16.0+
` const express = require ("express")
const app = express()

app.use(express.json())
`
#### express.urlEncoded()
- salah satu build-in middleware function yang disediakan oleh Express JS.
- Middleware function ini memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format urlencoded.
- Middleware function ini tersedia di Express JS versi 4.16.0+
` const express = require ("express")
const app = express()

app.use(express.urlEncoded())
`
### Express Third Party (custom) Middleware
Membuat custom middleware function atau menggunakan third party middleware function dapat menambahkan fungsionalitas dari sebuah Express Application.
Contoh custom middleware seperti function skilvulLogger yang sudah kita buat sebelumnya.
Selain membuat sendiri middleware function custom, kita bisa juga menggunakan third party middleware (middleware function yang di buat oleh orang lain).
Ada beberapa Third Party middleware yang di Kelola oleh Express JS team, ada juga yang di Kelola secara community.


# Design Database With MySQL
## Apa itu Basis Data Relasional?
Menurut Oracle , database relasional adalah "sejenis database yang menyimpan dan menyediakan akses ke titik data yang terkait satu sama lain".
Kita dapat membuat, membaca, memperbarui, dan menghapus (fungsi dasar dari basis data apa pun) informasi dalam basis data relasional kami menggunakan Sistem Manajemen Basis Data Relasional ( RDBMS ). Contoh RDBMS termasuk Oracle , Microsoft SQL Server , MySQL , dan PostgreSQL , di antara banyak lainnya. Masing-masing memiliki pro dan kontra (dan seperti semua coding-berdekatan, hyper-partisan online mereka), dan SQL tidak diimplementasikan dengan cara yang persis sama di masing-masingnya. Konsepnya sama, tetapi sintaks dan kata kuncinyamungkin sedikit berbeda
Dalam database relasional, catatan disimpan dalam tabel (pikirkan spreadsheet Excel, jika itu sesuatu yang Anda kenal) di mana setiap kolom adalah atribut (misalnya nama produk, biaya pembelian, harga eceran) dan setiap baris mewakili catatan (nama produk tertentu , biaya pembelian, harga eceran). item atau instance yang memiliki atribut tersebut).

## Primary Key
Setiap record di setiap tabel di database Anda harus memiliki atribut (atau kombinasi atribut) yang mengidentifikasinya secara unik — ini dikenal sebagai Primary Key.
dimungkinkan untuk menggunakan ' Composite key ' yang terdiri dari, misalnya, atribut 'nama_produk' dan 'jenis_produk' bersama-sama, dengan anggapan bahwa ini mengidentifikasi produk secara unik (yaitu bahwa Merek Keren ™ dll tidak pernah merilis produk lain dengan nama yang sama). Yang digunakan tergantung pada sifat data Anda — yang penting adalah bahwa setiap tabel memiliki Primary key, harus unik dan tidak boleh NULL .

## Foreign Key
Kita dapat mengungkapkan hubungan antara entitas ini (dalam hal ini, bahwa merek adalah produsen produk) dengan memasukkan kunci utama dari database merek sebagai 'Foreign Key' dalam database produk. Ini berarti bahwa setiap produk dapat dikaitkan dengan merek yang sesuai di database kita.

Ini sangat berguna karena ini berarti tabel-tabel ini terhubung dengan cara yang berarti dan kita dapat dengan mudah menemukan nama penghubung yang bertanggung jawab untuk 'Luft Extreme Sneakers', misalnya.
Atribut relasi ini, berapa banyak entitas lain yang dapat memiliki relasi dengan entitas, dikenal sebagai kardinalitas relasi. Hubungan lainnya termasuk 1-ke-1 dan N-to-M (banyak ke banyak). Kami akan membahas ini nanti.

Basis data kami dapat menjadi sangat kompleks karena kami mulai memiliki beberapa tabel dengan hubungan yang berbeda satu sama lain, tetapi dasar-dasar yang harus difokuskan di sini adalah:
- Setiap tabel memiliki kunci utama yang secara unik mengidentifikasi setiap record dalam tabel, dan yang tidak boleh nol.
- Untuk setiap hubungan tabel A ke tabel lain, diperlukan kunci asing sebagai atribut dalam tabel A untuk mendefinisikan hubungan itu.
Ini adalah bagaimana kita mendefinisikan hubungan antara data dalam hubungan 1-ke-N dalam database relasional.

## Merancang database
### 1. Mendefinisikan persyaratan
Hal pertama yang harus dipikirkan saat membuat database adalah untuk apa kita menginginkannya. Ini mungkin tampak jelas, tetapi layak untuk dinyatakan secara eksplisit. Persyaratan yang berbeda akan menghasilkan struktur informasi, hubungan, desain, dan implementasi yang berbeda

### 2. Membuat Rencana berdasarkana kebutuhan
Hal pertama yang harus dilakukan adalah membaca dokumen persyaratan dengan cermat, mencatat hal-hal yang mungkin menjadi entitas dalam database kita, dan kemungkinan hubungan di antara mereka.

Penting pada tahap ini untuk mengajukan pertanyaan untuk memperjelas persyaratan. Itu wajar bagi orang yang bekerja dengan sesuatu setiap hari untuk memikirkan beberapa hal sebagai 'akal sehat' atau jelas, ketika mereka mungkin tidak jelas bagi seseorang yang datang dari luar area kerja itu. Juga, orang terkadang tidak terbiasa memikirkan aspek-aspek pekerjaan mereka dengan ketelitian yang diperlukan untuk membuat database.
Langkah perantara yang sangat berguna antara mendapatkan persyaratan dan mengimplementasikan database kami di SQL adalah membuat Entity Relationship Diagram (ERD). Ini adalah, seperti yang mungkin Anda antisipasi, diagram yang memetakan hubungan antara entitas yang akan kita bangun ke dalam database kita. Proses menyusun diagram ini dapat membantu kita meluruskan hubungan dan mengidentifikasi wawasan penting atau atribut yang berlebihan seiring berjalannya waktu.

### 3. Mengidentifikasi entitas
apa saja identitasnya

### 4. Atribut mana yang ingin kita simpan?
Langkah selanjutnya adalah memikirkan atribut mana yang ingin kita simpan untuk setiap entitas kita. Ini mungkin dijabarkan secara rinci dalam dokumen persyaratan kami, atau mungkin memerlukan lebih banyak kebijaksanaan dari pihak pengembang basis data.

### 5. Memetakan hubungan
menentukan hubungan antara satu entitas ke entitas lain, misal one to one, one to many, many to many dll











