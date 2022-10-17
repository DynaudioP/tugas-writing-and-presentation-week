# Rangkuman Writing & Presentation Week 4
## JavaScript Intermediate
## Asynchronous
### Fetch
Merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karena Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah then jika promise mengembalikan resolve dan catch jika promise mengembalikan nilai reject.
 Array merupakan struktur data yang digunakan untuk menyimpan sekumpulan data dalam satu tempat. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.

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

## Git & Github Lanjutan
### Git Branch
Git development branch adalah cara yang sangat baik dalam mengerjakan aplikasi sambil melacak tiap versinya. Development branch adalah bifurkasi dari kondisi kode yang membuat alur baru bagi evolusinya. Branch ini dapat dipararelkan ke Git branch lain yang dibuat.

```JS
git branch [branch_baru]
```

Keuntungan menggunakan Git Branch ialah:
- Memungkinkan pengembangan fitur baru bagi aplikasi tanpa menganggu pengembangan di branch utama.
- Memungkinkan pembuatan branch-branch pengembangan berbeda yang dapat berpusat di satu repositori.

kita dapat pindah ke branch lain menggunakan checkout
```JS
git checkout <nama_branch>
```

Kita dapat menggabungkan branch menggunakan merge

```JS
git merge [branch]
```

### Git Remote
Remote digunakan untuk menyambungkan Repositori lokal ke Repositori Remote yang berada di GitHub

```JS
git remote add origin [repo-url]
```

### Git Push
Digunakan untuk mengirim perubahan local repository ke remote repository

```JS
git push github master
```

Keterangan:
- github adalah nama remote.
- master adalah nama cabang tujuan.

## Responsive Web Design
Responsive Web Design adalah bertujuan untuk membuat desain website kita dapat diakses dalam device apapun dengan ukuran layar apapun

### Chrome Web Devs Tools
Chrome DevTools adalah serangkaian alat developer web yang terintegrasi langsung ke browser Google Chrome. Alat ini memungkinkan Anda memeriksa aktivitas HTML (DOM) dan jaringan yang dirender di halaman Anda. 

Tools ini juga sangat berguna untuk mengelola website menjadi responsif karena kita dapet mengubah layout chrome kita menjadi tampilan website untuk device mobile menggunakan tools bawaan.

![request](https://miro.medium.com/max/828/0*8l-6z0z8yJ22QA5S.gif)

### Relative CSS Units
Relative unit berguna untuk mendesain website yang responsif karena ukurannya bisa berubah relatif terhadap parent atau ukuran layar.

Secara umum relative unit bisa dipakai sebagai satuan bawaan website responsif sehingga bisa membantu untuk meng-update style di ukuran layar yang berbeda.

- %: Ukurannya relatif terhadap parent element
- em: Ukurannya relatif terhadap font-size dari elemen saat ini
- rem: Ukurannya relatif terhadap font-size root elemen html. "rem" = "root em"
- ch: Ukurannya mengikuti jumlah karakter 
- vh: Ukurannya relatif terhadap tinggi viewport.
- vw: Ukurannya relatif terhadap lebar dari viewport
- vmin: Ukurannya relatif terhadap ukuran viewport yang lebih kecil . 
- vmax: Sama dengan vmin, dia akan melihat ukuran viewport yang lebih besar
- ex: Ukurannya relatif terhadap tinggi dari karakter "x" kecil font yang sedang aktif.

### Viewport
 Viewport adalah daerah pada layar yang menampilkan suatu konten. Dalam konteks ini, viewport adalah daerah yang menampilkan halaman web yang sedang kita akses. 
 
 Kita dapat menambahkan meta data di dalam elemen head di file HTML Untuk membuat halaman website menjadi responsif.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### Media Query
CSS media queries adalah CSS yang digunakan untuk mengatur CSS berdasarkan layar tampilan web, atau berdasarkan ukuran layar baik itu lebar, tingggi. 

Terkadang tampilan yang sudah kita desain dengan sedemikian rupa bisa kacau jika ditampilkan pada tampilan mobile. Dengan media query kita dapat menyelesaikan masalah ini dengan menentukan aturan ukuran dan tata letak elemen dengan kondisi-kondisi tertentu

Media query juga disebut dengan Breakpoint, karena cara kerja media query yakni dengan cara mengecheck ukuran viewport(layar/area dimana konten terlihat) apakah sesuai dengan kondisi yang kita deklarasikan, jika benar maka kode dalam kondisi tersebut yang akan dieksekusi. Dengan kata lain media query memberikan kemampuan menggunakan kode css yang sesuai dengan kondisi yang ditentukan.
```CSS
@media (max-width: 600px) {
  .button-group {
    display: flex;
    flex-direction: column;
  }
}
```

### Flexbox
Flexbox merupakan konsep pengaturan layout yang mengatur ukuran elemen Child dari suatu Container untuk beradaptasi dengan Parent/Container-nya. Flexbox umumnya digunakan pada sebuah elemen yang tidak pasti ukurannya atau berubah-ubah(dinamis). Hal ini sangat bermanfaat untuk membuat tampilan website responsif.

```CSS
.container {
    display: flex;
    justify-content: center;
}
```

### Flexbox Property
- display:
Property ini memiliki nilai yang menentukan apakah sebuah elemen akan berbentuk block atau inline.

```CSS
.container {
display: flex; /* atau inline-flex */
}
``` 
- flex-direction:
kita bisa menentukan arah Main Axis Flex Container dimana elemen flex-item kita dirender. Ada 4 nilai yang ada pada Property ini, yakni row, row-reverse, column, dan column-reverse.

```CSS
.container {
        display: flex;
        background-color: red;
        flex-direction: row | row-reverse | column | column-reverse.
}
```
- justify-content:
Property ini digunakan untuk mengatur alignment flex-item didalam Container di sepanjang main axis.

    ```CSS
    .container {
    display: flex;
    flex-direction: row
    justify-content: flex-start | flex-end | center | space-around | space-between
    }
    ```
- align-item:
Jika justify-content mengatur alignment dengan basis Main Axis, maka align-item sebaliknya, menggunakan Cross Axis.

    ```CSS
    .container {
    display: flex;
    align-items: stretch | flex-start | flex-end | center | baseline;
    }
    ```
- align-content:
Kita bisa menggunakan align-content jika kita ingin mengatur container dengan lebih dari satu baris flex-item (multiline).

    ```CSS
    .container {
    display: flex;
    flex-wrap: wrap;
    align-content: stretch | flex-start | flex-end | center | space-between | space-around;
    }
        ```
- flex-wrap:
Property ini membuat flex-item yang keluar dari batas flex-containernya dipindah ke baris baru.

    ```CSS
    .container {
    display: flex;
    flex-wrap: nowrap | wrap | wrap-reverse;
    }
    ```

Array juga dapat menyimpan berbagai macam tipe data.

```JS
const arr = ['Pokemon', 'Digimon', 2 , 5 , true];
console,log(arr);
```

## Bootstrap
Bootstrap merupakan sebuah framework yang berbasis HMTL, CSS dan JavaScript yang dapat digunakan untuk membuat website menjadi lebih mudah dibuat dan juga memiliki tampilan yang sudah responsif. Fitur-fitur yang tersedia dalam bootstrap sangat membantu kita dalam membuat website, dan yang paling terlihat sangat menggunakan bootstrap adalah tampilannya.

### Penerapan Bootstrap
Untuk menggunakan bootstrap kita perlu memanggil link bootstrap yang akan kita gunakan.
```HTML
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script>
```

### Layout dengan Sistem Grid.
Didalam bootstrap terdapat 12 grid untuk keseluruhan halaman. Kita dapat membuat 12 kolom untuk mengisi keseluruhan halaman. Namun bila kita hanya ingin membuat beberapa kolom saja, tentu saja itu bisa dilakukan dengan kolom yang lebih luas pada halaman web tersebut. Berikut merupakan class grid yang dapat digunakan.

| Grid Class | Keterangan |
| --- | ----------- |
| col |	Untuk ukuran yang sangat kecil, kurang dari 576px |
| col-sm | Ukuran kecil, untuk 576px atau lebih |
| col-md | Ukuran medium, untuk 768px atau lebih |
| col-lg | Ukuran besar, untuk 992px atau lebih |
| col-xl | Ukuran sangat besar, untuk 1200px atau lebih |


### Content di Bootstrap
Kita bisa menggunakan konten bawan dari bootstrap

contoh:

- Typography
    ```CSS
    <h1>h1. Bootstrap heading</h1>
    <h2>h2. Bootstrap heading</h2>
    <h3>h3. Bootstrap heading</h3>
    <h4>h4. Bootstrap heading</h4>
    <h5>h5. Bootstrap heading</h5>
    <h6>h6. Bootstrap heading</h6>
    ```
    
    Output :
    
    ![request](https://www.tutlane.com/images/bootstrap/bootstrap_html_headings_example_result.PNG)
    
### Component di Bootstrap
Dengan adanya komponen yang disediakan Bootstrap, kita dapat menambahkan banyak fitur untuk website kita dengan mudah, cepat dan juga responsif.

Ada banyak komponen yang disediakan oleh Bootstrap , seperti:

- Alerts
- Breadcrumb
- Buttons
- Card
- Carousel
- Close button
- Collapse
- Dropdowns
- Modal
- Navbar
- Navs & tabs
- Pagination
- Placeholders

Saya akan memberikan contoh komponen untuk membuat sebuah navbar 

```html
<nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Pricing</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled">Disabled</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```

Kita mungkin bisa menambahkan CSS namun akan sangat lama untuk membuatnya. Disini bootstrap menyediakan komponen yang dapat kita gunakan agar proses pembuatannya lebih cepat serta sudah responsif.

<br>

![request](https://github.com/DynaudioP/tugas-writing-and-presentation-week/blob/main/Week%204/gambar/gambar%201.JPG)


Navbar yang telah dibuat menggunakan juga sudah responsif tanpa adanya sentuhan CSS.

<br>

![request](https://github.com/DynaudioP/tugas-writing-and-presentation-week/blob/main/Week%204/gambar/gambar%202.JPG)







