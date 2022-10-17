# Week 4

## Day 1: API
- Cara kerjanya seperti ini: <br/>

Database (_kulkas_) -- Server (_dapur_) | **PELAYAN (_API_)** | Web application (_meja makan_)

- API merupakan perantara untuk mengambil data ke database
- Cara lain menangkap object promise menggunakan async `async function asyncNonton () {}` atau `let asyncNonton = async () => {}`

```
async function asyncNonton () {
 try {
   let result = await nonton ("jalan")
   console.log(result);
 } catch (error) {
   console.log(error)
 }
}

asyncNonton()
```
## Day 2: Github Lanjutan
- Untuk melakukan kolaborasi bisa membuat organisasi kemudian repository baru dan invite anggota
- Kemudian buat branch baru
- Setiap anggota harus clone repository yang tadi atau  `git pull` jika ada kode terbaru yang dipush dari anggota lain
- `git switch`atau`git checkout` gunanya untuk pindah branch
- kemudian bisa buat branch baru lagi didalamnya (jadi branch main itu tempat pengumpulan terakhirnya)
- Pull request mengajukan permintaan untuk menggabungkan branch kita ke yg lainnya
- Assignees ke team leader
- Conflict terjadi jika ada anggota yang merubah 1 file yang sama


## Day 3: Responsive Web Design & Bootstrap

### Responsive

- Responsive berarti tampilan web yang mengikuti ukuran device yang digunakan
- Viewport adalah area website yang dapat diakses user
- Terdapat banyak satuan unit yang bisa digunakan
	- **Absolute** : cm, px
	- **Relative** : em, rem, %, vw, vh
- Font size default HTML adalah 16px
```
@media (max-width: 500px) {
  .container {
    background-color: blue
  }
}
```

- Dari kode media query diatas berarti jika viewport kurang dari 500px maka backgorund berubah warna menjadi blue

### Bootsrap

- CSS Framework merupakan semacam template codingan yang siap untuk dipakai 
- Ada banyak contohnya Bootstrap, Tailwind,dan Bulma
- Cara mudah untuk menggunakan bootstrap bsia dengan copy CDN
- Column default ada 12 bagian kolom kecil
- Breakpoint adalah batasan batasan ukuran dari responsive
- Terdapat beberapa ukuran breakpoint 
	- Extra Small
	- Small
	- Medium
	- Large
	- Extra Large

Contohnya : jika pakai small, jadi ketika screen berubah jadi kecil (ada ukuran pxnya) maka element HTML berubah posisinya jadi kebawah
- Contoh penulisan kolom `col-lg-8` = artinya column tersebut memiliki breakpoint pada ukuran larga dan memiliki 8 dari 12 bagian kolom
