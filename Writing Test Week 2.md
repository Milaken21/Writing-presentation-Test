Week 2 Day 6
# JAVASCRIPT - SCOPE
* Scope adalah konsep dalam flow data variabel. 
* Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak.
* Blocks adalah code yang berada didalam curly braces {}.
* Conditional, function, dan  looping menggunakan blocks.
* Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file.
```
let myName = 'Raisha';
function greeting() {
    return myName; //Raisha
}
console.log (myName); //Raisha
```
* Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.
* Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping
```
function greeting() {
    let myName = 'Raisha';
    return myName; //Raisha
}
console.log(greeting()) //Raisha
console.log(myName); //uncaught ReferenceError: myName is not Defined because local scope
```
* Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.

# FUNCTION
* Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur.
* Dengan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk melakukan task/tugas.
* Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.

* Parameter Function
Dengan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk melakukan task/tugas.
Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.
```
funtion penambahan (a, b) {
return a + b;
		}
```
* Tidak mungkin membuat code yang sebenernya sama tapi dengan jumlah yang banyak berulang kali.
* Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menggunakannya

* Memanggil Function
```
greeting() //call the function name
console.log(greeting()); //output 'hello world'
```

# Argumen Function
* Argumen adalah nilai yang digunakan saat memanggil function.
* Jumlah argumen harus sama dengan jumlah parameternya
* Jadi jika di function penambahan ada 2 parameter nilai saat membuat function. Saat memanggil function kita gunakan 2 buah nilai argumen.
```
funtion penambahan (a, b) {
return a + b;
}
    console.log(penambahan(5,5)) //output: 10
```
# Default Parameter
* Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function.
* Default parameters bisa digunakan jika kita ingin menjaga function agar tidak error saat dipanggil tanpa argumen
```
functtion greetOnWebsite(name = 'stranger'){
    return 'hello' + name;
}
console.log(greetOnWebsite('David')); //output 'hello david'
console.log(greetOnWebsite()); //output 'hello stranger'
```

# Function Helper
* Kita bisa menggunakan function yang sudah dibuat pada function lain.
```
function multiplyByNineFifths(number) {
    return number*(9/5):
};
function getFahrenheit(celcius) {
    return multiplyByNineFifths(celcius) + 32;
}
getFahrenheit(15); //returns 59
```
# Arrow Function
* arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)
```
const greeting = () => {
    return 'hello world';
};
const penambahan = (a, b) => {
    return a + b;
};
```

# Short Syntax Function
* Zero parameter
``` 
const functionName = () => {}; 
```
* One Parameter
``` 
const functionName = paramOne => {};
```
* Two or more parameter
```
const functionName = (paramOne, paramTwo) => {};
```
* Single-line block
```
const sumNumbers = number => number + number;
```
* multi line block
```
const sumNumbers = number => {
    const sum = number + number;
    return sum;
}
```






Week 2 Day 7
# Tipe data primitive dan non primitive
tipe data primitive boolean, Null, number, undefined, dan numerik sedangkan non primitif terdapat array, object, dan function
# Nilai Primitif
Semua jenis kecuali objek mendefinisikan nilai yang tidak dapat diubah (yaitu, nilai yang tidak dapat diubah). Misalnya, String tidak dapat diubah. Kami menyebut nilai jenis ini sebagai " nilai primitif ".
# Tipe Boolean
Boolean mewakili entitas logis dan dapat memiliki dua nilai: truedan false. Lihat Boolean dan Booleanuntuk lebih jelasnya.
# Tipe Null
Jenis Null memiliki tepat satu nilai: null. Lihat nulldan Null untuk lebih jelasnya.
# undifined
Sebuah variabel yang belum diberi nilai memiliki nilai undefined. Lihat undefineddan Tidak ditentukan untuk detail lebih lanjut.
# Tipe Numerik
ECMAScript memiliki dua tipe numerik bawaan: Number dan BigInt — bersama dengan nilai terkait NaN .
# Tipe Number
Jenis Angka adalah nilai IEEE 754 format biner 64-bit presisi ganda . Ia mampu menyimpan angka floating-point positif antara 2^-1074 ( Number.MIN_VALUE) dan 2^1024 ( Number.MAX_VALUE) serta angka floating-point negatif antara -(2^-1074) dan -(2^1024), tetapi bisa hanya menyimpan bilangan bulat dengan aman dalam kisaran -(2^53 1) ( Number.MIN_SAFE_INTEGER) hingga 2^53 1 ( Number.MAX_SAFE_INTEGER).
* Nilai di luar rentang ±(2^-1074 hingga 2^1024) secara otomatis dikonversi:
* Nilai positif lebih besar dari Number.MAX_VALUEdikonversi ke +Infinity.
* Nilai positif yang lebih kecil dari Number.MIN_VALUEdikonversi ke +0.
* Nilai negatif yang lebih kecil dari - Number.MAX_VALUEdikonversi menjadi -Infinity.
* Nilai negatif lebih besar dari - Number.MIN_VALUEdikonversi ke -0.
# Big Init
Tipe BigInt adalah primitif numerik dalam JavaScript yang dapat mewakili bilangan bulat dengan presisi arbitrer. Dengan BigInts, Anda dapat dengan aman menyimpan dan mengoperasikan bilangan bulat besar bahkan di luar batas bilangan bulat aman untuk Numbers.

BigInt dibuat dengan menambahkan nke akhir bilangan bulat atau dengan memanggil konstruktor.

Anda dapat memperoleh nilai aman terbesar yang dapat ditambahkan dengan Numbers dengan menggunakan konstanta Number.MAX_SAFE_INTEGER. Dengan diperkenalkannya BigInts, Anda dapat beroperasi dengan angka di luar Number.MAX_SAFE_INTEGER.

Contoh ini menunjukkan, di mana peningkatan Number.MAX_SAFE_INTEGERpengembalian mengembalikan hasil yang diharapkan:
```
    // BigInt
    const x = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
    x + 1n === x + 2n; // false because 9007199254740992n and 9007199254740993n are unequal

    // Number
    Number.MAX_SAFE_INTEGER + 1 === Number.MAX_SAFE_INTEGER + 2; // true because both are 9007199254740992
```
Menyalin ke clipboard
dapat menggunakan operator +, *, -, **, dan %dengan BigInts—seperti halnya dengan Numbers. BigInt tidak sepenuhnya sama dengan Angka, tetapi secara longgar begitu.
BigInt berperilaku seperti Angka jika diubah menjadi boolean: if, ||, &&, Boolean, !. BigInts tidak dapat dioperasikan secara bergantian dengan Numbers. Sebaliknya a TypeErrorakan dilempar.

# Tipe NaN
NaN(" N ot a N umber") biasanya ditemui ketika hasil operasi aritmatika tidak dapat dinyatakan sebagai angka. Ini juga satu-satunya nilai dalam JavaScript yang tidak sama dengan dirinya sendiri.

# Tipe String
Jenis String JavaScript digunakan untuk mewakili data tekstual. Ini adalah satu set "elemen" dari nilai integer 16-bit unsigned. Setiap elemen dalam String menempati posisi dalam String. Elemen pertama ada di index 0, yang berikutnya di index 1, dan seterusnya. Panjang dari sebuah String adalah jumlah elemen di dalamnya.

String JavaScript tidak dapat diubah. Ini berarti bahwa setelah string dibuat, tidak mungkin untuk mengubahnya. Namun, masih dimungkinkan untuk membuat string lain berdasarkan operasi pada string asli. Sebagai contoh:

Sebuah substring dari aslinya dengan memilih huruf individu atau menggunakan substring().
Penggabungan dua string menggunakan operator penggabungan ( +) atau concat(). Gunakan string untuk data tekstual. Saat mewakili data kompleks, parsing string, dan gunakan abstraksi yang sesuai.

* Cara membuat string
const string1 = "A string primitive";
const string2 = 'Also a string primitive';
const string3 = `Yet another string primitive`;

# Akses Karater
Ada dua cara untuk mengakses karakter individu dalam sebuah string. Yang pertama adalah charAt()
```
'cat'.charAt(1) // gives value "a"
```
Cara lain adalah dengan memperlakukan string sebagai objek seperti array, di mana karakter individu sesuai dengan indeks numerik:
```
'cat'[1] // gives value "a"
```
* Membandingkan string
Dalam C, strcmp()fungsi ini digunakan untuk membandingkan string. Dalam JavaScript, Anda cukup menggunakan operator less-than dan more-than :
```
const a = 'a';
const b = 'b';
if (a < b) { // true
  console.log(`${a} is less than ${b}`)
} else if (a > b) {
  console.log(`${a} is greater than ${b}`)
} else {
  console.log(`${a} and ${b} are equal.`)
}
```
Perhatikan bahwa semua operator perbandingan, termasuk ===dan ==, membandingkan string dengan peka huruf besar/kecil. Cara umum untuk membandingkan string dengan tidak peka huruf besar-kecil adalah dengan mengonversi keduanya menjadi huruf besar yang sama (atas atau bawah) sebelum membandingkannya.
```
function areEqualCaseInsensitive(str1, str2) {
  return str1.toUpperCase() === str2.toUpperCase();
}
```
Pilihan apakah akan mengubah dengan toUpperCase()atau toLowerCase()sebagian besar arbitrer, dan tidak ada yang sepenuhnya kuat ketika melampaui abjad Latin. Misalnya, huruf kecil Jerman ßdan sskeduanya diubah menjadi SSoleh toUpperCase(), sedangkan huruf Turki ıakan salah dilaporkan sebagai tidak sama Idengan toLowerCase()kecuali jika secara khusus menggunakan toLocaleLowerCase("tr").
```
const areEqualInUpperCase = (str1, str2) =>
  str1.toUpperCase() === str2.toUpperCase();
const areEqualInLowerCase = (str1, str2) =>
  str1.toLowerCase() === str2.toLowerCase();

areEqualInUpperCase("ß", "ss"); // true; should be false
areEqualInLowerCase("ı", "I"); // false; should be true
```
Menyalin ke clipboard
Solusi yang peka terhadap lokal dan kuat untuk menguji kesetaraan peka huruf besar-kecil adalah dengan menggunakan Intl.CollatorAPI atau metode string localeCompare()— keduanya berbagi antarmuka yang sama — dengan sensitivityopsi yang disetel ke "accent"atau "base".
```
const areEqual = (str1, str2, locale = "en-US") =>
  str1.localeCompare(str2, locale, { sensitivity: "accent" }) === 0;

areEqual("ß", "ss", "de"); // false
areEqual("ı", "I", "tr"); // true
```
Metode localeCompare()ini memungkinkan perbandingan string dengan cara yang sama seperti strcmp()— metode ini memungkinkan pengurutan string dengan cara yang sadar-lokal.

# String primitif dan objek String
Perhatikan bahwa JavaScript membedakan antara Stringobjek dan nilai string primitif . (Hal yang sama berlaku untuk Booleandan Numbers.)

String literal (dilambangkan dengan tanda kutip ganda atau tunggal) dan string yang dikembalikan dari Stringpanggilan dalam konteks non-konstruktor (yaitu, dipanggil tanpa menggunakan newkata kunci) adalah string primitif. Dalam konteks di mana metode akan dipanggil pada string primitif atau pencarian properti terjadi, JavaScript akan secara otomatis membungkus string primitif dan memanggil metode atau melakukan pencarian properti pada objek pembungkus sebagai gantinya.
```
const strPrim = "foo"; // A literal is a string primitive
const strPrim2 = String(1); // Coerced into the string primitive "1"
const strPrim3 = String(true); // Coerced into the string primitive "true"
const strObj = new String(strPrim); // String with new returns a string wrapper object.

console.log(typeof strPrim); // Logs "string"
console.log(typeof strPrim2); // Logs "string"
console.log(typeof strPrim3); // Logs "string"
console.log(typeof strObj);  // Logs "object"
```
String primitif dan Stringobjek juga memberikan hasil yang berbeda saat menggunakan eval(). Primitif yang diteruskan ke evaldiperlakukan sebagai kode sumber; Stringobjek diperlakukan seperti semua objek lainnya, dengan mengembalikan objek. 

# 
Banyak operasi bawaan yang mengharapkan string terlebih dahulu memaksa argumen mereka ke string (yang sebagian besar mengapa Stringobjek berperilaku mirip dengan string primitif). Operasi tersebut dapat diringkas sebagai berikut:

String dikembalikan apa adanya.
* undefinedberubah menjadi "undefined".
* null berubah menjadi "null".
* true berubah menjadi "true"; falseberubah menjadi "false".
* Angka dikonversi dengan algoritma yang sama seperti toString(10).
* BigInts dikonversi dengan algoritma yang sama seperti toString(10).
* Simbol melempar a TypeError.
* Objek pertama dikonversi ke primitif dengan memanggil [@@toPrimitive]()(dengan "string"sebagai petunjuk), toString(), dan valueOf()metode, dalam urutan itu. Primitif yang dihasilkan kemudian diubah menjadi string.

# Konstruktor
* String()
Membuat Stringobjek baru. Ia melakukan konversi tipe ketika dipanggil sebagai fungsi, bukan sebagai konstruktor, yang biasanya lebih berguna.

# Metode statis
* String.fromCharCode()
Mengembalikan string yang dibuat dengan menggunakan urutan nilai Unicode yang ditentukan.
* String.fromCodePoint()
Mengembalikan string yang dibuat dengan menggunakan urutan titik kode yang ditentukan.
* String.raw()
Mengembalikan string yang dibuat dari string template mentah.
* Properti instan
String.prototype.length
Mencerminkan lengthstring. Hanya baca.

# Metode instan
* String.prototype.at()
Mengembalikan karakter (tepatnya satu unit kode UTF-16) pada index. Menerima bilangan bulat negatif, yang menghitung mundur dari karakter string terakhir.
* String.prototype.charAt()
Mengembalikan karakter (tepatnya satu unit kode UTF-16) pada index.
* String.prototype.charCodeAt()
Mengembalikan angka yang merupakan nilai unit kode UTF-16 pada nilai index.
* String.prototype.codePointAt()
Mengembalikan bilangan bulat non-negatif yang merupakan nilai titik kode dari titik kode yang disandikan UTF-16 mulai dari yang ditentukan pos.
* String.prototype.concat()
Menggabungkan teks dari dua (atau lebih) string dan mengembalikan string baru.
* String.prototype.includes()
Menentukan apakah string panggilan berisi searchString.
* String.prototype.endsWith()
Menentukan apakah string diakhiri dengan karakter string searchString.
* String.prototype.indexOf()
Mengembalikan indeks dalam Stringobjek panggilan dari kemunculan pertama searchValue, atau -1jika tidak ditemukan.
* String.prototype.lastIndexOf()
Mengembalikan indeks dalam Stringobjek panggilan dari kemunculan terakhir searchValue, atau -1jika tidak ditemukan.
* String.prototype.localeCompare()
Mengembalikan angka yang menunjukkan apakah string referensi compareStringmuncul sebelum, sesudah, atau setara dengan string yang diberikan dalam urutan pengurutan.
* String.prototype.match()
Digunakan untuk mencocokkan ekspresi reguler regexpdengan string.
* String.prototype.matchAll()
Mengembalikan iterator dari semua regexpkecocokan.
* String.prototype.normalize()
Mengembalikan Bentuk Normalisasi Unicode dari nilai string panggilan.
* String.prototype.padEnd()
Pads string saat ini dari akhir dengan string yang diberikan dan mengembalikan string baru dengan panjang targetLength.
* String.prototype.padStart()
Pads string saat ini dari awal dengan string yang diberikan dan mengembalikan string baru dengan panjang targetLength.
* String.prototype.repeat()
Mengembalikan string yang terdiri dari elemen objek berulang countkali.
* String.prototype.replace()
Digunakan untuk menggantikan kemunculan searchForpenggunaan replaceWith. searchFordapat berupa string atau Ekspresi Reguler, dan replaceWithdapat berupa string atau fungsi.
* String.prototype.replaceAll()
Digunakan untuk mengganti semua kemunculan searchForpenggunaan replaceWith. searchFordapat berupa string atau Ekspresi Reguler, dan replaceWithdapat berupa string atau fungsi.
* String.prototype.search()
Cari kecocokan antara ekspresi reguler regexpdan string panggilan.
* String.prototype.slice()
Mengekstrak bagian string dan mengembalikan string baru.
* String.prototype.split()
Mengembalikan array string yang diisi dengan memisahkan string panggilan pada kemunculan substring sep.
* String.prototype.startsWith()
Menentukan apakah string pemanggilan dimulai dengan karakter string searchString.
* String.prototype.substring()
Mengembalikan string baru yang berisi karakter string panggilan dari (atau di antara) indeks (atau indeks) yang ditentukan.
* String.prototype.toLocaleLowerCase()
Karakter dalam string diubah menjadi huruf kecil dengan tetap menghormati lokal saat ini.

Untuk sebagian besar bahasa, ini akan mengembalikan sama seperti toLowerCase().
* String.prototype.toLocaleUpperCase( [locale, ...locales])
Karakter dalam string diubah menjadi huruf besar dengan tetap menghormati lokal saat ini.

Untuk sebagian besar bahasa, ini akan mengembalikan sama seperti toUpperCase().
* String.prototype.toLowerCase()
Mengembalikan nilai string panggilan yang dikonversi menjadi huruf kecil.
* String.prototype.toString()
Mengembalikan string yang mewakili objek yang ditentukan. Mengganti Object.prototype.toString()metode.
* String.prototype.toUpperCase()
Mengembalikan nilai string panggilan yang dikonversi menjadi huruf besar.
* String.prototype.trim()
Memangkas spasi putih dari awal dan akhir string.
* String.prototype.trimStart()
Memangkas spasi putih dari awal string.
* String.prototype.trimEnd()
Memotong spasi putih dari akhir string.
* String.prototype.valueOf()
Mengembalikan nilai primitif dari objek yang ditentukan. Mengganti Object.prototype.valueOf()metode.
* String.prototype[@@iterator]()
Mengembalikan objek iterator baru yang berulang pada titik kode dari nilai String, mengembalikan setiap titik kode sebagai nilai String.

# Ada beberapa cara untuk mencapai efek yang hampir sama dalam JavaScript.
* Template literal : `${x}`melakukan persis langkah-langkah pemaksaan string yang dijelaskan di atas untuk ekspresi yang disematkan.
* Fungsi String(): String(x)menggunakan algoritma yang sama untuk mengonversi x, kecuali bahwa Simbol tidak melempar TypeError, tetapi mengembalikan "Symbol(description)", di mana descriptionadalah deskripsi Simbol.
* Menggunakan +operator : "" + xmemaksa operandnya ke primitif alih-alih string , dan, untuk beberapa objek, memiliki perilaku yang sama sekali berbeda dari paksaan string normal. Lihat halaman referensinya untuk lebih jelasnya.
* Bergantung pada kasus penggunaan Anda, Anda mungkin ingin menggunakan `${x}`(untuk meniru perilaku bawaan) atau String(x)(untuk menangani nilai simbol tanpa menimbulkan kesalahan), tetapi Anda tidak boleh menggunakan "" + x.
# Tipe Simbol
Simbol adalah nilai primitif yang unik dan tidak dapat diubah dan dapat digunakan sebagai kunci dari properti Objek (lihat di bawah). Dalam beberapa bahasa pemrograman, Simbol disebut "atom".

# Object
Dalam ilmu komputer, objek adalah nilai dalam memori yang mungkin dirujuk oleh pengidentifikasi .

# Properti
Dalam JavaScript, objek dapat dilihat sebagai kumpulan properti. Dengan sintaks literal objek , sekumpulan properti terbatas diinisialisasi; maka properti dapat ditambahkan dan dihapus. Nilai properti dapat berupa nilai jenis apa pun, termasuk objek lain, yang memungkinkan membangun struktur data yang kompleks. Properti diidentifikasi menggunakan nilai kunci . Nilai kunci adalah nilai String atau nilai Simbol .

Ada dua jenis properti objek: properti data dan properti pengakses . Setiap properti memiliki atribut yang sesuai . Setiap atribut diakses secara internal oleh mesin JavaScript, tetapi Anda dapat mengaturnya melalui Object.defineProperty(), atau membacanya melalui Object.getOwnPropertyDescriptor(). Anda dapat membaca lebih lanjut tentang berbagai nuansa di Object.defineProperty()halaman.

# properti data
Properti data mengaitkan kunci dengan nilai. Hal ini dapat dijelaskan dengan atribut berikut:
* Value
Nilai yang diambil oleh akses get properti. Dapat berupa nilai JavaScript apa pun.
* Writable
Nilai boolean yang menunjukkan apakah properti dapat diubah dengan penugasan.
* enumerable
Nilai boolean yang menunjukkan jika properti dapat dihitung dengan for...inloop. Lihat juga Enumerabilitas dan kepemilikan properti untuk mengetahui bagaimana enumerabilitas berinteraksi dengan fungsi dan sintaks lainnya.
* Configurable
Nilai boolean yang menunjukkan apakah properti dapat dihapus, dapat diubah menjadi properti pengakses, dan dapat mengubah atributnya.

# Properti pengakses
Mengaitkan kunci dengan salah satu dari dua fungsi pengakses ( getdan set) untuk mengambil atau menyimpan nilai.

Catatan: Penting untuk mengenali properti pengaksesnya — bukan metode pengakses . Kita dapat memberikan pengakses seperti kelas objek JavaScript dengan menggunakan fungsi sebagai nilai — tetapi itu tidak membuat objek menjadi kelas.
* get
Fungsi yang dipanggil dengan daftar argumen kosong untuk mengambil nilai properti setiap kali akses get ke nilai dilakukan. 
* Set
Fungsi yang dipanggil dengan argumen yang berisi nilai yang ditetapkan. Dieksekusi setiap kali properti tertentu dicoba untuk diubah.
* enumerable
Nilai boolean yang menunjukkan jika properti dapat dihitung dengan for...inloop.
* Configurable
Nilai boolean yang menunjukkan apakah properti dapat dihapus, dapat diubah menjadi properti data, dan dapat mengubah atributnya.

# Objek "Normal", dan Fungsinya
Objek JavaScript adalah pemetaan antara kunci dan nilai . Kunci adalah string (atau Simbol), dan nilai dapat berupa apa saja.

Fungsi adalah objek biasa dengan kemampuan tambahan yang dapat dipanggil .

# Tanggal
Saat mewakili tanggal, pilihan terbaik adalah menggunakan Dateutilitas bawaan dalam JavaScript.

# Koleksi yang diindeks: Array dan Array yang diketik
Array adalah objek reguler yang memiliki hubungan tertentu antara properti berkunci integer dan lengthproperti.

Selain itu, array mewarisi dari Array.prototype, yang menyediakan beberapa metode praktis untuk memanipulasi array. Misalnya, indexOf()(mencari nilai dalam array) atau push()(menambahkan elemen ke array), dan seterusnya. Ini membuat Array kandidat yang sempurna untuk mewakili daftar atau set.

Typed Arrays menyajikan tampilan seperti array dari buffer data biner yang mendasarinya, dan menawarkan banyak metode yang memiliki semantik serupa dengan rekan array. "Array yang diketik" adalah istilah umum untuk berbagai struktur data, termasuk Int8Array, Float32Array, dll.

# Koleksi kunci: Peta, Set, WeakMaps, WeakSets
Struktur data ini mengambil referensi objek sebagai kunci. Setdan WeakSetmewakili satu set objek, sementara Mapdan WeakMapmengasosiasikan nilai ke objek.

Perbedaan antara Maps dan WeakMaps adalah bahwa pada yang pertama, kunci objek dapat dicacahkan. Ini memungkinkan pengoptimalan pengumpulan sampah dalam kasus terakhir.

Anda bisa mengimplementasikan Maps dan Sets sendiri. Namun, karena objek tidak dapat dibandingkan (dalam arti <"kurang dari", misalnya), mesin juga tidak mengekspos fungsi hashnya untuk objek, kinerja pencarian tentu akan linier. Implementasi asli dari mereka (termasuk WeakMaps) dapat memiliki kinerja pencarian yang kira-kira logaritmik ke waktu konstan.

Biasanya, untuk mengikat data ke simpul DOM, seseorang dapat mengatur properti secara langsung pada objek, atau menggunakan data-*atribut. Ini memiliki kelemahan bahwa data tersedia untuk skrip apa pun yang berjalan dalam konteks yang sama. Maps dan WeakMaps memudahkan untuk mengikat data secara pribadi ke suatu objek.

# Data Struktur : JSON
JSON ( Java S cript O bject N otation ) adalah format pertukaran data yang ringan, berasal dari JavaScript, tetapi digunakan oleh banyak bahasa pemrograman. JSON membangun struktur data universal.

# Menentukan tipe menggunakan type of operator
Operator typeofdapat membantu Anda menemukan tipe variabel.

# Math 
Mathadalah objek bawaan yang memiliki properti dan metode untuk konstanta dan fungsi matematika. Ini bukan objek fungsi.

Mathbekerja dengan Numbertipe Ini tidak bekerja dengan BigInt.

tidak seperti banyak objek global lainnya, Mathbukan konstruktor. Semua properti dan metode Mathstatis. Anda merujuk ke pi konstan sebagai Math.PIdan Anda memanggil fungsi sinus sebagai Math.sin(x), di mana xadalah argumen metode. Konstanta didefinisikan dengan presisi penuh bilangan real dalam JavaScript.
* Math.E
Euler's constant and the base of natural logarithms; approximately 2.718.
* Math.LN2
Natural logarithm of 2; approximately 0.693.
* Math.LN10
Natural logarithm of 10; approximately 2.303.
* Math.LOG2E
Base-2 logarithm of E; approximately 1.443.
* Math.LOG10E
Base-10 logarithm of E; approximately 0.434.
* Math.PI
Ratio of a circle's circumference to its diameter; approximately 3.14159.
* Math.SQRT1_2
Square root of ½; approximately 0.707.
* Math.SQRT2
Square root of 2; approximately 1.414.

# Static methods
* Math.abs()
Returns the absolute value of x.
* Math.acos()
Returns the arccosine of x.
* Math.acosh()
Returns the hyperbolic arccosine of x.
* Math.asin()
Returns the arcsine of x.
* Math.asinh()
Returns the hyperbolic arcsine of a number.
* Math.atan()
Returns the arctangent of x.
* Math.atanh()
Returns the hyperbolic arctangent of x.
* Math.atan2()
Returns the arctangent of the quotient of its arguments.
* Math.cbrt()
Returns the cube root of x.
* Math.ceil()
Returns the smallest integer greater than or equal to x.
* Math.clz32()
Returns the number of leading zero bits of the 32-bit integer x.
* Math.cos()
Returns the cosine of x.
* Math.cosh()
Returns the hyperbolic cosine of x.
* Math.exp()
Returns ex, where x is the argument, and e is Euler's constant (2.718…, the base of the natural logarithm).
* Math.expm1()
Returns subtracting 1 from exp(x).
* Math.floor()
Returns the largest integer less than or equal to x.
* Math.fround()
Returns the nearest single precision float representation of x.
* Math.hypot()
Returns the square root of the sum of squares of its arguments.
* Math.imul()
Returns the result of the 32-bit integer multiplication of x and y.
* Math.log()
Returns the natural logarithm (㏒e; also, ㏑) of x.
* Math.log1p()
Returns the natural logarithm (㏒e; also ㏑) of 1 + x for the number x.
* Math.log10()
Returns the base-10 logarithm of x.
* Math.log2()
Returns the base-2 logarithm of x.
* Math.max()
Returns the largest of zero or more numbers.
* Math.min()
Returns the smallest of zero or more numbers.
* Math.pow()
Returns base x to the exponent power y (that is, xy).
* Math.random()
Returns a pseudo-random number between 0 and 1.
* Math.round()
Returns the value of the number x rounded to the nearest integer.
* Math.sign()
Returns the sign of the x, indicating whether x is positive, negative, or zero.
* Math.sin()
Returns the sine of x.
* Math.sinh()
Returns the hyperbolic sine of x.
* Math.sqrt()
Returns the positive square root of x.
* Math.tan()
Returns the tangent of x.
* Math.tanh()
Returns the hyperbolic tangent of x.
* Math.trunc()
Returns the integer portion of x, removing any fractional digits.



Week 2 Day 8, 9, 10
JAVASCRIPT dan HTML DOM
# Proses Randering dibalik layar
* html -> parsing -> tokens -> DOM
* CSS -> parsing -> tokens -> CSSOM
* DOM + CSSOM = Render tree
* Layouting

# isu terkait proses randering
* Jika saat proses parsing HTML, ditemukan tag <script>, secara default proses parsing akan dihentikan sampai script tersebut selesai diunduh dan dijalankan
* Jika script yang diunduh itu besar, ada jeda yang cukup lama antara halaman mulai dimuat sampai keluar tampilan

# Solusi isu terkait proses randering
* Taruh tag <script> eksternal sebelum tag penutup </body> - ini solusi paling umum agar dia mulai diproses setelah parsing HTML selesai.
* Taruh tag <script> sedini mungkin dan gunakan atribut async - atribut async akan membuat script tersebut diunduh tanpa menghentikan proses parsing dan dieksekusi seselesainya ia diunduh.
* Untuk script yang bergantung pada DOM, taruh tag <script> sedini mungkin, dan gunakan atribut defer - atribut defer akan membuat script tersebut diunduh tanpa menghentikan proses parsing dan dieksekusi seselesainya proses parsing selesai.

# Memanipulasi element HTML
# Mencari element HTML
getElementsByClassName akan ngereturn bentuk array; walaupun cuma ada 1 element dengan class itu Kalau bisa diulangin lagi penggunaan id dan class (id cuma boleh 1 element per page, class bisa beberapa sekaligus dan per element bisa beberapa class)
# Mengubah Konten Element
* Element.textContent
Element.textContent dapat kita gunakan untuk mengubah teks di dalam sebuah element
* Element.innerHTML
Element.innerHTML dapat kita gunakan untuk mengubah konten HTML di dalam sebuah element.
# Membuat Element HTML
.createElement() -> .textContext() untuk mengubah kontennya -> .appenChild() untuk menambahkan ke DOM
# Interaksi user (Event)
User experience itu bersifat dua arah:  selain menampilkan element HTML, halaman web juga harus bisa menangkap interaksi user
# HTML DOM Event
Focus, change, hover, click, blur, submit, scroll

# Menangkap Interaksi User
* Element.addEventListener("event")
* element.oneevent

# EventListener
Dengan cara Element.addEventListener(“event”)
* bisa dihilangkan
* bisa ada beberapa event listener yang sama untuk 1 element
* memiliki argumen tambahan (option)

# EventListener - Click 
* Misalkan kita mempunyai element <input id=”user-input” />  dan <button id=”alert-button”>show</button>. 
Kita ingin menampilkan pop up box yang berisi teks di dalam input tadi.
* // cari dulu kedua element tersebut berdasarkan id-nya
```
const input = document.getElementById(“user-input”)
const button = document.getElementById(“alert-button”)
// baru tambahkan event listener
button.addEventListener(“click”, function() {
	alert(input.value)
})

// atau
button.onclick = function() { alert(input.value) }
```
# EventListener - Blur
* “Blur”, lawan dari “focus”, adalah event di mana sebuah element kehilangan fokus dari user (misal user klk mouse di luar element tersebut atau user klik tab untuk berpindah element)

Misalkan kita ingin memvalidasi isi dari <input id=”username” /> agar panjangnya minimal 6 karakter..
```
// cari dulu element tersebut berdasarkan id-nya

const input = document.getElementById(“username”)

// tambahkan event listener
input.addEventListener(“blur”, () => {
	if(input.value.length < 6) alert(“Panjang username minimal 6”)
})
```

# EventListener - Form Submission
* Misalkan kita mempunyai element beberapa input dalam sebuah form <input name=”email /> dan <input type=”password” name=”password” />. Bagaimana caranya  kita mendapatkan isi dari kedua input tersebut saat submit form?
* Ada 2 cara:
** Pasang event listener di kedua input dan tombol submit, lalu saat tombol diklik, baca value dari kedua input tersebut. 
** Pasang event listener di form, lalu gunakan FormData untuk mengambil data dari masing-masing input
```
 const form = document.getElementById(“form”)

form.addEventListener(“submit”, function(event) {
	// cegah page refresh
	event.preventDefault()

	const formData = new FormData(form)
	const values = Object.fromEntries(formData) // { email: ... }
})
```
 















