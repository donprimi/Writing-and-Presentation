# WEEK 3

## Day 1 : React Context
- Mirip fungsinya seperti redux tetapi tidak perlu install tambahan
- Tapi context ini bukan termasuk state management, dia hanya menyediakan komponen secara global
- Context ini berbentuk component yang akan memprovide app kita
- `const MyContext = createContext()` dan jangan lupa `import {createContext} from 'react'`


## Day 2 : useReducer
- Dengan `useReducer`dapat membuat context menjadi state management karena sudah memiliki tempat penyimpanan
- `const [state, dispatch] = useReducer(reducer, initialState)`


```
function CounterProvider({children}) {
  const [state, dispatch] = useReducer(reducer, initialState)

  const increment = () => {
    dispatch({type: INCREMENT});
  }

  return (
    <CounterContext.Provider value={{state, increment}}>
      {children}
    </CounterContext.Provider> 
  )
}

```

## Day 3 : React Testing
- Manual testing berarti kita mengecek kesalahan secara manual
- Ada 2 macam testing yaitu manual dan automation
	- Manual 
	- Automation : menggunakan kode testing
		- Unit		   : Kode cepat & murah, Bagian yang paling kecil seperti function, oleh developer
		- Integration  	   : Melakukan testing yang saling berhubungan dengan aplikasi lain (misalnya database)
		- End to End (E2E) : Kode lambat & mahal, Testing dari sisi user seperti experience


- RTL = React Testing Library (sudah include Jest). Dia semi E2E

- 2 cara nulis testing
	- buat fitur -> testing (biasanya startup)
	- testing -> buat fitur
		- TDD (test fails, test  passes, refactor)
		  ekspektasi, menulis kode, menyempurnakan kodenya agar lebih rapi

- Menulis testing itu harus jelas spec yang ingin dibuat
- Install terlebih dahulu `npm install -D jest`
- Membuat file baru `app.test.js`


```
const sum = require('./app');

test ('menjumlahkan angka pada sum()', () => {
 expect(sum (0,0)).toBe(0)
 expect(sum (0,1)).toBe(1)
 expect(sum (1,1)).toBe(2)
})
```
- di app ada :
	`const sum = (x, y) => x + y` <br/>
	`module.exports = sum`

- Nanti di terminal ketik `npm run test `, disana akan ada tulisan dia failed atau passed
- [JEST](https://jestjs.io/docs/using-matchers)
