# Rangkuman Writing & Presentation Week 6
## React JS Dasar
### Introduction to React JS
ReactJS atau React adalah library JavaScript populer buatan Facebook yang digunakan dalam proses pengembangan aplikasi mobile dan web. React berisi kumpulan snippet kode JavaScript yang bisa digunakan berulang kali untuk mendesain antarmuka pengguna.

### Alasan Menggunakan React JS
- React JS is FAST. 
React JS membuat aplikasi front-end menjadi lebih cepat walaupun harus menghandle berbagai data.
- React JS is MODULAR. 
Kita dapat menerapkan konsep Modular javascript pada React JS membagi 1 tampilan pada website menjadi komponen-komponen kecil.
- React JS is SCALABLE. 
React JS dapat digunakan pada aplikasi berskala kecil hingga besar dan kompleks.
- React JS is POPULAR. 
Komunitas React JS di seluruh dunia sangat besar. Kebanyakan perusahaan teknologi sudah menggunakan React JS.

### Instalasi React JS
1. Install Node JS
kita dapat download dan install Node JS melalui link https://nodejs.org/en/download/
2. Menggunakan Library create-react-app 
kita dapat menggunakan library https://create-react-app.dev/
    - npx
    ```
    npx create-react-app my-app
    ```
    - npm
    ```
    npm init react-app my-app
    ```
    - Yarn
    ```
    yarn create react-app my-app
    ```
    
    Jika berhasil terinstall, maka kita dapat membuat projek/folder baru dan memulainya dengan start.
    ```
    npM create-react-app my-app
    cd my-app
    npm start
    ```
    
### Membuat Elemen UI menggunakan React JS
Pertama kita membuat file js baru pada direktori src
```JS
import React from 'react';

function HelloWorld() {
    return (
        <h1>Hello World</h1>
    )
};

export default HelloWorld
```

Kemudian kita mengedit file App.js
```JS
import React from 'react';
import HelloWorld from ',/HelloWorld'

function App() {
    return (
        <div>
            <HelloWorld />
        </div>
    );
};

export default App;
```

### Component
Component adalah bagian terpenting dari aplikasi React, karena aplikasi react sendiri terusun dari komponen-komponen. Component adalah salah satu core dari React JS. Component membagi UI dalam satuan-satuan kecil. Artinya dalam 1 page ada beberapa component yang bisa kita buat.

Component dibuat jika component tersebut bersifat reusable code. Pada sebuah project, kita membuat component jika component tersebut akan dibutuhkan di page lain.

### Component Class & Component Function
Ada 2 cara untuk membuat component yaitu
- Gunakan Function
- Gunakan Class

Class Component dapat menggunakan props dan state, sedangkan Functional Component hanya bisa menggunakan props itu sebabnya function component disebut stateless component. 

### Membuat Component
- Function Component
Berikut merupakan contoh penulisan Function Component
    ```JS
    import React from "react";
    
    const App = () => {
      return (
        <div>
          <h1>Hello Dio</h1>
        </div>
      );
    }
    
    export default App;
    ```
- Class Component
Berikut merupakan contoh penulisan Class Component
    ```JS
    import React, { Component } from 'react';
    
    class App extends Component {
      render() {
        return (
          <div>
            <h1>Hello Devsaurus</h1>
          </div>
        );
      }
    }
    
    export default App;
    ```

### JSX
JSX adalah ekstensi syntax JavaScript yang digunakan dalam pembuatan elemen React. Kita dapat menggunakannya untuk menyematkan (embed) kode HTML pada objek JavaScript.

Dengan menggunakan JSX, kita dapat menggunakan elemen-elemen HTML di dalam JavaScript. Disetiap JSX kita hanya bisa memasukkan 1 parent elemen.

```JS
let nama = 'dio';

function App() {
    return (
        <div>
            <h1>{nama}</h1>
        </div
    );
}

export default App;
```

### Virtual DOM
Document Object Model (DOM) berfungsi untuk menyajikan halaman web dalam tampilan struktur data. ReactJS menyimpan struktur data DOM Virtual ini dalam memorinya, sehingga kalau ada perubahan pada bagian tertentu dalam struktur data tersebut, Anda tidak perlu merender ulang semuanya.

Setiap kali ada perubahan data, ReactJS akan membuat satu struktur data DOM Virtual baru dan membandingkannya dengan yang sebelumnya, lalu mencari cara tercepat untuk menerapkan perubahan tersebut pada DOM yang asli.

Jadi, perubahan UI hanya akan memengaruhi bagian tertentu dalam struktur data DOM yang asli, sehingga proses render perubahan pun bisa lebih cepat dan lebih hemat resource. Hal ini akan sangat membantu bagi proyek berskala besar yang perlu banyak interaksi user.

### State & Props
Props merupakan argumen yang di-passing dari satu komponen ke komponen lain. Props digunakan untuk melakukan komunikasi data antara komponen parent dan child. Sedangkan, State merupakan tipe data pada komponen React yang bersifat privat. Artinya, data dengan tipe state hanya dapat digunakan di dalam komponen itu sendiri. Berikut merupakan contoh state & props.

- Props
    ```JS
    import React from 'react';
     
    function Parent() {
      return <Child name="Dio" />
    }
     
    function Child(props){
      return (
        <div>
          <h1>Hello {props.name}</h1>
        </div>
      )
    }
     
    export default Parent;
    ```
    
- State
    ```JS
    import React from 'react'
     
    class App extends React.Component {
      constructor(props) {
        super(props);
        this.state = {name: "Dio"};
      }
      render() {
        return (
          <div>
            <h1>Hello {this.state.name}</h1>
          </div>
        );
      }
    }
     
    export default App
    ```
    
### Stateful & Stateless Component
Stateful components adalah komponen yang mempunyai state dan bisa mengirim state tersebut ke component. Sedangkan Stateless adalah komponen yang tidak memili state dan hanya menggunakan props. Stateful components juga dikenal dengan sebutan Container dan Smart components. Stateless juga dikenal dengan sebutan Presentation dan Dumb Components.

### Lifecycle Method
Lifecycle dari komponen React ada 3 fase yaitu :
- Mounting
- Updating
- Unmounting

![Lifecycle](https://miro.medium.com/max/828/1*IrFfI3bAU6Gz8Pfv1CHulg.png)

### Mounting
Fase Mounting adalah fase ketika components di buat atau pertama kali di render ke DOM

Ada tiga methods yang akan di eksekusi yaitu 
- componentWillMount 
- render
- componentDidMount.

### Updating
Fase updating adalah fase ketika sebuah component akan di render ulang, biasanya ini terjadi ketika ada perubahan pada state atau props yang mengakibatkan perubahan DOM.

Ada 5 methods yang akan di eksekusi yaitu:
- componentWillReceiveProps 
- shouldComponentUpdate
- componentWillUpdate 
- render 
- componentDidUpdate

### Unmounting
Fase unmounting adalah fase ketika component di hapus dari DOM.

Pada fase ini hanya ada satu method yang akan di eksekusi yaitu 
- componentWillUnmount

yang di jalankan sebelum sebuah component di hapus dari DOM

### Styling pada React JS
Kita bisa melakukan styling pada React JS dengan cara seperti biasanya kita menggunakan CSS. Kita bisa melakukan styling dengan cara 
- Inline Style
    ```JS
    function App() {
        return (
            <div>
                <h1 style={{color: "red";}}>Dio</h1>
            </div
        );
    }
    ```

- StyleSheet CSS
    ```JS
    import NameStyle from './component/NameStyle/NameStyle';
    import './component/NameStyle/NameStyle.css';
    
    function App() {
        return (
            <div>
                <h1>Dio</h1>
            </div
        );
    }
    ```

## React JS Lanjutan
### React Hooks
Hooks merupakan fitur baru di React 16.8. Fitur ini memungkinkan Anda menggunakan state dan fitur React lainnya tanpa menuliskan sebuah kelas.

Sebelumnya state dan lifecycle hanya bisa digunakan di class component, namun dengan hooks kita bisa menggunakannya juga di functional component.

Berikut merupakan Hooks yang sering digunakan :
- useState
- useEffect

### useState
useState di panggil dalam function component untuk menambahkan suatu state lokal.
```JS
const [count, setCount] = useState(0);
```
Berikut merupakan contoh penggunaan useState
```JS
import React, { useState } from 'react';

function Contoh() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Anda menekan sebanyak {count} kali</p>
      <button onClick={() => setCount(count + 1)}>
        Klik Disini
      </button>
    </div>
  );
}
```

### useEffect
Hooks yang digunakan untuk menggunakan lifecycle pada functional component dengan mudah. Lifecycle yang ada di dalam hooks hanya menggunakan useEffect yang menyatukan componentDidMount, componentDidUpdate, dan componentWillUnmount.

Berikut merupakan contoh penggunaan useEffect
```JS
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Anda klik sebanyak ${count} kali`;
  });

  return (
    <div>
      <p>Anda klik sebanyak {count} kali</p>
      <button onClick={() => setCount(count + 1)}>
        Klik Disini
      </button>
    </div>
  );
}
```

### Form
Elemen form HTML bekerja sedikit berbeda dari elemen DOM lainnya di React, karena elemen form secara natural menyimpan beberapa state internal. 

Penanganan pada formulir adalah tentang bagaimana Anda menangani data saat itu untuk mengubah atau mengirimkan nilai. Dalam HTML, data formulir biasanya ditangani oleh DOM. Di React, data formulir biasanya ditangani oleh komponen. Ketika data ditangani oleh komponen, semua data disimpan dalam status komponen. Anda dapat mengontrol perubahan dengan menambahkan penangan kejadian di atribut onChange.

```JS
import React from 'react';
import ReactDOM from 'react-dom';

class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { username: '' };
  }
  myChangeHandler = (event) => {
    this.setState({username: event.target.value});
  }
  render() {
    return (
      <form>
      <h1>Hello {this.state.username}</h1>
      <p>Enter your name:</p>
      <input
        type='text'
        onChange={this.myChangeHandler}
      />
      </form>
    );
  }
}

ReactDOM.render(<MyForm />, document.getElementById('root'));
```

Anda dapat mengontrol tindakan kirim dengan menambahkan pengendali kejadian di atribut onSubmit.

```JS
import React from 'react';
import ReactDOM from 'react-dom';

class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = { username: '' };
  }
  mySubmitHandler = (event) => {
    event.preventDefault();
    alert("You are submitting " + this.state.username);
  }
  myChangeHandler = (event) => {
    this.setState({username: event.target.value});
  }
  render() {
    return (
      <form onSubmit={this.mySubmitHandler}>
      <h1>Hello {this.state.username}</h1>
      <p>Enter your name, and submit:</p>
      <input
        type='text'
        onChange={this.myChangeHandler}
      />
      <input
        type='submit'
      />
      </form>
    );
  }
}

ReactDOM.render(<MyForm />, document.getElementById('root'));
```

Anda dapat memvalidasi masukan formulir saat pengguna mengetik atau Anda dapat menunggu hingga formulir dikirimkan.

```JS
   super(props);
    this.state = {
      username: '',
      age: null,
    };
  }
  myChangeHandler = (event) => {
    let nam = event.target.name;
    let val = event.target.value;
    if (nam === "age") {
      if (!Number(val)) {
        alert("Your age must be a number");
      }
    }
    this.setState({[nam]: val});
  }
  render() {
    return (
      <form>
      <h1>Hello {this.state.username} {this.state.age}</h1>
      <p>Enter your name:</p>
      <input
        type='text'
        name='username'
        onChange={this.myChangeHandler}
      />
      <p>Enter your age:</p>
      <input
        type='text'
        name='age'
        onChange={this.myChangeHandler}
      />
      </form>
    );
  }
}

ReactDOM.render(<MyForm />, document.getElementById('root'));
```






