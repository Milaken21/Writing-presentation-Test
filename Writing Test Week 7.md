# Sequalize
Sequelize adalah ORM (Object Relational Mapping) Node JS yang berbasis promise. Sequelize mendukung sebagian besar relational Database seperti MySQL, PostgresQL, MariaDB, SQLite dan Miscrosoft SQL Server. Dengan fitur fitur di Sequelize, kita bisa mengelola dan mengatur data di database kita dengan cepat, dan efisien.


## ORM
ORM adalah suatu metode/teknik pemrograman yang digunakan untuk mengkonversi data dari lingkungan bahasa pemrograman berorientasi objek (OOP) dengan lingkungan database relational. 

### generete sequalize
Pertama kita perlu melakukan inisialisasi di project kita terlebih dahulu agar dapat melakukan generate code
```
npx sequalize -cli init
```
* kita dapat menggunakan generate dan kita bisa mengecek ke database sehingga dapat kita gunakan untuk penimpanan DB
```
npx sequalize-cli db:migrate
```
* Jika ada yang salah, kita bisa mengembalikan (undo) menggunakan :
```
npx sequalize-cli db:undo
```
### generate model
membuat table todo dengan field
```
npx sequalize-cli model:generate --name Todo --attributes
tittle:string,description:string,startTime:date,status:string
```
Kita bisa melihat datanya menjadi sebuat class (OOP) dan dapat kita gunakan untuk membuat Rest API menggunakan express atau dapat memberikan behaviour di statenya

### generate seed
Seed adalah data awal yang bisa kita gunakan untuk mengisi data di database untuk keperluan awal project menggunakan sequelize
```
npx sequalize-cli seed:generate --name demo-todo
```
Ketika sudah berhasil melakukan generate maka kita dapat melakukan pengisian data seed didalam file seed generator. Terdapat 2 data yang diisi yaitu “up” untuk mengisi data di db, dan “down” untuk drop atau menghapus semua data seed di db
* Kita kemudian menjalankan generate seed menggunakan sequelize
```
npx sequalize-cli db:seed:all
```
```
npx sequalize-cli db:seed:undo
```
Ketika kita menjalankan generate seed menggunakan terminal, maka kita dapat melihat bahwa seeding kita sudah berhasil ter insert ke db.

## Membuat CRUD Dengan Express dan Sequelize
### Get All Todo
membuat sebuah routing entuk get all todo 
```
const TodoModel = require('./models').Todo;

app.get('/todos', async function (req, res) {
    try {
        const todos = await TodoModel.findAll();

        res.status(200).json(todos);
    } catch (error) {
        res.status(500).json({
            message: error.message || 'internal server error'
        });
    }
});
```
### Get Todo Detail By Id
```
const TodoModel = require('./models').Todo;

app.post('/todos/:todoId', async function (req, res) {
    try {
        const todos = await TodoModel.findAllOne({ id:Number(todoId) });

        res.status(200).json(todo);
    } catch (error) {
        res.status(500).json({
            message: error.message || 'internal server error'
        });
    }
});
```

### create new todo
```
const TodoModel = require('./models'.todo;

app.post('/todos/:todoId', async function (req, res) {
    try {
        const { tittle, description, starTime } = req.body;

        const newTodoData = {
            tittlr: tittle,
            description: description,
            startTime: startTime,
            status: 'false',
        };

        const newTodo = await TodoModel.create(newTodoData);

        res.status(201).json({
            message: 'new todo created',
            todo: newtodo,
        });
    } catch (error) {
        res.status(500).json({
            message: error.message || 'internal server error'
        });
    }
});
```

### create new todo
```
const TodoModel = require('./models'.todo;

app.patch('/todos/:todoId', async function (req, res) {
    try {
        const { todoId } = req.params
        const { tittle, description, starTime } = req.body;

        const UpdateTodoData = {
            tittlr: tittle,
            description: description,
            startTime: startTime,
            status: status,
        };

        const updatedTodo = await TodoModel.update(updateTodoData, {
            where: {
                id: todoId,
            }
        });

        res.status(200).json({
            message: 'update todo success',
            todo: newtodo,
        });
    } catch (error) {
        res.status(500).json({
            message: error.message || 'internal server error'
        });
    }
});
```


### Delete Todo By Id
```
const TodoModel = require('./models'.todo;

app.delete('/todos/:todoId', async function (req, res) {
    try {
        const { todoId } = req.params

        await TodoModel.destroy({
            where: {
                id: todoId,
            },
        })

        res.status(200).json({
            message: 'update todo success',
            todo: newtodo,
        });
    } catch (error) {
        res.status(500).json({
            message: error.message || 'internal server error'
        });
    }
});
```

## Connecting to a database
Untuk terhubung ke database, kita harus membuat instance Sequelize. Ini dapat dilakukan dengan meneruskan parameter koneksi secara terpisah ke konstruktor Sequelize atau dengan melewatkan satu koneksi URI
```
const { Sequelize } = require('sequelize');

// Option 1: Passing a connection URI
const sequelize = new Sequelize('sqlite::memory:') // Example for sqlite
const sequelize = new Sequelize('postgres://user:pass@example.com:5432/dbname') // Example for postgres

// Option 2: Passing parameters separately (sqlite)
const sequelize = new Sequelize({
  dialect: 'sqlite',
  storage: 'path/to/database.sqlite'
});

// Option 3: Passing parameters separately (other dialects)
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: /* one of 'mysql' | 'postgres' | 'sqlite' | 'mariadb' | 'mssql' | 'db2' | 'snowflake' | 'oracle' */
});
```

## Testing the connection
dapat menggunakan fungsi ```.authenticate()``` untuk menguji apakah koneksi baik-baik saja:
```
try {
  await sequelize.authenticate();
  console.log('Connection has been established successfully.');
} catch (error) {
  console.error('Unable to connect to the database:', error);
}
```

## Closing the connection
Sequelize akan membuat koneksi tetap terbuka secara default, dan menggunakan koneksi yang sama untuk semua kueri. Jika Anda perlu menutup koneksi, panggil ```sequelize.close()``` (yang asinkron dan mengembalikan Promise). 

## New databases versus existing databases
Jika Anda memulai proyek dari awal, dan database Anda masih kosong, Sequelize dapat digunakan sejak awal untuk mengotomatiskan pembuatan setiap tabel di database Anda.
Juga, jika Anda ingin menggunakan Sequelize untuk terhubung ke database yang sudah diisi dengan tabel dan data, itu juga berfungsi! Sequelize membuat Anda tercakup dalam kedua kasus.

## Logging
Secara default, Sequelize akan masuk ke konsol setiap kueri SQL yang dijalankannya. Opsi options.logging dapat digunakan untuk menyesuaikan perilaku ini, dengan mendefinisikan fungsi yang dijalankan setiap kali Sequelize akan mencatat sesuatu. Nilai default adalah console.log dan saat menggunakan itu hanya parameter log pertama dari panggilan fungsi log yang ditampilkan. Misalnya, untuk logging kueri, parameter pertama adalah kueri mentah dan yang kedua (disembunyikan secara default) adalah objek Sequelize.
Nilai umum yang berguna untuk ```options.logging:```
```
const sequelize = new Sequelize('sqlite::memory:', {
  // Choose one of the logging options
  logging: console.log,                  // Default, displays the first parameter of the log function call
  logging: (...msg) => console.log(msg), // Displays all log function call parameters
  logging: false,                        // Disables logging
  logging: msg => logger.debug(msg),     // Use custom logger (e.g. Winston or Bunyan), displays the first parameter
  logging: logger.debug.bind(logger)     // Alternative way to use custom logger, displays all messages
});
```
 

# MongoDB
MongoDB adalah salah satu database open source NoSQL yang cukup populer digunakan. MongoDB sering dipakai untuk aplikasi berbasis Cloud, Big Data maupun Grid COmputing. MongoDB menyimpan data menggunakan dokumen dengan format JSON.
## NoSQL 
NoSQL adalah Not Only SQL artinya kita bisa mengolah database dengan fleksibel dan tidak membutuhkan Query. kita memiliki skalabilitas yang tinggi sesuai dengan perkembangan data kita.

## Kelebihan MongoDB sebagai NoSQL
- Sistem tidak membutuhkan Tabel
- Tidak perlu menggunakan Tabel yang terstruktur
- By Default sudah menggunakan JSON(JavaScript Object Notation), sehingga memudahkan integrasi dengan JavaScript
- Performa lebih cepat dengan kemampuan menampung banyak data yang bervariasi

## Kekurangan MongoDB sebagai NoSQL
* Tidak mendukung transaksi
* Masalah konsistensi data
* Menggunakan banyak memory
* Hanya bisa menampung maksimal 16MB disetiap document

## Anatomi komponen dari Database MongoDB
* database adalah wadah untuk menyimpan berbagai macam Collection
* Collection adalah tempat kumpulan dari berbagai macam document, sehingga collection sering disamakan dengan tabel pada SQL
* Document adalah unit terkecil yang berada pada MongoDB
cotoh data pada mongoDB


# Mongoose
Mongoose adalah library yang bisa dibilang sebagai Object Modelling MongoDB untuk NodeJS. Mongoose bisa digunakan untuk mengelola hubungan antara data, menyediakan validasi. Dan juga digunakan untuk menerjemahkan antara objek dalam kode dan representasi Objek tersebut di MongoDB.

## simple CRUD
Sebelum membuat operasi CRUD, jangan lupa untuk menginstall express untuk routing dan body-parser, untuk menggunakan method Post dan testing API di postman
```
npm instal express
npm instal body-parser
```
Untuk menampilkan keseluruhan data (READ) kita bisa menggunakan fungsi find().
```
app.get('/users', (req, res) => {
    user.find{}, (error, users) => {
        if(error)
            return res.send(error);
    })
})
```
menggunakan method POST untuk mendaftarkan user, sebelum mendaftarkan kita mengecek dulu apakah user sudah ada atau belum dengan menggunakan findOne(), jika sudah ada akan muncul pesan error, jika belum terdaftar maka user akan didaftarkan menggunakan fungsi create(), Dan data user bisa diisi menggunakan Postman, Isi form raw dengan tipe JSON, atau bisa juga menggunakan form-data, untuk mendaftarkan user, setelah itu kita bisa menekan tombol send untuk mengirim request POST.
```
{
"name": "ridho"
"pasword": "aws"
"email": "ridho@gmail.com"
"phoneNumber": "0876543219"
}
```

```
app.get('/users/:id', (req, res) => {
    user.findById({
        -id : req.params.id
    }, (error, result) => {
        if(error){
            res.status(400).send({
                message: 'no date found',
            })
        } else {
            res.status(200).send({
                message: "showing data",
                result
            })
        }
    })
})
```
Dengan kode diatas kita akan mendapatkan data user berdasarkan id, dengan fungsi findById().
```
app.get('/users/:id', (req, res) => {
    User.deleteOne({
        -id : req.params.id
    }, (error, result) => {
        if(error){
            res.status(400).send({
                message: 'error, no id found, cannot delete',
            })
        } else {
            res.status(200).send({
                message: "delete success",
                result
            })
        }
    })
})
```
Dengan kode diatas kita akan menghapus satu data berdasarkan ID dengan menggunakan deleteOne().

```
app.put('/users/:id', (req, res) => {
    User.findByIdAndUpdate({
        -id : req.params.id
    }, {
        name: req.body.name,
        password: req.body.password,
        email: req.body.email,
        phoneNumber: req.body.phoneNumber 
    },  (error, result) => {
        if(error){
            res.status(400).send({
                message: 'error, no id found, cannot delete',
            })
        } else {
            res.status(200).send({
                message: "delete success",
                result
            })
        }
    })
})
```
Dengan kode diatas kita akan mengedit/update satu data berdasarkan ID dengan menggunakan findByIdAndUpdate().

## Populate
Populate ada kaitannya dengan relasi database. Populate adalah proses penggabungan 2 collection atau lebih menjadi satu objek JSON. Kita akan mengupdate schema user kita dan menambahkan address schema untuk mem-populate collection


# Docker
Docker adalah software yang menjalankan suatu aplikasi menggunakan container
Docker men-sharing kernel dari host OS, serta meng-container-kan suatu aplikasi agar dapat dijalankan dimana saja dan kapan saja
Aplikasi yg berjalan di dalam container docker tidak terpengaruh oleh faktor luar karena terisolasi
Docker berfungsi sebagai penyedia layanan virtual bagi aplikasi yg diinstall pada sebuah host. 
Docker akan menyediakan hal-hal yang diperlukan untuk aplikasi mulai dari akses file, koneksi internet, hingga port agar aplikasi dapat berjalan dengan mulus

### container vs vm
VM memakan banyak resource dan waktu utk booting karena melakukan virtualisasi pada host hardware-nya.  Sedangkan container kebalikannya dari vm, container melakukan virtualisasi pada host OS-nya
