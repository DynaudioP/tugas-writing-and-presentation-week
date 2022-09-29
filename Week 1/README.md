# Rangkuman Writing & Presentation Week 1
## Unix Command Line
## Command Line Interface (CLI)
CLI atau Command Line Interface adalah sistem antarmuka yang memungkinkan pengguna untuk memasukkan perintah ke terminal dalam menjalankan tugas.

### Kelebihan CLI
- CLI umumnya memiliki kemampuan lebih yang tak bisa dilakukan GUI (terutama dalam urusan server, web, hacking, dsb).
- CLI ringan digunakan sehingga tidak mengharuskan komputer untuk memiliki spesifikasi tinggi bila ingin menginstal CLI.
- CLI memiliki tampilan yang membingungkan sehingga pengguna pemula sulit untuk mengacaknya atau memainkannya.

### Contoh CLI
- bash
- zsh
- fish
- dash

### Shell
Shell adalah program yang menjembatani user dengan sistem operasi . Dengan adanya shell kita bisa menjalankan suatu perintah pada sistem operasi. Jadi bisa dibilang shell merupakan penerjemah bagi user untuk berkomunikasi dengan komputer

### Terminal
Mengacu pada sebuah wrapper dari suatu program yang menjalankan shell, sehingga sebuah terminal bisa dikatakan sebagai lingkungan tempat menjalankan input dan output.

### File System Structure
Merupakan struktur dari bagaimana cara data disimpan di dalam sistem. Secara singkat, file system adalah pengaturan penyimpanan data yang sangat mempermudah pekerjaanmu sehari-hari. Berikut contoh dari file system structure.

![tree](https://e7.pngegg.com/pngimages/483/529/png-clipart-file-system-directory-structure-computer-file-hierarchy-linux-file-system-directory-structure.png)

### Command

- pwd - Untuk melihat current working directory
- cd - Untuk berpindah directory
- ls - Untuk melihat sebuah file di sebuah directory
- mkdir - Untuk membuat direktori baru
- touch - Untuk membuat sebuah file
- cp - Untuk menyalin sebuah file
- mv - Untuk memindahkan dan mengganti nama file
- rm - Untuk menghapus sebuah file
- rmdir - Untuk menghapus sebuah directory

Command diatas merupakan perintah-perintah dasar yang wajib diketahui dan merupakan sampel kecil dari perintah-perintah yang lebih banyak lagi.

## Git & GitHub
### Pengertian Git & GitHub
- Git
 Git merupakan version control system bersifat open source yang digunakan untuk melacak konten dan menyimpan kode beserta seluruh perubahannya. Dengan adanya VCS seorang programmer dapat terselamatkan jika dikemudian hari terhapus file local nya.

- GitHub
GitHub merupakan layanan cloud penyedia Git atau penyedia layanan hosting berupa web untuk repositori Git yang memungkinkan untuk berkolaborasi dengan team atau orang lain dalam mengelola dokumen atau suatu project.

### Perbedaan Git & GitHub
Antara GIT dan GitHub sebenarnya merupakan dua platform yang didirikan oleh perusahaan dan dengan tujuan yang sama, namun fitur yang dimilikinya berbeda. Kedua platform ini sangat membantu pekerjaan programmer dalam bekerja dalam tim untuk menyusun kode script. Seluruh pekerjaan juga dapat dipantau dan dievaluasi dengan mudah karena penggunaan control system. Berikut merupakan beberapa perbedaan antara Git & GitHub

| Git | GitHub |
| --- | ----------- |
| Diakses secara offline | Diakses secara online |
| Tidak memakai fitur user management | Menggunakan fitur user management |
| Install software di penyimpanan lokal | Di-host melalui layanan cloud |
| Fokus pada version control dan code sharing | Fokus pada source code hosting yang terpusat |

### Alur Kerja Git
- Working Directory
Tahap dimana kita bisa membuat, menghapus, dan mengubah file. Di tahap ini masih belum bisa dilakukan commit karena belum berada di tahapn Staging
- Staging
Tahap dimana perubahan yang dilakukan di Working Directory siap untuk dilakukan commit
- Commit
Tahap dimana perubahan yang telah berada di Staging siap untuk di commit atau di simpan permanen di local repository

![tree](https://miro.medium.com/max/640/1*w1IrUWtQhZE_7mtbf7xbyQ.png)

### Mengapa Wajib Menggunakan Git & GitHub
Git & GitHub digunakan untuk merekam dokumentasi setiap perubahan pada kode yang dibuat, diupdate, maupun dihapus, semacam track record yang tersimpan di komputer lokal, fungsinya adalah agar kita dapat melihat perkembangan yang telah terjadi pada proyek yang dibuat. Dan adanya GitHub sangat memudahkan programmer yang bekerja secara tim untuk menyusun script kode yang masing-masing telah dibuat dan seluruh kerjanya pun dapat dipantau karena penggunaan Version Control System. Karena fungsinya yang cukup krusial dan sangat membantu dalam pengembangan pemrograman, menguasai penggunaan Git & GitHub menjadi hal yang wajib bagi seorang programmer baik yang baru belajar maupun profesional.


### Command Git
- Git Config
    Digunakan untuk menetapkan nama pengguna yang kemudian jika melakukan proses commit Git akan menggunakan informasi data tersebut

    ```
    $ git config --global user.name "John Doe"
    $ git config --global user.email johndoe@example.com
    ```
- Git init
    Digunakan untuk membuat repositori baru 
    ```
    $ git init <nama proyek>
    ```
- Git add
    Digunakan untuk memasukkan file yang berada di tahap working directory ke tahap staging yang siap untuk di commit
    ```
    $ git add <file_name>
    ```
- Git commit
    Digunakan untuk menyimpan perubahan file yang berapa di tahap staging ke tahap commit yang menyimpan perubahan secara permanen
    ```
    $ git commit -m <Pesan catatan commit>
    ```
- Git remote
    Digunakan untuk menambahkan remote yang menghubungkan local repository ke remote repository
    ```
    $ git remote add origin <server>
    ```
- Git push
    Digunakan untuk mengirim perubahan local repository ke remote repository
    ```
    $ git push -u origin master
    ```
- Git clone 
    digunakan untuk membuat salinan repository dari lokal maupun remote
    ```
    $ git clone <repo> <directory>
    ```

## HTML
HTML adalah singkatan dari HyperText Markup Language. Pengertian HTML adalah bahasa pemrograman standar yang digunakan untuk membuat sebuah halaman web, yang kemudian dapat diakses untuk menampilkan berbagai informasi di dalam sebuah penjelajah web Internet.
### Fungsi HTML
HTML Berfungsi sebagai kerangka dari sebuah website dimana HTML mempunyai tugas untuk membuat struktur halaman website

## Tools yang dibutuhkan untuk membuat HTML
Tools yang dibutuhkan untuk membuat html adalah Web Browser serta Code Editor. Code Editor yang dibutuhkan yang akan kita gunakan adalah Visual Studio Code. Alasan digunakannya Visual Studio Code ialah banyaknya ekstensi yang membantu kita dalam Web Development seperti Rename tag, Closing tag, Live Server dan masih banyak lagi. Adanya built-in Git dan Debug Console juga memudahkan pengguna untuk mengakses banyak hal.

## Kerangka HTML
HTML memiliki kerangka seperti dibawah ini.
```HTML
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
### Tag HTML
- html
Berfungsi untuk tag yang menandakan proses mulai menuliskan kode program pada dokumen HTML.
```HTML
<html>
    <head>
     
    </head>
    <body>
        
    </body>
</html>
```
- <head>
Tag ini digunakan untuk menambahkan metadata ke dalam dokumen html yang berisi judul, deskripsi, library dan lain sebagainya.
```HTML
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
```
- body
Tag body digunakan sebagai tempat untuk menuliskan setiap elemen atau lebih tepatnya disebut juga dengan konten pada HTML itu sendiri.
```HTML
<body>
    <p>Halo</p>
</body>
```
- tag h1 dan h6
Tag yang digunakan untuk membuat heading pada di website. hierarki ukuran font tertinggi untuk <h> berada pada <h1>.
```HTML
<h1>Hai teman</h1>
```

- tag p
Tag yang digunakan untuk membuat sebuah paragraf/tulisan
```HTML
<p>Hai teman</p>
```
- tag b dan i
Tag yang digunakan untuk membuat tulisan tebal(<b>) dan miring(<i>)
```HTML
<p><b>Hai teman</b></p>
<p><i>Hai teman</i></p>
```

- tag a
Tag yang digunakan untuk menyertakan link di tulisan yang dapat di-klik
```HTML
<p><a href="">Hai Teman</a></p>
```

- tag img
Tag yang digunakan untuk menampilkan gambar
```HTML
<img src="https://e7.pngegg.com/pngimages/471/1009/png-clipart-lion-graphy-lion-mammal-animals-thumbnail.png" alt="singa">
```

- tag ol dan ul
Tag yang digunakan untuk membuat list.
```HTML
<ol>
    <li>Joni</li>
    <li>Boni</li>
    <li>Toni</li>
</ol>
<ul>
    <li>Joni</li>
    <li>Boni</li>
    <li>Toni</li>
</ul>
```

- Tag div
Tag yang digunakan untuk membungkus tag-tag lain dan biasa digunakan untuk menetukan section seperti header,main,footer dll. 
```html
    <div>
        <h1>Hai teman</h1>
        <p>Hai teman</p>
    </div
```

### Semantic Tag
Semantic tag atau semantic markup adalah sebutan untuk tag HTML yang memiliki 'arti' atau 'makna. Sedangkan tag seperti <div> yang tidak memiliki 'arti apa-apa' sering kita gunakan untuk membuat struktur halaman website. Penggunaan Semantic HTML tentunya akan mempermudah proses pengembangan web karena tag yang digunakan mudah dipahami oleh bahasa manusia.

- <header>
Tag yang digunakan untuk menandakan bagian header dari website
```html
<body>
    <header>
    </header>
</body>
```
- <nav>
Tag yang digunakan untuk menandakan bagian navigasi dari website
```html
<body>
    <navr>
    </nav>
</body>
```
- <section>
Tag yang digunakan untuk menandakan bagian konten dari website
```html
<body>
    <section>
    </section>
</body>
```
- <footer>
Tag yang digunakan untuk menandakan bagian footer dari website
```html
<body>
    <footer>
    </footer>
</body>
```

### Deploy HTML
Deploy adalah sebuah proses dimana kita menyebarkan aplikasi yang sudah kita buat agar bisa digunakan oleh orang-orang. Untuk deploy file HTML perlu sebuah server untuk di taruh. Netlify adalah salah satu platform penyedia layanan build tools sekaligus Continous Deployment. Netlify memungkinkan kita untuk mempublish website statis secara gratis. Netlify juga sudah terintegrasi dengan Git Host popular seperti Github, Gitlab dan Bitbucket.

## CSS
CSS atau Cascading Style Sheets adalah kumpulan perintah yang digunakan untuk menjelaskan tampilan sebuah halaman situs web dalam mark-up language.

CSS berperan sebagai 'baju' untuk sebuah website, yang memberi warna dan layout pada website.
### Menyisipkan CSS di dalam file HTML
- Inline CSS
Inline CSS adalah cara menambahkan CSS dengan menggunakan atribut style pada tag pembuka elemen HTML. Cara ini biasanya digunakan untuk memberi gaya atau style unik
pada suatu elemen.
```HTML
<!DOCTYPE html>
<html>
<head>
	<title>Mengenal CSS</title>
</head>
<body>
	<h1 style="padding: 5px; background-color: red;">Tutorial Penerapan CSS</h1>
	<p style="padding: 10px; background-color: green;">
		Selamat datang di website kami!
	</p>
</body>
</html>
```
- Internal CSS
Internal CSS merupakan cara menambahkan CSS dengan menggunakan tag <style> di dalam tag <head>. Cara ini diperuntukkan untuk mengatur style untuk satu halaman website.
```HTML
<!DOCTYPE html>
<html>
<head>
	<title>Mengenal CSS</title>
	<style type="text/css">
		h1{
			padding: 5px; 
			background-color: red;
		}
		p{
			padding: 10px; 
			background-color: green;
		}
	</style>
</head>
<body>
	<h1>Tutorial Penerapan CSS</h1>
	<p>Selamat datang di website kami!</p>
</body>
</html>
```

- External CSS
External CSS adalah cara menambahkan CSS dengan menggunakan tag <link> yang didefinisikan pada setiap dokumen HTML. Cara ini merupakan cara yang paling umum digunakan oleh para pengembang, karena dengan cara ini memungkinkan kita untuk membuat hanya satu style CSS yang kemudian dapat diterapkan ke semua halaman website.
```HTML
<html>
<head>
    <link rel="stylesheet" type="text/css" href="style.css">
	<title>Mengenal CSS</title>
</head>
<body>
	<h1>Tutorial Penerapan CSS</h1>
	<p>Selamat datang di website kami!</p>
</body>
</html>
```
### Syntax CSS

CSS memiliki syntax yang sederhana dan menggunakan sejumlah kata kunci berbahasa Inggris untuk menentukan nama-nama berbagai properti. CSS syntax terdiri dari selector, property, dan value.
```css
selector {
    property:
}
```
- Selector
Digunakan untuk mencari bagian web yang ingin dimanipulasi atau yang ingin di-style
- Property
adalah jenis style, atau elemen apa yang akan diubah dari sebuah tag HTML.
- Value
 adalah nilai dari property. 

### FlexBox CSS
Flexible Box biasa disebut flexbox merupakan mode layout yang ada di CSS3 dan digunakan untuk mengatur elemen di suatu halaman web. Flexbox ini akan mengatur ukuran dari elemen anaknya secara otomatis, dan mampu beradaptasi dengan ukuran container-nya.

Tujuan dari flexbox yaitu memberikan container kemampuan untuk mengatur panjang, lebar, dan posisi item-item yang berada di dalamnya agar memaksimalkan ruang yang ada.

```css
header {
    display: flex;
    justify-content: space-between;
}
```
## Algoritma & Struktur Data
## Algoritma
Algoritma adalah urutan langkah untuk menyelesaikan masalah secara sistematis dan logis. Algoritma menawarkan suatu metode dalam menyelesaikan sebuah permasalahan. Algoritma diartikan sebagai urutan langkah dalam menyelesaikan masalah secara sistematis dan logis.
## Kualitas Algoritma
- Input dan output harus didefinisikan terlebih dahulu dengan tepat
- Setiap step harus benar-benar clear dan tidak ambigu
- Algoritma seharusnya tidak mengandung suatu code pada bahasa pemograman tertentu. 
- Algoritma harus dibuat agar dapat digunakan dalam bahasa pemograman apapun.

## Manfaat Algoritma
- Membantu menyederhanakan suatu program yang rumit dan juga besar.
- Mempermudah membuat program yang dapat menyelesaikan masalah tertentu.
- Bisa digunakan berulang kali dalam menyelesaikan suatu permasalahan.

## Perbedaan Algoritma dengan Struktur Data
Algoritma memberikan langkah-langkah yang dilakukan untuk menyelesaikan masalah, sedangkan struktur data mengatur data yang dibutuhkan dalam memori (mengorganisasi data).
## Contoh Algoritma
Berikut merupakan algoritma untuk membuat kopi instan
1. Ambil cangkir
2. Ambil kopi instan
3. Masukkan bubuk kopi ke dalam cangkir sesuai takaran
Siapkan air panas. Kalau belum tersedia, panaskan air.
4. Tuangkan air panas ke dalam cangkir
5. Aduk cangkir hingga kopi larut
6. Tambahkan gula atau krimer sesuai selera. Aduk.
7. Minum kopi

Algoritma dilakukan secara urut(sistematis) dan juga logis. Kita tiap hari tanpa disadari menerapkan algoritma dalam kehidupan sehari-hari

## Pseudocode
Pseudocode adalah ringkasan sebuah algoritma yang disajikan sebagai deskripsi tingkat tinggi informal yang dibuat untuk mudah dibaca oleh manusia bukan untuk mesin. Penulisannya pun tidak memiliki aturan atau struktur yang baku. Contohnya sebagai berikut
```
    a = 10
    b = 5
    IF a equals to b:
        print "a sama dengan b"
    else:
        print "a tidak sama dengan b"
```
## Flowchart
Flowchart atau bagan alur adalah diagram yang menampilkan langkah-langkah dan keputusan untuk melakukan sebuah proses Algoritma yang digambarkan dengan diagram dan arah panah. Contohnya sebagai berikut
![](https://bitlabs.id/blog/wp-content/uploads/2021/03/1-flowchart-bawa-payung.png)

## Contoh penerapan algoritma ke JavaScript
Dengan adanya algoritma yang sudah dibuat tentu saja akan memudahkan kita untuk menerapkannya ke bahasa pemrograman yang kita inginkan. Kita akan menggunakan pseudocode dan JavaScript untuk menerapkan algoritmanya.

```
nilai = 65
if nilai greater than 80 :
    print "Selamat kamu lulus."
else:
    print "Anda harus remidi."
```
Dengan adanya gambaran suatu algoritma yang kita terapkan. Akan lebih mudah untuk kita konversikan ke bahasa aslinya

```js
let nilai = 65;
if (nilai > 80){
    console.log("Selamat kamu lulus")
}else{
    console.log("Anda harus remidi")
}
```
## JavaScript
JavaScript adalah bahasa pemrograman web yang digunakan untuk memanipulasi element HTML dan membuat interaksi. Secara sederhana, JavaScript adalah sebuah bahasa pemrograman yang populer dan digunakan dalam membuat situs dengan konten website dinamis. JavaScript menambahkan aspek “interaktif” ke dalam HTML dan CSS.

### Fungsi JavaScript
JavaScript dapat membuat website menjadi lebih terlihat menarik, dinamis dan juga interaktif. Contohnya konten yang bergerak serta dapat memperbarui secara real time tanpa harus memuat ulang halaman website.

### Menyisipkan JavaScript di dalam HTML
- Internal JavaScript
Anda bisa langsung menambahkan JavaScript di HTML dengan menggunakan tag <script></script> yang mencakup semua kode JS yang Anda tulis
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Website Pertamaku</title>
    <script>
      console.log("Halo Semua!"); // output : Halo Semua!
    </script>
  </head>
  <body>
    <h2>JavaScript di dalam head</h2>
  </body>
</html>
```

- External JavaScript
Eksternal JavaScript yaitu membuat file JavaScript yang terpisah dengan file HTML. Cara menyambungkannya sama seperti internal JavaScript, yaitu menggunakan tag <script> di dalam element <body>, hanya saja, kita menambahkan attribute src di dalam <script> untuk menyambungkan dengan file eksternal JavaScript kita.
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>Website Pertamaku</title>
    <script src="script.js"></script>
  </head>
  <body>
    <h2>Hello, World!</h2>
  </body>
</html>
```

### Tipe Data
Pada penggunaanya, bahasa pemograman javascript ini menggunakan beberapa jenis tipe data. Berikut merupakan tipe data yang ada di dalam JavaScript.
- String
String merupakan tipe data untuk menuliskan sebuah karakter. String biasanya memakai tanda kutip baik tunggal maupun ganda pada karakternya. Tipe data ini biasa digunakan untuk membuat sebuah kalimat.
- Number/Integer
Merupakan tipe data yang digunakan untuk menunjukan angka bilangan bulat, baik positif maupun negatif.
- Boolean
Boolean merupakan tipe data yang hanya akan membuat dua nilai yaitu true atau false. Tipe data ini biasa digunakan untuk memberikan nilai pada pilihan seperti yes dan no, on dan off, benar dan salah, dan lainnya. Intinya tipe data ini hanya digunakan untuk nilai yang berupa 2 pilihan.
- Float
Float Merupakan tipe data yang digunakan saat akan menggunakan angka yang merupakan bilangan desimal seperti 3.14 atau 0.2.
- Object
Object Merupakan tipe data yang memungkinkan anda menggunakan tipe data lain di dalamnya. Tipe data ini akan berisi nilai dari tipe data.
- Array
Array merupakan tipe data yang digunakan untuk menyimpan banyak nilai pada satu variabel. 
- Null
Sebuah nilai yang berarti kosong atau menunjuk pada nilai yang tidak ada
- Undefined
Tipe data yang tidak memiliki nilai, berbeda dengan null, undefined ini tidak juga memiliki object. Perbedaanya dengan null ialah kalau null biasanya kita peroleh dalam kondisi normal dan sudah direncanakan , sedangkan undefined diperoleh dari sebuah kesalahan atau error.

### Variabel
Variabel adalah wadah untuk menyimpan nilai atau data. Ketika kita mendeklarasikan variabel, komputer akan menyisihkan memori untuk data yang kita simpan. Ada 3 cara untuk mendefinisikan sebuah variabel
- var
- let
- const

### Operator
Operator adalah simbol yang digunakan untuk melakukan operasi pada suatu nilai dan variabel.

Operator dalam pemrograman terbagi dalam 6 jenis:
1. Operator Aritmatika
2. Assignment Operator
3. String Operator
4. Operator Perbandingan
5. Operator Logika

### Operator Aritmatika
Operator aritmatika digunakan di operasi matematika yang melibatkan data dengan tipe number/integer.

| Operator | Deskripsi |
| --- | ----------- |
| + | Penjumlahan |
| - | Pengurangan |
| * | Perkalian |
| / | Pembagian |
| ** | Eksponen (pangkat) |
| % | Modulus (menghasilkan sisa hasil pembagian) |
| ++ | Increment (menambah 1) |
| - - | Decrement (mengurangi 1)Pembagian |

Contoh: 
```JS
let a = 10;
let b = 20;

var c = a + b;
console.log(c);
```

### Assignment Operator
Operator penugasan adalah operator yang digunakan untuk memberikan tugas kepada variabel. Biasanya digunakan untuk mengisi variabel.

| Nama Operator	| Simbol |
| --- | ----------- |
| Pengisian Nilai |	= |
| Pengisian dan Penambahan | += |
| Pengisian dan Pengurangan | -= |
| Pengisian dan Perkalian | *= |
| Pengisian dan Pemangkatan | **= |
| Pengisian dan Pembagian | /= |
| Pengisian dan Sisa bagi | %= |

Contoh :
```JS
let a = 10;

a *= 2
console.log(a);
```

### String Operator
String operator digunakan untuk menggabungkan dua atau lebih data string. Operasi ini biasa dikenal dengan sebutan string concatenation.

Ada 2 String operator yaitu:
- (+)
- (+=)

Contoh :

```JS
let a = "Hai";
let b = "Teman";

console.log(a + " " + b);
```

### Operator Perbandingan
Operator perbandingan adalah operator yang digunakan untuk membandingkan dua nilai.Operator perbandingan akan menghasilkan sebuah nilai boolean true dan false.

Operator perbandingan terdiri dari:

| Nama Operator	| Simbol |
| --- | ----------- |
| Lebih Besar | > |
| Lebih Kecil	| < |
| Sama Dengan	| == atau === |
| Tidak Sama dengan | != atau !== |
| Lebih Besar Sama dengan	| >= |
| Lebih Kecil Sama dengan	| <= |

Contoh :
```JS
let a = 10;

console.log(a == 10); // Output: True
```

## Operator Logika
Operator logika digunakan untuk melakukan operasi terhadap dua nilai boolean.

| Nama Operator	| Simbol |
| --- | ----------- |
| Logika AND | && |
| Logika OR	| || |
| Negasi/kebalikan	| ! |

Contoh : 
```JS
let a = 10;
let b = 5;

console.log(a == 6 && b == 5); // Output: False
```

### Conditional
Merupakan statement percabangan atau sebuah persyaratan yang menggambarkan suatu kondisi. kondisi akan dicek dan menjalankan perintah berdasarkan kondisi tersebut.
- IF Statement
    Percabangan if merupakan percabangan yang hanya memiliki satu blok pilihan saat kondisi bernilai benar

- ELSE IF Statement
Percabangan if/else merupakan percabangan yang memiliki dua blok pilihan.

- IF ELSE IF
Percabangan if/else/if merupakan percabangan yang memiliki lebih dari dua blok pilihan.

- Truthy dan Falsy
Truthy and falsy digunakan untuk mengecek apakah variabel telah terisi namun tidak mementingkan nilainya.

- Switch Case Conditional
Switch Case adalah sama dengan pencabangan atau IF ELSE, hanya saja caranya yang berbeda, bisa dikatakan lebih sederhana ketimbang penggunaan IF ELSE.

### Looping
Looping atau yang lebih dikenal dengan perulangan adalah suatu metode untuk meng-eksekusi suatu perintah yang sama terus-menerus hingga kondisi tertentu terpenuhi.

- For Loop
For loop mengulangi blok kode sampai kondisi tertentu terpenuhi. Ini biasanya digunakan untuk mengeksekusi blok kode untuk beberapa kali.

- For/In Loop
Loop for-in adalah tipe khusus dari loop yang berulang di atas properti objek, atau elemen array. 
- While Loop
While loop akan me-loop melalui blok kode sampai kondisi yang ditentukan bernilai true. Segera setelah fail, loop akan dihentikan. 

- Do While Loop
Do While loop adalah varian dari while loop, yang mengevaluasi kondisi pada akhir setiap loop yang berulang-ulang. Dengan do-while loop blok kode dieksekusi sekali, dan kemudian kondisinya dievaluasi, jika kondisinya true, maka pernyataan akan diulangi selama kondisi yang ditentukan dievaluasi adalah true.

