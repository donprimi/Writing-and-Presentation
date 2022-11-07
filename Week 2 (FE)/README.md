# Week 2 - Front End Bootcamp

## Day 1 : Proptypes
- Prop Types digunakan untuk mengecek tipe data yang akan kita kirim agar tidak terjadi salah tangkap data
- Kalo data yang diminta dan data yang dikirim tidak sesuai maka akan ada warning di console log tetapi code tetap bisa berjalan
- `npm install prop-types`
- `import PropTypes from "prop-types"`

```
StudentInfo.propTypes = {
  name : PropTypes.string,
  age: PropTypes.number,

};
```
- `PropTypes.any`
- `PropTypes.oneOfType ([PropTypes.string, PropTypes.number])`
- `.isRequired`
- `PropTypes.shape({})`

## Day 2 : Router
- Router digunakan untuk berpindah2 halaman karena pada dasarnya react dikenal dengan single page
- Router ini mirip tag `<a>` untuk berpindah tanpa reload tetapi disini namanya `<link>`
- React router banyak versinya tapi kita pakai yang versi 6
- Harus install dulu `npm install react-router-dom@6`
- **Browser Router** digunakan sebagai penanda bahwa codingan kita menggunakan router
- Pada file **main** `import {BrowserRouter} from 'react-router-dom'` lalu dibawahnya bungkus `<app/>` dengan `<BrowserRouter>`
- Pada file **app** bisa menambahkan `import {Routes, Route, Link} from 'react-router-dom'` dengan menambahkan parent pembungkus <routes>
- Buat folder **pages** untuk menampung halaman halaman yang akan kita bikin
- Halaman yang menggunakan slice berupa `path='/'` akan ditampilkan paling awal ketika browser dibuka
- Untuk menyambungkan halaman bisa tambahkan `<Link to={"/about"}> About </Link>`



- Route biasanya tag single `<Route/>` tapi kalo mau bikin nested route bisa menggunakan tag penutup `<Route> </Route>`
- Untuk bisa mendeteksi anak2 dari nested route maka harus dilapor melalui outlet
- Navigation cocok untuk membawa data, beda dengan link



## Day 3 : Redux
- Macam macam state management : redux, context, jotai, zustand
- Dengan adanya redux tidak akan terjadi props drilling yang akan mengoper data dr parent ke child child lainnya
- Redux ini berguna untuk memanipulasi state management dalam react
- state management ini digunakan jika banyak komponen yang memerlukan 1 data yang sama
- Membuat tempat terpusat sehingga component yg membutuhkan tinggal ambil tanpa harus dioper oper
- `npm install redux react-redux`
- Pertama tama harus membuat tempa penyimpanannya yaitu `store`
- `const store = createStore (() => {})` didalamnya nanti ada function
- `action` digunakan untuk merubah data. dia merupakan function isinya object (dalam object ada property `type`)
- `payload` gunanya untuk membawa datanya	
	
	```
	const Actions = {
	 type: '',
	 payload: ''
	}	
	```

- `dispatch` digunakan sebagai perantara agar action yang ada didalam dispatch bisa mengubah data dalam reducer
- `...state` merupakan spread, dipakai agar initialState yang sudah ditulis bisa muncul semua

- Tahapan:
 	- Membuat tempat penyimpanan seperti gudang berupa `store` (di folder baru dan filenya .js)
	- Kemudian membuat penyimpanan kecil ibarat rak yaitu `reducer` (di folder baru dan filenya .js)
	- Membuat `initialState` yg isinya berupa value
	- Membuat perkondisian menggunakan switch case
	- Membuat `provider` untuk menandakan `store` kita tersedia untuk komponen biar bisa dipake (caranya bungkus tag app dgn provider)
	- Membuat component yang ingin dibuat
	- Mengambil data dari store melalui `useSelector`(sudah disediakan oleh react redux)
	- Ubah data pada store ke dalam reducer bisa menggunakan perantara berupa `dispatch` yang didalamnya ada action
	- Bikin folder `action` baru & file action berupa .js


## Day 4 & Day 5
- Dalam 1 store bisa menyimpan beberapa reducer menggunakan `combineReducers({a, b})`
- Thunk memberi bantuan agar dispatch bisa membawa action secara asyncronous (karena defaultnya syncronous, tidak bisa ditunda)



>**CATATAN**
>dalam react kita membutuhkan 2 folder baru yaitu component & redux dan ada isinya lagi
>	- Component
>	  - isinya file `.jsx`
>	  - redux
>	  - folder action _(isinya `.js`)_
>	  - folder reducer _(isinya `.js`)_
>  - folder store _(isinya `.js`)_

>Harus selalu install di tiap project baru
>	- Proptypes (bikin folder sendiri)
>	- React dan react redux
>	- React router (bikin folder sendiri)
>	- Bootstrap

