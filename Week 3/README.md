## Day 1: Array
- Bisa menampung banyak data dengan berbagai macam tipe data
`let arr = ["hallo", 1, true]`
- isi data array disebut index dan dimulai dari 0 <br/>
	[0] hallo <br/>
	[1] 1 <br/>
	[2] true <br/>
- `console.log(arr[nomor index])`

- Splice menghapus data dan menambahkannya
`arrBuah.splice(2, 3, "Buah Naga")` = diapus dari index ke 2 sebanyak 3 data dan ditambah dengan Buah Naga di tengah
- Slice mengambil data dalam array dengan cara mencopy sehingga data aslinya tidak terganggu		
`arrBuah.slice (2,4)` = diambil dari array ke 2 sampai 3 karena berhentinya di 4

## Day 2: Object
- Object dapat menyimpan beberapa tipe data, function bahkan object lagi
- Object tidak punya index dan length seperti array
- Nama lain dari property adalah **key**
- `let object = {property : value}`

```
let siswa = {
  nama: "terra",
  umur: 17,
  "nomor handphone": 08453682362,
}
```


- Cara akses object
	- Dot notation 
	`console.log(siswa.nama);`
	- Bracket _(berguna untuk properti yang memiliki spasi)_
	`console.log(siswa["nomor handphone"]);`
	- Variabel baru
	```
	let properti = "umur";
	console.log(siswa[properti])
	```

- Menambahkan properti
	- Menggunakan dot
	`siswa.hobi = membaca;`
	- Menggunakan bracket
	`siswa["jurusan"] = "IPS";`

- Merubah value properti
	- Menggunakan dot
	`siswa.nama = "Tara";`
	- Menggunakan bracket
	`siswa["umur"] = 19;`
- Isi properti dalam objek yang menggunakan **const** dapat diubah tapi **properti**nya aja jangan keseluruhan constnya
- Menghapus properti menggunakan `delete object.property;`

- Method
```
const greeting = {
  welcome: function () {
    return "halo selamat datang";
  },
}
```
- Object dapat dirubah menjadi array menggunakan `console.log(Object.keys(siswa));` atau berdasarkan isi dari properti `console.log(Object.values(siswa));`
- Nested object

- Untuk looping object bisa menggunakan `for...in`
```
for (let key in siswa) {
  console.log(siswa[key]);
}
```
_(maka nanti yang muncul adalah isi value dari property/key yang ada dalam object)_

- Array of object yaitu array yang isinya banyak object
`[{}, {}, {}]`

## Day 3: JS Modules & Recursive

### Modules
- Modules adalah cara untuk memisahkan kode ke file yang berbeda dan bisa saling terhubung
- Gunanya agar mudah untuk mengelola file dan tidak menumpuk di satu file
- Tidak bisa export 1 file harus pilih bagian mana yang harus di export
`<script src="./indonesia.js" type="module"></script>`
- file javascript yang disambung ke HTML seperti `indonesia.js` hanya bisa import tidak bisa export

`export let motor = ["suzuki", "yamaha", "honda"]`
`export {motor, smartphone}`

```
import {motor} from "./jepang.js"
comsole.log {motor};
```

- Kalo mau ubah nama variabel bisa `{motor as motorJepang} console.log {motorJepang}`
- `export default` merupakan export yang cuman bisa export 1 variabel utama secara bawaan
- Untuk memanggilnya tidak perlu menggunakan `{}`

### Recursive
- Function yang memanggil dirinya sendiri
- Menyelesaikan masalah dari yang terkecil
- Biasa digunakan untuk perhitungan matematika dan bisa menggantikan loopping

## Day 4: Asyncronous
- Single thread berarti memiliki 1 jalur proses
- Non blocking berarti mengizinkan proses lain untuk mendahului yang sebelumnya (diselak)
- Asyncronous proses yang dilakukan secara tidak berurutan atau mengerjakan proses yang lain dulu yang lebih ringan
_(jadi walaupun hanya 1 **jalur** tapi bisa tetap berjalan karna boleh **diselak** dan dilanjut prosesnya secara **tidak berurutan** karna ngelanjutin yang tadi belom selesai)_
- Proses yang terpotong dan tersambung ini disebut concurent

- Multi thread memiliki banyak jalur sehingga beberapa proses dilakukan secara bersamaan atau disebut multitask
- Kalo blocking itu biasanya syncronous karena tidak bisa diselak jadi harus berurutan prosesnya

- Javascript Asyncronous
	- Callback
	- Promises
	- Async Await
- `setTimeout` termasuk webAPI untuk memberi waktu untuk menjalankan proses (dipake saat simulasi asyncronous aja)
- Promises itu ada pending, fullfilled dan rejected
```
let nontonPromise = new Promise((resolve, reject) => {
  resolve ("nonton terpenuhi")
  reject ("gagal nonton")

nontonPromise
.then(result => {
  console.log(result)
})

.catch((err) => {
  console.log(err)
})

})
```
## Day 5: Web Storage
- Web storage berupa gudang penyimpanan dari web browser yang kita pakai
- Dapat menyimpan beberapa data seperti preferensi user, settings, dll
- Dibagi 2 yaitu local storage dan session storage
- Ketika tab ditutup maka yang di session akan hilang
- JSON fungsinya untuk mengkonversi data dari array menjadi string
