
# Rangkuman Writing & Presentation Week 1
## JavaScript Dasar
## Scope
 Scope adalah area dari cakupan kode agar bisa berjalan maupun diakses oleh kode lainnya. Terdapat tiga jenis scope, yakni global scope, local scope, dan block scope.
- Global Scope
Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file. Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.

- Local Scope
Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping. Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.

- Block Scope
Blocks adalah code yang berada didalam curly braces. Conditional, function, dan  looping menggunakan blocks.

## Function
Fungsi adalah satu blok (kumpulan) perintah coding (statemens) yang mempunyai tujuan atau fungsi tertentu. Fungsi diproses atau dieksekusi apabila dipanggil oleh coding yang lain. Jadi kita tidak perlu untuk menulis kode yang sama secara berulang. Memudahkan kita untuk nilai data yang membutuhkan metode yang sama.

### Parameter
adalah syarat input yang harus dimasukkan ke dalam suatu fungsi dan dideklarasikan bersama dengan deklarasi fungsi.

### Argument
adalah nilai yang dimasukan ke dalam suatu fungsi, sesuai dengan persyaratan parameter, di mana argument dituliskan bersamaan dengan pemanggilan fungsi.

```js
function segitiga(alas,tinggi){
    let luas = 0.5 * alas * tinggi;
    return luas;
}
console.log(segitiga(5,10)); // Output: 25 
```

- Alas dan tinggi Adalah Parameter. Disini parameternya mempunyai syarat input bertipe number.
- 5 dan 10 adalah Argument. Sesuai dengan persyaratan input parameter yaitu tipe number.

### Default Parameter
Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function.

```js
function absen(nama = "Zidan"){
    return "Selamat Pagi " + nama;
}
console.log(absen("Abdul")); // Output: Selamat Pagi Abdul
console.log(absen()); // Output: Selamat Pagi Zidan
```

### Function Helper
Kita dapat menggunakan function yang telah dibuat pada function yang lain.
```js
function multiplyByNineFifths(number) {
	return number * (9/5);
}

function getFahrenheit(celcius) {
	return multiplyByNineFifths(celcius) + 32;
}

getFahrenheit(15); // Output 59
```


### Arrow Function
Arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)
```JS
let hello;

hello = () => {
  return "Hai teman";
}
```

## Data types
Tipe data adalah jenis data yang dapat disimpan, dimanipulasi, dan digunakan untuk memberi tahu komputer bagaimana menfasirkan nilai atau datanya. Tipe data menentukan jenis data yang dimiliki variabel dan tipe operasi, seperti operasi matematika, logika dan sebagainya. Tipe data di JavaScript dikelompokkan di ke dalam dua kategori primitif dan non-primitif.

### Primitif
Tipe data primitif hanya dapat menyimpan satu nilai pada satu waktu dan tidak dapat diubah menggunakan cara yang sama seperti tipe data non-primitif. Tipe data Primitif akan dianggap sama jika nilainya sama. Berikut tipe data primitif yang ada di JavaScript.

- String
Tipe data String digunakan untuk mewakili data tekstual atau karakter. String dapat dibuat menggunakan petik tunggal atau ganda dan diakhiri dengan petik yang sama, kita bisa memasukkan karakter diantara petik.
    ```JS
    const namaDepan = 'Dio'; // Petik tunggal
    const namaBelakang = "Putra"; // Petik ganda
    ```

- Number
Tipe data Number atau angka di JavaScript mewakili angka positif dan negatif entah itu bulat (integer) maupun desimal (floating-point).
    ```JS
    const bulatPositif = 10;
    const bulatNegatif = -10;
    ```
- Boolean
Tipe data Boolean adalah salah satu tipe data yang digunakan ketika mengekspresikan logika benar atau salah. Boolean hanya memiliki dua nilai, true dan false.
    ```JS
    const minum = true;
    const makan = false;
    ```
- undefined
Undefined adalah nilai yang diberikan ketika variabel dideklarasikan tanpa inisialisasi atau tidak diberi nilai. Ini hanya berlaku untuk variabel let dan var, karena kita tidak dapat mendeklarasikan variabel const tanpa nilai.
    ```JS
    let nama;
    
    console.log(nama); // undefined
    ```

- null
null dapat digunakan untuk mewakili ketidakhadiran yang disengaja dari nilai objek. Kita dapat menetapkan null ke variabel untuk menunjukkan bahwa saat ini variabel tersebut tidak memiliki nilai apa pun, tapi nanti akan memilikinya.
    ```JS
    let mahasiswa = null;
    console.log(mahasiswa); // null
    ```
- Symbol
Symbol adalah tipe data baru yang diperkenalkan pada JavaScript ES2015. Nilai yang memiliki tipe data Symbol disebut sebagai "nilai Symbol". Nilai Simbol dibuat dengan menjalankan fungsi Symbol yang secara dinamis menghasilkan nilai unik. Nilai sebenarnya bersifat anonim, tidak bisa dilihat.
    ```JS
    const a = Symbol();
    const b = Symbol();
    
    console.log(a === b); // false
    console.log(a); // Symbol()
    console.log(b); // Symbol()
    ```

### Non-Primitif
Tipe data non-primitif adalah tipe data yang didefinisikan sendiri oleh programmer dan biasanya berisi lebih dari satu nilai. Berikut merupakan tipe-tipe data non-primitif

- Object
Object adalah tipe data yang kompleks yang memungkinkan kita menyimpan kumpulan nilai dengan tipe data yang berbeda. Objek berisi properti yang didefinisikan sebagai pasangan kunci dan nilai (key dan value).
    ```JS
    const obj = {
      nama: 'dio',
      umur: 19,
    };
    
    console.log(obj); // {nama: "dio", umur: 19}
    ```
    
    Untuk mengakses nilai tertentu pada objek kita bisa menggunakan nama objek diikuti dengan titik dan kunci yang ingin diakses nilainya.

    ```JS
    const obj = {
      nama: 'dio',
      umur: 19,
    };
    
    console.log(obj.nama); // dio
    console.log(obj); // {nama: "dio", umur: 19}
    ```
    
    Untuk mengubah nilai kunci objek sama seperti mengakses nilai, namun diperlukan operator assigment = diikuti dengan nilai yang ingin dimasukkan.
    
    ```JS
    const obj = {
      nama: 'dio',
      umur: 19,
    };
    obj,nama = 'dynau'
    
    console.log(obj.nama); // dynau
    console.log(obj); // {nama: 'dynau', umur: 19}
    ```
    
    Kita juga bisa menambahkan kunci dan nilai baru menggunakan cara yang sama seperti mengubah nilai, namun tentunya kita perlu menggunakan nama kunci baru.
    
    ```JS
    const obj = {
      nama: 'dio',
      umur: 19,
    };
    obj,kuliah = 'Universitas Mulawarman'
    
    console.log(obj); // {nama: 'dynau', umur: 19, kuliah: 'Universitas Mulawarman'}
    ```
    
- Array
Array adalah jenis objek yang dapat digunakan untuk menyimpan beberapa nilai, tanpa properti seperti objek. Array memiliki indeks yang dimulai dari nol dengan kata lain elemen atau nilai pertama di dalam array memiliki indeks 0, elemen berikutnya memiliki indeks 1 dan seterusnya. kita bisa menggunakan indeks untuk memanipulasi nilainya. Nilai pada array literal harus diapit dengan kurung siku [], jika memiliki lebih dari satu nilai dipisahkan dengan koma. Kita bisa memasukkan tipe data apa pun ke dalam array, termasuk array dan objek.

    ```JS
    const arr ['dio , 19];
    
    console.log(arr); // ['dio', 19]
    ```
    Cara untuk mengakses elemen array:

    ```JS
    const arr ['dio', 19];
    
    console.log(arr[0]); // 'dio'
    ```

    Cara untuk mengubah elemen array:

    ```JS
    const arr ['dio', 19];
    arr[1] = 20;
    
    console.log(arr); // ['dio', 20]
    ```


## DOM Manipulation
DOM merupakan singkatan dari Document Object Model. Berfungsi untuk memanipulasi tampilan web agar menjadi lebih dinami dan interaktif. Ini adalah sebuah interface yang memungkinkan Anda sebagai developer untuk memanipulasi style, konten dari sebuah website.

### Fungsi DOM 
- Mengubah element HTML pada halaman website.
- Mengubah attribute HTML pada halaman website.
- Mengubah CSS style pada halaman website.
- Menambah dan/atau menghapus element maupun attribute HTML.
- Menambah HTML event (contoh: efek klik pada mouse, hover pada mouse, dan lain-lain) pada halaman website.
- Berinteraksi dengan semua HTML event di website.

### Mengakses Elemen HTML
Objek dokumen mewakili halaman situs web. Jika ingin mengakses elemen apa pun di halaman HTML, maka selalu mulai dengan mengakses objek dokumen. Berikut merupakan cara untuk mengakses element HTML

- Dengan Nama Tag
Kita dapat mengakses elemen-elemen HTML berdasarkan tagnya
    ```JS
    let listItems = document.getElementsByTagName(‘li’);
    ```
- Dengan Nama ID
Kita dapat mengakses elemen-elemen HTML berdasarkan ID-nya
    ```JS
    let title = document.getElementById(‘header-title’);
    ```
- Dengan Nama Class
Kita dapat mengakses elemen-elemen HTML berdasarkan class-nya
    ```JS
    let items = document.getElementsByClassName(‘list-items’);
    ```
- Dengan Query Selector
Sebuah method querySelector() memungkinkan kita untuk bisa mengembalikan elemen yang pertama. Pengembalian tersebut sudah sesuai dengan CSS selector yang telah di tentukan sebelumnya.
```JS
let header = document.querySelector(‘.header’); // seperti CSS
```

### Mengubah Konten HTML
- Element.textContent
dapat kita gunakan untuk mengubah teks di dalam sebuah element
    ```JS
    <h1 id = 'header'></h1>
    
    dan
    
    document.querySelector(‘.header’).textContent = 'Ini Header';
    ```

    Output :
    
    ![textContent](https://github.com/DynaudioP/tugas-writing-and-presentation-week/blob/main/Week%202/gambar/textcontent.JPG)

- Inner HTML
dapat kita gunakan untuk mengubah konten HTML di dalam sebuah element.

    ```JS
    <ul id="list"></ul>
    
    Kita bisa menambahkan item kedalamnya dengan
    
    document.getElementById("list") = "<li>Ayam</li><li>Kucing</li>"
    ```
    
    Output :

    ![innerhtml](https://github.com/DynaudioP/tugas-writing-and-presentation-week/blob/main/Week%202/gambar/innerhtml.JPG)

### Membuat Elemen HTML
Kita dapat menghadirkan elemen-elemen dengan memanfaatkan method createElement. Method ini akan mengambil tagname sebagai parameternya. Lalu menyimpannya dalam variabel. Ketika sudah tersipan, Anda cukup membuat beberapa konten.
```JS
let div = document.createElement(‘div’);
```

### Menghapus Elemen HTML
Kita bisa mendapatkan elemen dan menghapusnya. Method yang Anda gunakan adalah removeChild
```JS
let elem = document.querySelector(‘#header’); 
elem.parentNode.removeChild(elem);
```

### Mengubah Style Elemen
Kita dapat mengubah style elemen menggunakan JavaScript
```JS
document.getElementsByTag(“h2”).style.borderBottom = “solid 3px #000”;
```
### Menangkap Interaksi User
#### addEventListener
addEventListener adalah method yang sangat penting yang digunakan untuk membuat event untuk keperluan manipulasi didalam DOM javascript. Dengan cara addEvenListener event
- Bisa dihilangkan
- Bisa ada beberapa event listener yang sama untuk 1 element
- Memiliki argument tambahan { options }

#### EventListener Click
Dapat digunakan untuk menampilkan Pop-Box

```JS
const button = document.getElementById(“alert-button”)

// baru tambahkan event listener
button.addEventListener(“click”, function() {
	alert(input.value)
})

// atau
button.onclick = function() { alert(input.value) }
```

### EventListener Blur
“Blur”, lawan dari “focus”, adalah event di mana sebuah element kehilangan fokus dari user (misal user klik mouse di luar element tersebut atau user klik tab untuk berpindah element).

```JS
const input = document.getElementById(“username”)

// tambahkan event listener
input.addEventListener(“blur”, () => {
	if(input.value.length < 6) alert(“Panjang username minimal 6”)
})
```

### EventListener Form Submission
Ada 2 cara:
- Pasang event listener di kedua input dan tombol submit, lalu saat tombol diklik, baca value dari kedua input tersebut. 
- Pasang event listener di form, lalu gunakan FormData untuk mengambil data dari masing-masing input

```JS
const form = document.getElementById(“form”)

form.addEventListener(“submit”, function(event) {
	// cegah page refresh
	event.preventDefault()

	const formData = new FormData(form)
	const values = Object.fromEntries(formData) // { email: ... }
})
```
