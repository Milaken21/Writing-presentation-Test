WEB DEVELOPMENT ADVANCE
Day 1
Javascript intermediate - multidimensional array

multidimensional array atau arry of array artinya ada array di dalam array
contoh
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

console.log(inventory);
```
* Array multidimensional bisa diibaratkan seperti table, baris pada table itu menunjukkan jumlah array, sedangkan column pada table itu menunjukkan isi dari tiap array.

# Akses index multidimensional array
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

console.log(inventory[1][0]);
// output: jaket hoodie;
```
Sama seperti array satu dimensi, multidimensional array juga dapat menggunakan Property dan Method built-in Array.
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

inventory.push(['jaket sweater', 7]);
console.log(inventory)
// Output: 
// [
//    ['kaos polos', 10],
//    ['jaket Hoodie', 12], 
//    ['Topi', 24],
//    ['Celana Jeans', 8],
//    ['Jaket Sweater', 7],
// ]
```
# Operation using map in multidimensional array
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

// menghitung produk yang terjual.
// kita anggap jumlah stok awal 100 untuk seluruh produk.
inventory.map(dataInventory => {
    let terjual = 100 - dataInventory[1];
    dataInventory[2] = terjual;
});

console.table(inventory);
```
# LOOPONG FOR MULTIDIMENSIONAL ARRAY
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

inventory.forEach((baris) => {
    baris.forEach((column) => {
        console.log(column);
    });
});

// output
// kaos polos
// 10
// Jaket Hoodie
// 12
// Topi
// 24
// Celana Jeans
// 8
```
* using FOR LOOP
```
let inventory = {
    ['kaos polos', 10],
    ['jaket Hoodie', 12], 
    ['Topi', 24],
    ['Celana Jeans', 8],
};

// This loop is for outer array
for (var i = 0, L1 = inventory.length; i < L1; i++) {

    // This loop is for inner-arrays
    for(var i = 0, L2 = inventory[i].length; j < L2; j++) {

        //Accesing each elements of inner array
        document.write( '<p>' + inventory[i][j] + '</p>');
    }
}
```

WEB DEVELOPMENT ADVANCE
Day 2
Javascript intermediate - object

# Object
object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method).
* Properti adalah data lengkap dari sebuah object.
* Method adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.
* contoh mobil memiliki properti nama, model, dan warna. mobil memiliki method start(), drive(), dan stop()

# Membuat sebuah object
Object dapat diassign kedalam sebuah variabel.
```
let person = {}; //person adalah object kosong
```
```
let person = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}
```
Sama seperti array, didalam object kita dapat menyimpan properti dengan tipe data apapun.

# Mengakses object dan Property Object
```
let person = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}

// memanggil variabel untuk mengakses object
console.log(person);
```
```
let people = {
    name: 'john Doe',
    age: 25,
    'current address': 'cambridge, UK',
}
```
gunakan single quote pada key jika menggunakan spaso seperti 'current address'

```
let person = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}

// memanggil variabel dengan properti
console.log(person.name); // 'John Doe'
```
Mengakses properti object

* Bracket Notation
menggunakan bracket notation untuk memanggil properti
```
let people = {
    name: 'john Doe',
    age: 25,
    'current address': 'cambridge, UK',
}

console.log(people['name']); // 'John Doe'
Console.log(people['current addres']) // 'cambridge, UK'
```

# Update Object
* DO
    * Object dapat mengupdate value dari key yang sudah tersedia
    * Object dapat menambahkan key dan value baru
```
let person = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}

// update current key with thw new value
people.age = 27;

// add new key and value
people.address = 'Cambridge, UK';

console.log(people);
// output
// {
//    name: 'john Doe',
//    age: 27,
//    isVerified: true,
//    'current address': 'cambridge, UK',
// }
```
* DONT'S
Jika menggunakan constant pada variable object. Kita tidak bisa mengganti seluruh data object dengan object yang baru.
```
let people = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}

people = {
    fullname: 'John Doe'
}

console.log(people); // Uncaught TypeError: Assignment to constant variable.
```
Jadi jika membutuhkan untuk update seluruh data object gunakan ‘let’ pada saat deklarasi variabel.

# Delete Object Property
dapat menghapus properti dari object menggunakan delete operator.
```
let people = {
    name: 'John Doe',
    Age: 25,
    isVerified: true,
}

delete people.age;

console.log(people);
// Output
// {
//    name: 'John Doe',
//    isVerified: true,
// },
```
menghapus properti object age dari data people

# Method
Value yang dimasukkan pada property berupa function, maka itu disebut method.
* console adalah global javascript object.
* log() adalah property yang berupa function dari object console.
* membuat method custom
```
const greeting = {
    welcome: function () {
        return 'Halo selamat datang';
    },
    afterTransaction: function () {
        return 'Terima kasih sudah membeli produk kami';
    },
};

console.log(greeting.welcome()); // 'Halo selamat datang'
```
terdapat 2 method pada obeject greeting

# Nasted Object
Object yang berasal dari turunan object lainnya.
```
const news = {
    title: 'Impact Byte menjadi Unicorn',
    description: 'Lorem ipsum dolor sit amt consectetur adipiscing elit',
    author: {
        people: {
            name: 'David Winalda',
            age: 25,
            city: 'Bandung',
        }
    }
};

console.log('News:', news.title);
console.log('Article published by', news.author.people.name);

//output
//'News: Impact Byte menjadi Unicorn'
// 'Article published by David Winalda'
```

# Pass by reference
mengubah data yang ada pada object melalui sebuah function dan memasukkan object sebagai parameter function.
```
let number = {
    originA: 2,
    originB: 3,
};

function changeData (obj) {
    obj.originA = 4;
    obj.originB = 6;
};

changeData(number)
console.log(number.originA); // 4
console.log(number.originB); // 6
```
mengubah data object number dengan sebuah function changeData

# Looping Object
Jika ingin menampilkan seluruh object properti. bisa menggunakan looping. Jadi tidak perlu mengakses secara manual memanggil setiap propertinya.
```
for(let key in object) {
    // ...
};
```
looping pada object
```
const news = {
    title: 'Impact Byte menjadi Unicorn',
    description: 'Lorem ipsum dolor sit amt consectetur adipiscing elit',
    author: {
        people: {
            name: 'David Winalda',
            age: 25,
            city: 'Bandung',
        }
    }
};

for(let data in news) {
    console.log(news[data]);
};
// 'Impact Byte menjadi Unicorn'
// 'Lorem ipsum dolor sit amt consectetur adipiscing elit'
// people {...}

for(let author in news.author.people) {
    console.log(news.author.people[author]);
}
// 'David Winalda'
// 25
// 'Bandung'
```

# Array of Object
* Object tidak hanya menyimpan satu data
* Object sama seperti Array yang bisa menyimpan banyak data
* bisa menggunakan array of object untuk data yang lebih dari satu.
```
let students = [
    {
        name: 'John Doe',
        age: 25,
        isVerified: true,
    },
    {
        name: 'Dava Winalda',
        age: 26,
        isVerified: false,
    },
    {
        name: 'Ryan Snom',
        age: 30,
        isVerified: true,
    }
];

// Gunakan forEach jika object berada di dalam array
students.forEach((listStudent) => {
    console.log(listStudent);
})
```
looping pada data array of object students

WEB DEVELOPMENT ADVANCE
Day 3
Javascript intermediate - Recursive

* Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu.
* Recursive kebanyakan digunakan untuk case matematika, fisika, kimia, dan yang berhubungan dengan calculation.
```
function recursive() {
    // ...
    recursive();
    // ...
}
```
```
function recursive() {
    if(condition) {
        // stop calling itself
        // ...
    } else {
        recursive();
    }
}
```
recursive  akan berhenti memanggil dirinya sendiri jika kondisi terpenuhi

# Ciri Rekursif
* Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.
* Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

# Contoh kasus rekursif
```
function countDown(fromNumber) {
    console.log(fromNumber);

    let nextNumber = fromNumber -1;

    // jika kondisi ini bernilai false maka recursive berhenti
    if (nextNumber > 8) {
        countDown(nextNumber)
    }
}
countDown(3);

// output
// 3
// 2
// 1
```
fungsi rekursif menghitung mundur number
``` 
function pow(x, n) {
    if (n == 1) {
        return x;
    } else {
        return x * pow(x,n-1);
    }
}

console.log(pow(2, 3)); // 8
```
mencari hasil dari nilai pangkat dengan rekursive


WEB DEVELOPMENT ADVANCE
Day 4
Javascript intermediate - asyncronus

# Asynchronous
Pemrograman asinkron adalah teknik yang memungkinkan program Anda untuk memulai tugas yang berpotensi berjalan lama dan masih dapat responsif terhadap peristiwa lain saat tugas itu berjalan, daripada harus menunggu sampai tugas itu selesai.
```
const name = 'Miriam';
const greeting = `Hello, my name is ${name}!`;
console.log(greeting);
// "Hello, my name is Miriam!"
```
Pada setiap titik, browser menunggu baris untuk menyelesaikan pekerjaannya sebelum melanjutkan ke baris berikutnya. 

Itu membuatnya menjadi program yang sinkron . akan tetap sinkron bahkan jika kita memanggil fungsi yang terpisah, seperti ini:
```
function makeGreeting(name) {
  return `Hello, my name is ${name}!`;
}

const name = 'Miriam';
const greeting = makeGreeting(name);
console.log(greeting);
// "Hello, my name is Miriam!"
```
Di sini, makeGreeting()adalah fungsi sinkron karena pemanggil harus menunggu fungsi menyelesaikan pekerjaannya dan mengembalikan nilai sebelum pemanggil dapat melanjutkan.

# Fungsi sinkron yang berjalan lama
Bagaimana jika fungsi sinkron membutuhkan waktu lama?

Program di bawah ini menggunakan algoritme yang sangat tidak efisien untuk menghasilkan banyak bilangan prima besar ketika pengguna mengklik tombol "Hasilkan bilangan prima". Semakin tinggi jumlah bilangan prima yang ditentukan pengguna, semakin lama operasi akan berlangsung.
```
<label for="quota">Number of primes:</label>
<input type="text" id="quota" name="quota" value="1000000" />

<button id="generate">Generate primes</button>
<button id="reload">Reload</button>

<div id="output"></div>
```
```
const MAX_PRIME = 1000000;

function isPrime(n) {
  for (let i = 2; i <= Math.sqrt(n); i++) {
    if (n % i === 0) {
      return false;
    }
  }
  return n > 1;
}

const random = (max) => Math.floor(Math.random() * max);

function generatePrimes(quota) {
  const primes = [];
  while (primes.length < quota) {
    const candidate = random(MAX_PRIME);
    if (isPrime(candidate)) {
      primes.push(candidate);
    }
  }
  return primes;
}

const quota = document.querySelector('#quota');
const output = document.querySelector('#output');

document.querySelector('#generate').addEventListener('click', () => {
  const primes = generatePrimes(quota.value);
  output.textContent = `Finished generating ${quota.value} primes!`;
});

document.querySelector('#reload').addEventListener('click', () => {
  document.location.reload();
});
```
Coba klik "Generate primes". Tergantung pada seberapa cepat komputer Anda, mungkin diperlukan beberapa detik sebelum program menampilkan pesan "Selesai!".

Cara yang dibutuhkan
* Mulai operasi yang berjalan lama dengan memanggil fungsi.
* Suruh fungsi tersebut mulai beroperasi dan segera kembali, agar program kita tetap bisa responsif terhadap event-event lainnya.
* Beritahu dengan hasil operasi ketika akhirnya selesai.

# Event handlers
Penangan acara benar-benar merupakan bentuk pemrograman asinkron: Anda menyediakan fungsi (penangan acara) yang akan dipanggil, tidak segera, tetapi kapan pun peristiwa itu terjadi. Jika "peristiwa" adalah "operasi asinkron telah selesai", maka peristiwa tersebut dapat digunakan untuk memberi tahu pemanggil tentang hasil pemanggilan fungsi asinkron.

Beberapa API asinkron awal menggunakan peristiwa hanya dengan cara ini. XMLHttpRequestAPI memungkinkan Anda membuat permintaan HTTP ke server jauh menggunakan JavaScript . Karena ini bisa memakan waktu lama, ini adalah API asinkron, dan Anda akan diberi tahu tentang kemajuan dan penyelesaian akhir permintaan dengan melampirkan event listener ke XMLHttpRequestobjek.

# Callback
Penangan acara adalah jenis panggilan balik tertentu. Panggilan balik hanyalah fungsi yang diteruskan ke fungsi lain, dengan harapan bahwa panggilan balik akan dipanggil pada waktu yang tepat. Seperti yang baru saja kita lihat, callback dulunya merupakan cara utama penerapan fungsi asinkron dalam JavaScript.

Namun, kode berbasis panggilan balik bisa menjadi sulit untuk dipahami ketika panggilan balik itu sendiri harus memanggil fungsi yang menerima panggilan balik. Ini adalah situasi umum jika Anda perlu melakukan beberapa operasi yang dipecah menjadi serangkaian fungsi asinkron. Misalnya, pertimbangkan hal berikut:
```
function doStep1(init) {
  return init + 1;
}

function doStep2(init) {
  return init + 2;
}

function doStep3(init) {
  return init + 3;
}

function doOperation() {
  let result = 0;
  result = doStep1(result);
  result = doStep2(result);
  result = doStep3(result);
  console.log(`result: ${result}`);
}

doOperation();
```
Di sini kita memiliki satu operasi yang dibagi menjadi tiga langkah, di mana setiap langkah bergantung pada langkah terakhir. Dalam contoh kita, langkah pertama menambahkan 1 ke input, yang kedua menambahkan 2, dan yang ketiga menambahkan 3. Dimulai dengan input 0, hasil akhirnya adalah 6 (0 + 1 + 2 + 3). Sebagai program sinkron, ini sangat mudah. Tetapi bagaimana jika kita menerapkan langkah-langkah menggunakan panggilan balik?
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

Karena alasan ini, sebagian besar API asinkron modern tidak menggunakan callback. Sebaliknya, dasar dari pemrograman asinkron dalam JavaScript adalah Promise.

# Javascript promise
“Bayangkan kamu masih kecil . Ibumu berjanji padamu bahwa dia akan membelikanmu telepon baru minggu depan.”

Anda tidak tahu apakah Anda akan mendapatkan telepon itu sampai minggu depan. Ibumu benar- benar bisa membelikanmu telepon baru, atau dia tidak .

Itu adalah sebuah janji . Sebuah janji memiliki tiga keadaan. Mereka:

* Tertunda: Anda tidak tahu apakah Anda akan mendapatkan telepon itu
* Terpenuhi: Ibu senang , dia membelikanmu ponsel baru
* Ditolak: Ibu tidak bahagia , dia tidak membelikanmu telepon

# Membuat promise
```
// ES5: Part 1

var isMomHappy = false;

// Promise
var willIGetNewPhone = new Promise(
    function (resolve, reject) {
        if (isMomHappy) {
            var phone = {
                brand: 'Samsung',
                color: 'black'
            };
            resolve(phone); // fulfilled
        } else {
            var reason = new Error('mom is not happy');
            reject(reason); // reject
        }

    }
);
```
kode ini cukup ekspresif
Di bawah ini adalah bagaimana sintaks janji terlihat normal:
```
// promise syntax look like this
new Promise(function (resolve, reject) { ... } );
```

# Consuming Promise
Sekarang kita punya promisi
```
// ES5: Part 2

var willIGetNewPhone = ... // continue from part 1

// call our promise
var askMom = function () {
    willIGetNewPhone
        .then(function (fulfilled) {
            // yay, you got a new phone
            console.log(fulfilled);
             // output: { brand: 'Samsung', color: 'black' }
        })
        .catch(function (error) {
            // oops, mom didn't buy it
            console.log(error.message);
             // output: 'mom is not happy'
        });
};

askMom();
```

# Chaining Promises
Janji dapat diika atau dirantai

Katakanlah Anda, anak itu, berjanji kepada teman Anda bahwa Anda akan menunjukkan kepada mereka telepon baru ketika ibumu membelikan Anda satu.
```
// ES5

// 2nd promise
var showOff = function (phone) {
    return new Promise(
        function (resolve, reject) {
            var message = 'Hey friend, I have a new ' +
                phone.color + ' ' + phone.brand + ' phone';

            resolve(message);
        }
    );
};
```
Catatan: Kita dapat mempersingkat kode di atas dengan menulis seperti di bawah ini:
```
// shorten it

// 2nd promise
var showOff = function (phone) {
    var message = 'Hey friend, I have a new ' +
                phone.color + ' ' + phone.brand + ' phone';

    return Promise.resolve(message);
};
```
Mari kita rantai janji. Anda, anak itu, hanya bisa memulai showOffjanji setelah willIGetNewPhonejanji.
```
// call our promise
var askMom = function () {
    willIGetNewPhone
    .then(showOff) // chain it here
    .then(function (fulfilled) {
            console.log(fulfilled);
         // output: 'Hey friend, I have a new black Samsung phone.'
        })
        .catch(function (error) {
            // oops, mom don't buy it
            console.log(error.message);
         // output: 'mom is not happy'
        });
};
```
Itu adalah bagaimana Anda dapat mengikat janji.

# Janji tidak sinkron
Janji tidak sinkron. Mari kita log pesan sebelum dan sesudah kita memanggil janji.
```
// call our promise
var askMom = function () {
    console.log('before asking Mom'); // log before
    willIGetNewPhone
        .then(showOff)
        .then(function (fulfilled) {
            console.log(fulfilled);
        })
        .catch(function (error) {
            console.log(error.message);
        });
    console.log('after asking mom'); // log after
}
```
Apa urutan output yang diharapkan? Anda mungkin mengharapkan:
```
1. before asking Mom
2. Hey friend, I have a new black Samsung phone.
3. after asking mom
```
Namun, urutan output yang sebenarnya adalah:
```
1. before asking Mom
2. after asking mom
3. Hey friend, I have a new black Samsung phone.
```
Anda tidak akan berhenti bermain sambil menunggu janji ibumu (ponsel baru). Itu adalah sesuatu yang kami sebut asynchronous : kode akan berjalan tanpa memblokir atau menunggu hasilnya. Apa pun yang perlu menunggu janji untuk melanjutkan dimasukkan ke dalam .then.






