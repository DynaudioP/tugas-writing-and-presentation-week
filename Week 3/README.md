# Rangkuman Writing & Presentation Week 3
## JavaScript Intermediate
## Array
 Array merupakan struktur data yang digunakan untuk menyimpan sekumpulan data dalam satu tempat. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.

```JS
const arr = ['Pokemon', 'Digimon', "Ninja"];
console,log(arr);
```

Array juga dapat menyimpan berbagai macam tipe data.

```JS
const arr = ['Pokemon', 'Digimon', 2 , 5 , true];
console,log(arr);
```

### Membuat Array
Kita dapat membuat array dengan menggunakan square brackets.
```JS
\\ Square Brackets 
[]
```

- Menggunakan Array Literal
Membuat Array dengan Array Literal.
    ```JS
    let hewan = ['Ayam', 'Sapi', 'Kelinci'];
    ```

- Menggunakan Kata Kunci new
Membuat Array dengan kata kunci new
    ```JS
    let buah = new Array( 'Mangga', 'Apel', 'Jeruk');
    ```

### Mengakses Array
Array akan menyimpan sekumpulan data dan memberinya nomer indeks agar mudah diakses. Indeks array selalu diawali dari nol 0.

```JS
let hewan = ['Ayam', 'Sapi', 'Kelinci'];

console.log(hewan[0]) // Ayam
```

### Update Array
Data/element di suatu array bisa kita tambah/ubah/hapus

```JS
let hewan = ['Ayam', 'Sapi', 'Kelinci'];

console.log(hewan[0]); // Ayam - Sebelum di update

hewan[0] = 'Kambing';

console.log(hewan[0]); // Kambing - Se di update
```

### Const in Array
Jika menggunakan let, kita dapat mengubah array  dengan array baru dan konten nilai yang ada di dalam array dengan nilai lain Const tidak bisa melakukan update data. Namun pada Array kita dapat melakukan update konten nilai di dalam array (mutable).
```JS
const hewan = ['Ayam', 'Sapi', 'Kelinci'];
hewan[2] = ['Kuda'];

console.log(hewan)// Output : Error. Tidak bisa update array baru
```

### Array Properties
Array memiliki 5 properti yang sering digunakan yaitu
- constructor
- length
- index
- input
- prototype

```JS
////// Length digunakan untuk mengembalikan jumlah panjang data dari array ///////
const hewan = ['Ayam', 'Sapi', 'Kelinci'];

console.log(hewan.length) // 3 
```

### Array Methods
Array memiliki method atau biasa disebut built-in methods, yang sama dengan function yang dapat digunakan kapan saja kita membutuhkannya.

- push
menambahkan array pada index terakhir
- pop
Menghapus array pada index terakhir
- shift
Menghapus array pada index pertama
- unshift
Menambahkan array pada index pertama
- sort
Mengurutkan array secara ascending maupun descending

```JS
///// Contoh menggunakan method .pop()
const hewan = ['Ayam', 'Sapi', 'Kelinci'];
hewan.pop();

console.log(hewan) // 'Ayam', 'Sapi'
```

### Looping pada Array.
Built in methods untuk melakukan looping pada array ada 2
- forEach
untuk melakukan looping pada setiap elemen array.
    ```JS
    const hewan = ['Ayam', 'Sapi', 'Kelinci'];
    
    hewan.forEach(element => {
    console.log(element);
    });
    ```
- map
Untuk melakukan perulangan/looping dengan membuat array baru.
    ```JS
    let arr = [1,2,3,4,5];
    
    let doubled = arr.map(num => {
        return num * 2;
    });
    console.log(doubled);
    ```
    
Letak perbedaannya hanya jika forEach akan melakukan perulangan pada setiap element array tanpa membuat array baru, sedangkan map akan melakukan perulangan dan menghasilkan nilai balik berupa array baru

## Multidimensional Array
Multidimensional Array adalah array yang menyimpan array lain pada setiap indeks, bukan elemen tunggal. 

Dengan kata lain, kita dapat mendefinisikan array multi dimensi sebagai array dari suatu array. 
```JS
let tas = [
    ['Buku' , 6],
    ['Pensil' , 2],
    ['Penghapus' , 1],
    ['Pulpen' , 2],
];
console.log(tas);
```

### Mengakses Multidimensional Array
Kita dapat mengakses Multidimensional Array menggunakan dua square brackets
```JS
let tas = [
    ['Buku' , 6],
    ['Pensil' , 2],
    ['Penghapus' , 1],
    ['Pulpen' , 2],
];
console.log(tas[1][0]); // 'Pensil'
```

### Penggunaan Built-in Method pada Multidimensional Array
Kita dapat menggunakan built in method array di sebuah dimensional array
```JS
let tas = [
    ['Buku' , 6],
    ['Pensil' , 2],
    ['Penghapus' , 1],
    ['Pulpen' , 2],
];

tas.push(['Pensil', 2])
console.log(tas);
```

### Operation using map in Multidimensional Array
Kita bisa menggunakan map di Multidimensional Array
```JS
let tas = [
    ['Buku' , 6],
    ['Pensil' , 2],
    ['Penghapus' , 1],
    ['Pulpen' , 2],
];

tas.map(dataTas => {
    let terjual = 100 - dataTas[1];
    dataTas[2] = terjual;
});
console.log(tas);
```

### Looping for Multidimensional Array
Kita bisa melakukan perulangan pada Multidimensional Array
```JS
let tas = [
    ['Buku' , 6],
    ['Pensil' , 2],
    ['Penghapus' , 1],
    ['Pulpen' , 2],
];

tas.forEach((baris) => {
    baris.forEach((column) => {
        console.table(column);
    });
});
```

## Object
Object adalah sebuah tipe data yang pada variabelnya dapat menyimpan properti maupun function/method. Sama seperti Array dalam sebuah object dapat menyimpan segala jenis tipe data. Object pun dapat mengupdate nilai pada variabelnya dengan cara menambahkan atau menghapusnya. 

### Membuat Sebuah Object
- Menggunakan Object Literal
Membuat Object dengan Object Literal.
```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};
```

- Menggunakan Kata Kunci new
Membuat Object dengan kata kunci new
```JS
let orang = new Object();

orang.nama = 'dio';
orang.umur = 19;
orang.pekerjaan = 'mahasiwa';
```

### Mengakses Object dan Property Object
Kita dapat mengakses object dengan memanggil nama variabel object tersebut.
```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};

console.log(orang)
```

Terdapat 2 cara untuk mengakses properti object yaitu:
- Dot Notation
Kita dapat mengakses properti object menggunakan dot notation.
```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};

console.log(orang.nama) // 'dio'
```

- Bracket Notation
Kita dapat mengakses properti object menggunakan bracket notation.
```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};

console.log(orang['umur']) // 19
```

### Update Object
Kita dapat melakukan update pada variabel dengan tipe data Object. 
- Object dapat mengupdate value dari key yang sudah tersedia
- Object dapat menambah key dan value baru

```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};

orang.age = 23;
console.log(orang);
```

### Delete Object Property
Kita dapat menghapus properti dari object menggunakan delete operator.
```JS
let orang = {
  nama: 'dio',
  umur: 19,
  pekerjaan: 'mahasiswa'
};

delete orang.age;
console.log(orang);
```

### Method Object
Jika value yang kita masukkan pada property berupa function. Maka itu disebut method.
```JS 
let ayam = {
    enak: true,
    kaki: 2,
    suara: function(){
        return "ku ku riuk";
    }
};

console.log(ayam.suara())
```

### Nested Object
Nested object adalah sekumpulan objek dapat “bersarang” atau nested di dalam objek lain yang mana setiap objek bersarang memiliki jalur akses yang unik.
```JS
var mahasiswa = {
    "nim": 2009116023,
    "nama" : "dio", 
    "kelas" : {
        "id" : "si05",
        "semester" : 5,
        "jurusan" : {
            "id": 105,
            "nama" : "Sistem Informasi",
            "alias" : "SI"
        }
    }
};

console.log(mahasiswa.kelas.jurusan.nama);
console.log(mahasiswa['kelas']['jurusan']['alias']);
```

### Pass By Reference
Kita bisa mengubah data yang ada pada object melalui sebuah function dan memasukkan object sebagai parameter function. Ini biasa disebut passed by reference.
```JS
let number = {
    originA: 2,
	originB: 3,
}

function changeData (obj) {
	obj.originA = 4;
	obj.originB = 6;
}

changeData(number)
console.log(number.originA); // 4
console.log(number.originB); // 6
```

### Looping pada Object
Jika kita ingin menampilkan seluruh object properti. Kita bisa menggunakan looping.
```JS
for(let key in object) {
	// ...
}
```

### Array Of Object
Object sama seperti Array yang bisa menyimpan banyak data. Kita dapat menggunakan array of object untuk data yang lebih dari satu.
```JS
let orang = {
    {
    nama: 'dio',
    umur: 19,
    pekerjaan: 'mahasiswa'
    },
    {
    nama: 'curry',
    umur: 30,
    pekerjaan: 'atlet' 
    }
};

orang.forEach((listOrang) => {
    console.log(listOrang);
});
```

## Javascript Recursive
Rekursif adalah sebuah function yang memanggil dirinya sendiri sampai kondisi tertentu. Biasanya digunakan untuk kasus yang melibatkan operasi matematika di dalamnya. Tujuan utama dari rekursif adalah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.

### A New Paradigm
- procedural
- conditional
- looping
- modular (function)
- recursive


### Ciri-ciri dari recursive
- Fungsi recursive memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti.
- Fungsi recursive selalu memaanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.

### Struktur Recursive
Berikut merupakan struktur Recursive
```JS
function recursive() {
	if(condition) {
		// berhenti memanggil diri sendiri
	} else {
		recursive();
	}
}
```

### Contoh Kasus Recursive
Mencari hasil dari nilai pangkat dengan rekursif

```JS
function pow(x,n) {
    if (n=1){
        return x;
    } else {
        return x * pow(x, n-1);
    }
}
console.log(pow(2,3)) // 8
```

### Modules
Modules adalah reusable code, artinya data atau kodingan yang dapat digunakan berkali-kali. Modules memungkinkan untuk memecah kode menjadi file terpisah sehingga mempermudah untuk maintain code. Ada beberapa tindakan yang ada di dalam modules. 
- Export
- Import
- Export as
- Import as
- Export Default

## Web Storage
Web Storage adalah wadah untuk sebuah data yang digunakan untuk penyimpanan data yang terikat di browsernya. Jenis Web Storage yang umumnya adalah 
- local 
- session 
- indexDB

### localStorage
localStorage merupakan salah satu cara yang dapat digunakan untuk menyimpan data di web browser. Pada Local Storage penyimpanan data tidak memiliki kadaluarsa, artinya data yang disimpan tetap ada meskipun browser telah ditutup. Ada 4 Metode yang dapat digunakan dalam menggunakan localStorage, yaitu :
- setItem
Digunakan untuk menyimpan data kedalam localStorage. Dalam penggunaannya dibutuhkan dua parameter yaitu key dan value.
    ```JS
      window.localStorage.setItem('Makanan', 'Sate');
      window.localStorage.setItem('Minuman','Es Teh');
    ```
- getItem
Digunakan untuk untuk mengakses data yang disimpan pada localStorage.
    ```JS
    let tes = localStorage.getItem('Minuman'));
    console.log(tes)
    ```
- removeItem
Digunakan untuk menghapus data tertentu pada penyimpanan localStorage bedasarkan key.
    ```JS
    window.localStorage.removeItem('Minuman')
    ``` 
- clear
Digunakan untuk menghapus seluruh data yang telah tersimpan di localStorage.
    ```JS
    window.localStorage.clear()
    ```

### sessionStorage
sessionStorage menyimpan data secara sementara, data akan menghilang saat tab ditutup atau browser ditutup. sessionStorage memiliki metode yang sama dengan localStorage yaitu:
- setItem
Digunakan untuk menyimpan data.
    ```JS
    window.sessionStorage.setItem("data_object")
    ```
- getItem
Mengambil data dari sessionStorage.
    ```JS
    let dataObject = sessionStorage.getItem("data_object")
    console.log(dataObject)
    ```
- removeItem
Digunakan untuk menghapus data tertentu bedasarkan key.
    ```JS
    window.sessionStorage.removeItem('nasi')
    ```
- clear
Digunakan untuk menghapus seluruh data yang telah tersimpan di sessionStorage.
    ```JS
    window.sessionStorage.clear()
    ```

## Asynchronous
Asynchronous sebuah teknik yang menyelesaikan fungsi secara paralel. Langkah yang dijalankan akan berjalan secara paralel atau bisa dijalankan dalam waktu yang bersamaan. Artinya kita mengizinkan program untuk menjalankan perintah lain sambil menunggu proses yang lain sedang dijalankan. 

Mengapa perlu menggunakan asynchronous? Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Jadi kita bisa mengerjakan proses yg lain secara paralel.

### Contoh Asynchronous
```JS
setTimeout(() => {

    console.log(2)

}, 0);

log(3)
```

### Event Loop
Event loop adalah bagian dari JavaScript Runtime yang bertugas untuk menangani Event Callback, Event Callback sendiri adalah bagian dari code yang dieksekusi setelah event tertentu.

Ketika event terjadi maka callback dari event tersebut akan ditempatkan pada suatu tempat yang disebut Event Handler Queue atau Queue. Event Loop akan terus memonitor Queue dan akan mengeksekusi callback sesuai urutan siapa yang pertama masuk ke dalam Queue.

### Callback JavaScript
Callback adalah function yang menjadi argument untuk function lain dan akan dieksekusi pada poin tertentu, bisa jadi saat ini atau nanti.

```JS
const notify = () => {
  console.log('Download complete!');
};
const download = (url, callback) => {
  console.log(`Downloading from ${url}....`);
  callback();
};
```

### Promise
Promise bisa dikatakan sebagai object yang menyimpan hasil dari sebuah operasi asynchronous baik itu hasil yang diinginkan (resolved value) atau alasan kenapa operasi itu gagal (failure reason).

Sebuah Promise berada di salah satu diantara 3 kondisi(state):
- pending, operasi sedang berlangsung
- fulfilled, operasi selesai dan berhasil
- rejected, operasi selesai namun gagal

### Membuat Promise
Keyword yang dipakai untuk membuat Promise adalah Promise.
```JS
let progress = 100;
const download = new Promise((resolve, reject) => {
  if (progress === 100) {
    resolve('Download complete');
  } else {
    reject('Download failed');
  }
});
```

### Async Await
Async/Await digunakan untuk menghandle operasi asynchronous dengan syntax yang lebih mirip dengan synchronous.

```JS
const getStatus = (url) => {
  console.log(`Downloading from ${url}...`);
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Download Complete');
    }, 3000);
  });
};
async function download(url) {
  let status = await getStatus(url); // tunggu sampai promise selesai
  console.log(status);
}
const url = 'https://brachio.site/download';
download(url);
```

### Async Fetch
merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karena Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah then jika promise mengembalikan resolve dan catch jika promise mengembalikan nilai reject.
```JS
get_user_data = () => {
	fetch('/api/user/' + user_id)
	.then(response => { response.json() })
	.then(res => { ... })
	.catch(error => {console.log(error) })
}
```

### API 
Application programming interface atau API adalah seperangkat kode pemrograman yang membantu developer mengintegrasikan data antara dua aplikasi yang berbeda secara bersamaan. Application programming interface memungkinkan pengembang untuk membangun aplikasi menggunakan berbagai elemen seperti fungsi, protokol, dan alat lainnya.

### HTTP 
HTTP atau singkatan dari Hypertext Transfer Protocol merupakan protokol jaringan lapisan aplikasi (application layer) berfungsi membantu proses transfer data / informasi antar komputer. Protokol ini mampu mentrasnfer data seperti dokumen, file, gambar, audio hingga video.

### HTTP Request
adalah sebuah aktivitas dimana client meminta kepada Server.

Contoh:
![request](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_request.png)

Klien (browser) mengirimkan permintaan HTTP ke server; kemudian server mengembalikan respons ke klien. Tanggapan berisi informasi status tentang permintaan dan mungkin juga berisi konten yang diminta.

Method-nya terdiri dari :
- GET.
- POST.
- PUT.
- HEAD.
- DELETE.
- PATCH.
- OPTIONS.













