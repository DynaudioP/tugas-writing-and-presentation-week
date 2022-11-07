# Rangkuman Writing & Presentation Week 7
## React JS Lanjutan
### PropTypes
PropTypes merupakan library untuk menvalidasi sebuah props atau memeriksa tipe data yang akan masuk pada suatu komponen. Jika tidak sesuai, maka akan memunculkan pesan error.

### Instalasi PropTypes
anda bisa menggunakan npm untuk menginstall library Proptypes
```
npm install prop-types
```

### Contoh PropTypes

```JS
import React, { Component, PropTypes } from 'react';
import logo from './logo.svg';
import './App.css';
  
class App extends Component {
  render() {
    return (
      <div className="App">
          <Header textHeader="Welcome to React" />
          <Content textContent="kali ini telah dipecah menjadi beberapa components" />
      </div>
    );
  }
}
  
class Header extends Component {
    render() {
        return (
            <div className="App-header">
              <img src={logo} className="App-logo" alt="logo" />
              <h2>{this.props.textHeader}</h2>
            </div>
        );
    }
}
  
Header.propTypes = {
    textHeader: PropTypes.string.isRequired
}
  
class Content extends Component {
    render() {
        return (
            <p className="App-intro">
              {this.props.textContent}
            </p>
        );
    }
}
Content.propTypes = {
    textContent: PropTypes.string.isRequired
}
  
export default App;
```

## React Router
React Router merupakan library yang dibangun di atas React dan digunakan untuk membuat perutean di aplikasi React menggunakan Paket React Router. Ini menyediakan URL sinkron di browser dengan data yang akan ditampilkan di halaman web. Ini memelihara struktur standar dan perilaku aplikasi dan terutama digunakan untuk mengembangkan aplikasi web satu halaman.

Jadi pada React, Router membantu kita untuk mengarahkan page satu ke page yg lainnya berdasarkan path url yg ditentukan.

### Instalasi React Router
Kita install menggunakan npm
```
npm install react-router-dom@6
```

Kemudian kita menambahkan import BrowserRouter pada bagian index js 
```JS
import { BrowserRouter } from "react-router-dom";
```



### Komponen Router
Berikut salah satu komponen pada React Router
- BrowserRouter : Ini digunakan untuk menangani URL dinamis.
    ```JS
    import * as React from "react";
    import * as ReactDOM from "react-dom";
    import { BrowserRouter } from "react-router-dom";
    
    ReactDOM.render(
      <BrowserRouter>
        {/* The rest of your app goes here */}
      </BrowserRouter>,
      root
    );
    ```
- HashRouter: Ini digunakan untuk menangani permintaan statis.
    ```JS
    import * as React from "react";
    import * as ReactDOM from "react-dom";
    import { HashRouter } from "react-router-dom";
    
    ReactDOM.render(
      <HashRouter>
        {/* The rest of your app goes here */}
      </HashRouter>,
      root
    );
    ```

### Route
Untuk memulai kita bisa menuliskan komponen Route untuk pathnya dan kemudian menaruh semua Route komponen di dalam single Routes . Saat URL kita berubah, react akan melihat isi dari Route yang kemudian render konten di elemen route tersebut yang pathnya sama dengan URL tersebut.

```JS
import { Route, Routes } from "react-router-dom"
import { Home } from "./Home"
import { BookList } from "./BookList"

export function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/books" element={<BookList />} />
    </Routes>
  )
}
```

### Link 
Biasanya ketika kita ingin pindah suatu halaman kita akan menggunakan anchor tag, tetapi React Router mempunyai custom komponen yaitu Link yang berfungsi seperti layaknya anchor tag.

```JS
import { Route, Routes, Link } from "react-router-dom"
import { Home } from "./Home"
import { BookList } from "./BookList"

export function App() {
  return (
    <>
      <nav>
        <ul>
          <li><Link to="/">Home</Link></li>
          <li><Link to="/books">Books</Link></li>
        </ul>
      </nav>

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/books" element={<BookList />} />
      </Routes>
    </>
  )
}
```

### Route Lanjutan
Ada berbagai macam teknik penggunan routing yaitu diantaranya :
- Dynamic Routing
- Nested Routes

### Dynamic Routing
Cara paling simpel dan yang sering digunakan di React Router ialah Dynamic Routing. Contohnya jika kita render sebuah komponen untuk setiap web kita, kita dapat menulis masing-masing route tersebut, namun hal tersebut terlihat tidak mungkin untuk ditulis untuk semua route-nya . Jadi disini peran Dynamic Route berada.
```JS
<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/books" element={<BookList />} />
  <Route path="/books/:id" element={<Book />} />
</Routes>
```

### Nested Routes
Nested routes memungkinkan kita untuk render banyak komponen di satu halaman, Ini berguna untuk user jika mereka ingin masuk kedalam sebuah halaman dan tetap tracking posisi mereka saat ini.

![Nested](https://res.cloudinary.com/practicaldev/image/fetch/s--woYtEIif--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fbvp5tclz9pcugs0mlmw.png)

```JS
<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/books">
    <Route index element={<BookList />} />
    <Route path=":id" element={<Book />} />
    <Route path="new" element={<NewBook />} />
  </Route>
  <Route path="*" element={<NotFound />} />
</Routes>
```

Yang perlu kita lakukan hanyalah membuat parent dari Route yang mempunyai path prop yang dibagikan ke seluruh child route.

## State Management 
### React Redux
Redux adalah salah satu state management yang sangat populer digunakan di reactjs untuk mengolah state management dengan cara menyimpan state di satu tempat, sehingga lebih mudah untuk di manage. 

### Instalasi Redux
Kita install menggunakan npm
```
npm install redux react-redux
```

### Konsep Utama Redux
- Action 
- Reducer 
- Store 

### Action
Action merupakan sebuah function yang mereturn sebuah objek. Action wajib memiliki type property dan input apapun untuk melakukan action.

```JS
const increment = () => {
    return {
        type: 'INCREMENT'
    }
}
```

### Reducer
Reducer merupakan sebuah fungsi yang tugasnya untuk mengolah state yang ada di store.

```JS
const counter = (state = 0, action) => {
    switch(action.type) {
        case 'INCREMENT':
            return state + 1;
        default:
            return state;
    }
}
```

### Store
Store menyimpan state dan juga memperbarui state.
```JS
import { createStore } from 'redux';

const store = createStore(counter);
// Note: we passed the reducer to create the store
```

### useSelector
useSelector adalah function yang mengambil state saat ini sebagai argumen dan mengembalikan data apa pun yang Anda inginkan darinya.
```JS
const result: any = useSelector(selector: Function, equalityFn?: Function)
```

### useDispatch
useDispatch mengembalikan referensi ke fungsi dispatch dari redux store. Anda dapat menggunakannya untuk mengirimkan actions sesuai kebutuhan.

```JS
const dispatch = useDispatch()
```

## Async Actions with Middleware and Thunk
### Redux Thunk
Thunk adalah konsep pemrograman yang menggunakan fungsi untuk menunda evaluasi/kalkulasi suatu operasi.

Redux Thunk adalah sebuah  middleware yang memungkinkan Anda untuk menulis Action yang mengembalikan function, bukan action. 
### Instalasi Redux Thunk
Kita install redux menggunakan npm
```
npm install redux-thunk
```

Sekarang, terapkan middleware saat membuat penyimpanan aplikasi menggunakan applyMiddleware Redux. 

```JS
import React from 'react';
import ReactDOM from 'react-dom';
import { Provider } from 'react-redux';
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import './index.css';
import rootReducer from './reducers';
import App from './App';
import * as serviceWorker from './serviceWorker';

// use applyMiddleware to add the thunk middleware to the store
const store = createStore(rootReducer, applyMiddleware(thunk));

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
);
```

### Contoh Penggunaan Redux Thunk
Kasus penggunaan paling umum untuk Redux Thunk adalah berkomunikasi secara asinkron dengan API eksternal untuk mengambil atau menyimpan data. Redux Thunk memudahkan pengiriman aksi yang mengikuti siklus hidup permintaan ke API eksternal.

Membuat item agenda baru biasanya melibatkan pengiriman aksi terlebih dahulu untuk mengindikasikan bahwa pembuatan item agenda telah dimulai. Kemudian, jika item agenda berhasil dibuat dan dikembalikan oleh server eksternal, aksi lain akan dikirim bersama item agenda baru. Jika ada kesalahan dan agenda gagal disimpan di server, sebuah aksi bersama kesalahan dapat dikirim sebagai gantinya.

Contoh file AddTodo.js
```JS
import { connect } from 'react-redux';
import { addTodo } from '../actions';
import NewTodo from '../components/NewTodo';

const mapDispatchToProps = dispatch => {
  return {
    onAddTodo: todo => {
      dispatch(addTodo(todo));
    }
  };
};

export default connect(
  null,
  mapDispatchToProps
)(NewTodo);
```

Contoh file index.js
```JS
import {
  ADD_TODO_SUCCESS,
  ADD_TODO_FAILURE,
  ADD_TODO_STARTED,
  DELETE_TODO
} from '../actions/types';

const initialState = {
  loading: false,
  todos: [],
  error: null
};

export default function todosReducer(state = initialState, action) {
  switch (action.type) {
    case ADD_TODO_STARTED:
      return {
        ...state,
        loading: true
      };
    case ADD_TODO_SUCCESS:
      return {
        ...state,
        loading: false,
        error: null,
        todos: [...state.todos, action.payload]
      };
    case ADD_TODO_FAILURE:
      return {
        ...state,
        loading: false,
        error: action.payload.error
      };
    default:
      return state;
  }
}
```



