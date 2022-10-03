# Writing _(week 2)_
## Day 1 : Js Dasar-Scope & Funciton
- While merupakan kondisi dimana kita tidak tahu berapa kali atau berapa lama
berjalannya
- While = selama (contohnya: "selama air itu mengalir" jadi kita tidak tahu sampai kapannya)
- Terdapat 3 cara penulisan function:
	- Classic
	`function myFunction(kondisi){}`
	- Variable
	`let myFunction = function() {}`
	- Arrow
	`let myFunction = () => {}`

```
function cariAngka (x) {
 for (let i = 1; i <= 20; i++){
   if(i == x){
   console.log(i) 
   }
 }
}

cariAngka (5)
cariAngka (12)
```
- x disebut dengan **parameter** sedangkan 5 dan 12 disebut dengan **argument**
- Return nilainya dikembalikan lagi ke kita agar bisa dipakai atau diolah lagi datanya

```
function greeting(name){
  return 'hallo, ${name}'
}
```


## Day 2 : Data Type & Method
- Tipe data primitive (string, number, boolean)
- Tipe data non primitive merupakan pengembangan dari tipe data yang standar/primitive (array & object)
- typescript adalah type save untuk javascript
- `typeof` dapat digunakan untuk mengecek tipe data 
- Properties = anggepannya ciri ciri dari string (contohnya: punya berapa karakter) `console.log(variabel.length)`
- Method = kemampuan dari string (contohnya: bisa dirubah jadi uppercase `variabel.toUpperCase`
- Untuk mengetahui selengkapnya bisa cek di [String Properties and Methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- [Built in Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)

- contoh mengambil karakter dalam string 
menggunakan bantuan built in function
`console.log(hewan.includes("n"))`

menggunakan cara biasa dengan for
```
for (let i = 0; i<hewan.length; i++){
  if (hewan[i] == "n"){
    console.log(true)
  }
}
```
- Salah satu property pada tipe data number adalah isNaN (is Not a Number) yaitu untuk mengetahui apakah value itu bukan angka
- Faktanya `true` itu dianggap sebagai 1
- Untuk menggunakan rumus matematika bisa cek [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)

## Day 3 : DOM
- DOM (Document Object Model) berguna untuk mengambil data mengakses dan memanipulasi element html
 penghubung bahasa pemograman agar dapat berinteraksi dengan dokumen HTML
- DOM bukan bagian dari javascript tapi ia merupakan web API (programming interface)
```
<body>
  <a href= "#"> My Link </a>
```
- Nodelist merupakan per element dari syntax
	- < body >
	- < a >
	- "My Link"
	- "href"
- [Traversing elements](https://zellwk.com/blog/dom-traversals/)
	- Bawah (getElementById, getElementByTagName, querySelector, children)
	- Atas (parentElement, closest())
	- Samping (nestElementSibling, previousElementSibling)

```
<ul class= "list">
	<li class= "item"> satu </li>
	<li class= "item"> dua </li>
	<li class= "item"> tiga </li>
```
- Mengambil data berdasarkan class
```
let item = document.getElementsByClassName("item")
console.log(items[2]);
```

## Day 4 :DOM (Manipulation)
- Untuk mengetahui dokumentasi lengkap bisa cek [javascript DOM](https://www.javascripttutorial.net/javascript-dom/)
- `innerHTML = "<h1> hallo </h1>"`= dapat memasukkan html ke dalam isinya
-  `innerText = hallo` = merubah isi menjadi string
- bisa merubah styling contohnya `link.style.color = "black"`

## Day 5 :DOM (Events)
- Events berguna untuk menangkap interaksi user seperti hover, click, blur, dll
- Syntax event :
	- Element.addEventListener("event")
	- Element.onevent
- Ada beberapa cara untuk menggunakan DOM Events
	```
	<p onclick= "alert('selamat datang')"> Hallo </p>
	```
	```
	paragraf.onclick = function () {
	 alert("selamat datang")
	}
	```
  ```
	let paragrf = document.getElementById("paragraf")
	paragrf.addEventListener("click", function() => {
	  alert("selamat datang")
	})
	```
