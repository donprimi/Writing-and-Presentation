# WEEK 1 - Front End Bootcamp

## Day 1 : ReactJS
- Javascript biasanya hanya bisa berjalan di web browser dengan bantuan HTML
- Dengan adanya **NodeJS** maka javascrpit bisa berjalan diluar browser
- NodeJS bisa digunakan untuk mendownload package yang disediakan React
- React JS merupakan library javascript untuk mempermudah kita
- Selain React ada juga alternatif lain seperti Angular, Vue, dan Svelte
- _Berbasis komponen_ = Dengan React kita bisa membuat asset komponen yang bisa dipake berulang kali
_(cth : Membuat navbar cukup sekali untuk beberapa page, jika ada perubahan cukup ubah di main navbarnya aja nanti yang lain ikut keupdate)_
- Untuk install React dapat menggunakan `npx create-react-app namafile` lalu `npm start` (tanda sudah terinstall adalah terdapat tulisan "happy coding")
- SPA (Single Page Application) = file HTML cukup 1 tidak perlu per page

- ReactJS Virtual DOM merupakan copy dr Real DOM
- Kalo pake Real DOM render perubahannya lama karena selalu render dr awal
- Sedangkan kalo pake Virtual DOM yang dirender cuman di perubahan yang baru dibikin, gak render semua dr awal

- di dalam `div id="root"` kita menyisipkan halaman halaman yang dibutuhkan
- `JSX` adalah Javascript XML yang penulisannya seperti HTML. Tanpa JSX code akan sulit penulisannya
- React hanya bisa return 1 element maka harus dibungkus dengan `<div>` atau fragment kosong `<>`
- Setiap membuat component nama functionnya harus capital diawal  (function **Home**())
- import **file** from **'.folder/file'**

```
function Home (){
 return (
   <div> 
      <h1> Hallo </h1>
   </div>
 )
}

export default Home
```

- `Class` dalam JSX ditulis `ClassName`
- Untuk memberhentikan npm bisa menggunakan `ctrl + c` atau `npm kill-host 300`

## Day 2 : React Component

- React component dibutuhkan ketika memerlukan element untuk dipakai berulang kali 
- Bisa membuat folder react menggunakan [Vite](Vitejs.dev/guide) agar lebih cepat
	`npm create vite@latest nama-folder --template react`
- Untuk menggunakan cdn bootstrap bisa disisipkan di index.html
- File utama dalam `src` adalah `main.jsx` dan biasanya ada CSS bawaannya
- Untuk membuat component perlu membuat folder `component` dulu yang isinya menampung banyak component
- `state` adalah data yang ada di dalam component
- `props` adalah data yang dikasih yang nanti akan diterima mirip ketika memberi attribute <br/>
  _(data **state** dikasih ke dalam **props**)_ 
- Terdapat component `stateless` yang berarti tidak memiliki data yang dinamis
- Untuk bisa menggunakan component harus dipanggil dulu `import nama from "./nama.css";`
- Menggunakan single tag ketika memanggil component di file utama`<navbar/>`
- Lalu di dalam template component panggil dengan `{props.namaproperty}`
- Nama property adalah isi data yang ingin ditampilkan menggunakan component (data yang ingin dicustom di component)
- Langkah menggunakan component
	- Membuat folder component & buat file component yg ingin dibuat menggunakan `.jsx`
	- Buat template componentnya (jangan lupa nama componentnya menggunakan capital di depannya)
	- Di file JSX utama misalnya `App.jsx` tulis import component dan tulis letak filenya (import..from..)
	- Sisipkan nama property dari component menggunakan single tag dan isi props atau attribute data
	  `<card nama="Beta" umur="17"/>`
	- Di file component tulis di parameter function `(props)`
	- Panggil data props dengan memanggil `{props.nama}`

## Day 3 
- State digunakan jika ada kemungkinan data untuk berubah ubah
- Contohnya perubahan data input, perubahan gambar ketika diklik, perubahan jumlah total harga, dll
- Untuk memanggil state bisa menggunakan `import {useState} from "react";`
- `useState` merupakan array isinya ada 2 [value, function] yang merupakan destructure
	**value** = nilai yang ditampilkan
	**function** = update data yang diinginkan (setCount, getCount, dll)
- `const [count, setCount] = useState (0)` 
	- Dalam kurung disebelah useState adalah nilai awal atau variabel yang ingin ditampilkan. Di kondisi ini kita ingin menampilkan angka 0
	- Kata **set** dalam setCount artinya merubah nilai, men set data
- Untuk mengetahui penulisan event bisa dilihat di [Handling Events](https://reactjs.org/docs/handling-events.html)
 

```
import {useState} from "react";

function Counter () {
  const [count, setCount] = useState(0)
  
  const increment = () => {
    console.log("incremet")
   
    setCount(count + 1)
  }

  const decrement = () => {
    setCount(count-1)
  }    

  return (
  <>
   <button onClick={decrement}> - </button>
   <span>{count}</span>
   <button onClick={increment}> + </button>
  </>
  ) 
}

export default Counter
``` 

- Ada cara untuk menambahkan argument pada function yang ada di dalam event dengan cara membuat **callback**
- Callback adalah cara untuk memastikan kode tertentu tidak dieksekusi sampai kode lain telah selesai dieksekusi

```
const handleClick = (name) => {
  console.log ("ini click dari" + name)
}

return {
 <>
  <h1 onClick={() = handleClick ("Beta")}>Heading</h1>
 </>
}

```

- Untuk menampilkan state berbentuk array atau object maka bisa di looping menggunakan cara mapping. Cara ini tepat utk dipakai karena `map` dapat sekaligus mereturn data kita
- `{users.map((item, index) => (
   <Card key={index} nama={item.name} umur={item.umur}/>
   ))}`
- Ketika menggunakan map maka harus memiliki key yang unique maka dari itu digunakan index agar key setiap card unique
- Kegunaan dari key adalah agar jika terjadi perubahan di salah satu data maka yang dirender hanya di bagian data tersebut saja _(key jadi penanda dan pembeda dari data lainnya)_

- **Conditional rendering** memperbolehkan kita untuk membuat suatu kondisi didalam state
  [LINK](https://reactjs.org/docs/conditional-rendering.html)
- Contohnya `const [isLogin, setIsLogin] = useState(false);`



## Day 4 
- Lifecycle merupakan masa hidup sebuah component
	- Mount: Component muncul
	- Update: Ada perubahan pada component _(contohnya input form login)_
	- Unmount: Component hilang _(component login hilang setelah submit)_
- Dari lifecycle diatas terdapat function tersendiri yaitu `DidMount`, `DidUpdate`, `WillUnmount`
- 3 function diatas hanya berlaku pada cara yang classic dengan penggunaan class
- Ada 2 cara membuat component yaitu dengan **class** dan **function**, yang akan kita pakai adalah function karena lebih sederhana sedangkan class adalah cara classic
- Kita bisa menambahkan side effect pada proses lifecycle menggunakan function serta callback `useEffect(() => {}` dengan menyisipkan `import {useEffect} from "react";`
- Jadi side effect ini berlaku ketika component ini menjalankan lifecyclenya sampai selesai dan auto berjalan ketika halaman dimuat
- Dalam VS code proses ngebacanya itu = function paling atas - mount pada return - baru side effect _(urutannya si side eefect di skip dulu, mount diduluin)_
- Ketika state ada yang berubah maka semua proses rendering diulang lagi dr awal seperti refresh
- Dapat menggunakan depedency berupa`[]` jika side effect ingin berlaku cukup sekali ketika mount saja tanpa berlaku ketika ada update

- `npm install axios` sebagai pengganti fetch
- Dengan menggunakan axios tidak perlu lagi menggunakan `.then` 2 kali dan tidak perlu merubah jadi json
- Hooks ditandai dengan function `use..`

- `useRef` digunakan untuk memanggil DOM dan bisa ditambahkan seperti `.value` dll
- untuk mentrigger useEffect agar jalan bisa memasukkan keterangan di `[]`

## Day 5
- `const form = () => {}`
- Untuk label pada form ada perbedaan penulisan dari `for` menjadi `htmlFor`
- `useState("")` digunakan ketika nilai awalnya 0
- `onChange` digunakan agar kita bisa menangkap perubahan contohnya ketika menginput data form (sbg jalur antara form & code kita)
- `<input type="text" value={name} onChange ={(e) => setName (e.target.value)} />`
- `onSubmit` digunakan untuk memberi hasil inputan kita untuk disimpan
- Penggunaan onChange atau onSubmit digunakan di tag parent seperti <form> bukan di child seperti <input>
- Jangan lupa kalo submit data itu hrs pake `preventDefault` biar gak ke refresh karena sifat bawaannya

```
const Form () => {
 const [name, setName] = useState ("");
 const [address, setAddress] = useState ("");
 const [program, setProgram] = useState ("");
 const [data, setData] = useState ({});
 
 const handleSubmit = (e) => {
  e.preventDefault();

  setData ({name, address});
  setName("");
  setAddress("");
  setProgram("");

 };

 console.log (data);

 return (
  <>
    <form>
      <label htmlFor ="name">Name</label>
      <input type="text" value={name} onChange=((e) => setName(e.target.value))/>
      <label htmlFor ="address">Address</label>
      <input type="text" value={address} onChange=((e) => setAddress(e.target.value))/>
      
      <label htmlFor="option">Program</label>
      <select value={program} onChange ((e) => setProgram(e.target.value))>
        <option value ="">select program</option>
        <option value="KM">KM</option>
        <option value="SIC">SIC</option>
        <option value="Amman">Amman</option>
      </select>

      <button type ="submit">Submit</button>

    </form>

    <br/>
    <h2>Name: {data.name}</h2>
    <h2> Address: {data.address}</h2>
    <h2>Program: {data.progrm}</h2>

  </>
 );
};
```

- Kegunaan string kosong `("")` pada name dan address dibawah preventDefault adalah agar setelah disubmit inputnya bisa kosong lagi
- Ketika ada option atau checkbox maka value diletakkan di parent elementnya _(si select)_
- Untuk melihat dokumentasi API Axios bisa dilihat di [LINK](https://axios-http.com/docs/api_intro)
