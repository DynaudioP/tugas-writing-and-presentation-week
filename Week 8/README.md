# Rangkuman Writing & Presentation Week 8
## React Context
Context API merupakan sebuah cara untuk membuat global state yang nanti bisa digunakan di semua level komponen tanpa harus mengirim props ke lower level component secara manual.

### Membuat Context
Untuk membuat context, gunakan function context
```JS
export const LocaleContext = React.createContext('en');
```

### Provider
Komponen Provider digunakan untuk membungkus komponen tree yang akan membutuhkan akses ke nilai dari konteksnya.
```JS
export const LocaleContext = React.createContext();

class LocaleProvider extends React.Component {
  constructor(props) {
    super(props);

    this.changeLocale = () => {
      this.setState(state => {
        const newLocale = state.locale === 'en' ? 'fr' : 'en';
        return {
          locale: newLocale
        };
      });
    };

    this.state = {
      locale: 'en',
      changeLocale: this.changeLocale
    };
  }

  render() {
    return (
      <LocaleContext.Provider value={this.state}>
        {this.props.children}
      </LocaleContext.Provider>
    );
  }
}

export default LocaleProvider;
```

### Menggunakan Provider
Kita dapat menggunakan Provider di atas komponen App:
```JS
import LocaleProvider from './context/LocaleContext';
import Greeting from './Greeting';
import ToggleLocale from './ToggleLocale';

class App extends Component {
  render() {
    return (
      <LocaleProvider>
        <Greeting />
        <ToggleLocale />
      </LocaleProvider>
    );
  }
}

export default App;
```

### Consumer
Komponen React yang menerima perubahan context. Ini memungkinkan Anda menerima context di dalam komponen fungsi.
```JS
import { LocaleContext } from './context/LocaleContext';

export default () => {
  return (
    <LocaleContext.Consumer>
      {localeVal =>
        localeVal.locale === 'en' ? <h1>Welcome!</h1> : <h1>Bienvenue!</h1>
      }
    </LocaleContext.Consumer>
  );
};
```

## React Testing
React Testing Library adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya. Pendekatan ini membuat refactoring menjadi mudah dan juga mendorong Anda untuk menerapkan best practices untuk aksesbilitas.

### Manual Testing
Manual Testing adalah langkah untuk mencari cacat atau bug pada program perangkat lunak, pada metode ini tester/penguji memiliki peran penting sebagai pengguna akhir untuk pengecekan semua fitur aplikasi bekerja dengan benar. Penguji melakukan pengecekan secara manual tanpa menggunakan bantuan dari tools atau scripts, tujuannya adalah untuk memastikan jika aplikasi yang di uji bebas cacat dan aplikasi perangkat lunak dapat bekerja sesuai apa yang diharapkan.

| Kelebihan                               | Kekurangan                                 |
|-----------------------------------------|--------------------------------------------|
| Mendapatakan Visual Feedback.           | Kurang teliti daripada automation testing. |
| Unsur Manusia                           | Tidak Reusable                             |
| Lebih murah dalam proyek jangka pendek. | Kelelahan terhadap tester.                 |

### Automated Testing
Automated test bergantung pada pra-scripted tes yang berjalan secara otomatis, fungsinya untuk membandingkan hasil yang diharapkan dengan hasil yang sebenarnya. Sehingga dapat mengetahui apakah aplikasi berjalan sesuai dengan apa yang diharapkan, menggunakan automated testing dapat dilakukan secara berulang.

| Kelebihan                                            | Kekurangan                         |
|------------------------------------------------------|------------------------------------|
| Dapat menemukan bug lebih banyak dari manual tester. | Lebih mahal                        |
| Kecepatan dan efisiensi                              | Kurangnya Human Element            |
| Test Reusable                                        | Tidak adanya feedback mengenai UI. |

### Test Driven Development (TDD)
TDD merupakan suatu proses software development yang mengutamakan pembuatan test sebelum melakukan implementasi pada aplikasi. Berikut merupakan life cycle dari sebuah proses TDD.

![TDD](https://miro.medium.com/max/828/0*l-U_MOAXzlL5mpb4.jpeg)

Terdapat tiga checklist pada proses TDD, yaitu:
- RED 
Menulis test yang menggambarkan fitur yang ingin dikembangkan dan pastikan test tersebut gagal
- GREEN 
Menulis implementasi yang paling simpel, tidak perlu memikirkan kualitas kode yang digunakan, cukup untuk lolos dari tes yang sebelumnya dibuat
- REFACTOR 
Me-refactor aplikasi yang sebelumnya dibuat menjadi lebih efisien dan berkualitas, dan tentunya tetap lolos dari test yang sebelumnya dibuat

### Jest
Jest adalah JavaScript test runner, yaitu library JavaScript untuk membuat, menjalankan, dan menyusun pengujian.

```
npm i jest --save-dev
```

Buat file bernama filterByTerm.spec.js dan mulai menulis tes

```JS
describe("Filter function", () => {
  test("it should filter by a search term (link)", () => {
    const input = [
      { id: 1, url: "https://www.url1.dev" },
      { id: 2, url: "https://www.url2.dev" },
      { id: 3, url: "https://www.link3.dev" }
    ];

    const output = [{ id: 3, url: "https://www.link3.dev" }];

    expect(filterByTerm(input, "link")).toEqual(output);

  });
});
```

lalu tulis untuk memulai tes
```
npm test
```

Berikut merupakan hasilnya
```
FAIL  __tests__/filterByTerm.spec.js
  Filter function
    ✕ it should filter by a search term (2ms)

  ● Filter function › it should filter by a search term (link)

    ReferenceError: filterByTerm is not defined

       9 |     const output = [{ id: 3, url: "https://www.link3.dev" }];
      10 | 
    > 11 |     expect(filterByTerm(input, "link")).toEqual(output);
         |     ^
      12 |   });
      13 | });
      14 |
```

Kemudian kita coba untuk mengimplementasikan function filter agar bisa mem-filter elemen dari sebuah array 

```JS
function filterByTerm(inputArr, searchTerm) {
  return inputArr.filter(function(arrayElement) {
    return arrayElement.url.match(searchTerm);
  });
}

describe("Filter function", () => {
  test("it should filter by a search term (link)", () => {
    const input = [
      { id: 1, url: "https://www.url1.dev" },
      { id: 2, url: "https://www.url2.dev" },
      { id: 3, url: "https://www.link3.dev" }
    ];

    const output = [{ id: 3, url: "https://www.link3.dev" }];

    expect(filterByTerm(input, "link")).toEqual(output);
  });
});
```

Lalu kita jalankan tes dan ini merupakan hasil yang didapatkan
```
 PASS  __tests__/filterByTerm.spec.js
  Filter function
    ✓ it should filter by a search term (link) (4ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        0.836s, estimated 1s
```

### React Testing Library
React Testing Library adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya. Pendekatan ini membuat refactoring menjadi mudah dan juga mendorong Anda untuk menerapkan best practices untuk aksesbilitas.

```
npm install --save-dev @testing-library/react
```

Pertama kita import testing library, api serta hal-hal yang dibutuhkan.
```JS
// import dependencies
import React from 'react'

// import API mocking utilities from Mock Service Worker
import {rest} from 'msw'
import {setupServer} from 'msw/node'

// import react-testing methods
import {render, fireEvent, waitFor, screen} from '@testing-library/react'

// add custom jest matchers from jest-dom
import '@testing-library/jest-dom'
// the component to test
import Fetch from '../fetch'
```

```JS
test('loads and displays greeting', async () => {
  // Arrange
  // Act
  // Assert
})
```

### Mock
Kita gunakan function setupServer dari msw untuk mock API request yang dibuat tested component.

```JS
// declare which API requests to mock
const server = setupServer(
  // capture "GET /greeting" requests
  rest.get('/greeting', (req, res, ctx) => {
    // respond using a mocked JSON body
    return res(ctx.json({greeting: 'hello there'}))
  }),
)

// establish API mocking before all tests
beforeAll(() => server.listen())
// reset any request handlers that are declared as a part of our tests
// (i.e. for testing one-time error scenarios)
afterEach(() => server.resetHandlers())
// clean up once the tests are done
afterAll(() => server.close())

// ...

test('handles server error', async () => {
  server.use(
    // override the initial "GET /greeting" request handler
    // to return a 500 Server Error
    rest.get('/greeting', (req, res, ctx) => {
      return res(ctx.status(500))
    }),
  )

  // ...
})
```

### Arrange
Kita render React element ke dalam DOM menggunakan method render
```JS
render(<Fetch url="/greeting" />)
```

### Act
Kita gunakan fireEvent method untuk memulai simulasi user actions
```JS
fireEvent.click(screen.getByText('Load Greeting'))

// wait until the `get` request promise resolves and
// the component calls setState and re-renders.
// `waitFor` waits until the callback doesn't throw an error

await waitFor(() =>
  // getByRole throws an error if it cannot find an element
  screen.getByRole('heading'),
)
```

### Assert
```JS
// assert that the alert message is correct using
// toHaveTextContent, a custom matcher from jest-dom.
expect(screen.getByRole('alert')).toHaveTextContent('Oops, failed to fetch!')

// assert that the button is not disabled using
// toBeDisabled, a custom matcher from jest-dom.
expect(screen.getByRole('button')).not.toBeDisabled()
```

Berikut merupakan keseluruhan kode dari setiap section-section diatas
```JS
import React from 'react'
import {rest} from 'msw'
import {setupServer} from 'msw/node'
import {render, fireEvent, waitFor, screen} from '@testing-library/react'
import '@testing-library/jest-dom'
import Fetch from '../fetch'

const server = setupServer(
  rest.get('/greeting', (req, res, ctx) => {
    return res(ctx.json({greeting: 'hello there'}))
  }),
)

beforeAll(() => server.listen())
afterEach(() => server.resetHandlers())
afterAll(() => server.close())

test('loads and displays greeting', async () => {
  render(<Fetch url="/greeting" />)

  fireEvent.click(screen.getByText('Load Greeting'))

  await waitFor(() => screen.getByRole('heading'))

  expect(screen.getByRole('heading')).toHaveTextContent('hello there')
  expect(screen.getByRole('button')).toBeDisabled()
})

test('handles server error', async () => {
  server.use(
    rest.get('/greeting', (req, res, ctx) => {
      return res(ctx.status(500))
    }),
  )

  render(<Fetch url="/greeting" />)

  fireEvent.click(screen.getByText('Load Greeting'))

  await waitFor(() => screen.getByRole('alert'))

  expect(screen.getByRole('alert')).toHaveTextContent('Oops, failed to fetch!')
  expect(screen.getByRole('button')).not.toBeDisabled()
})
```



