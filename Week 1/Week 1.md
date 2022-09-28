# Writing and Presentation _(Week 1)_
## Day 1 : Unix Command Line, Git & Github

### Unix Command Line
- Shell adalah program yang digunakan untuk berkomunikasi yang menghubungkan user dengan sistem operasi
- CLI atau Command Line Interface adalah shell yang berbasis teks (contohnya : sh, bach, cmd.exe)
- Untuk mengakses CLI bisa menggunakan terminal
- GUI atau Graphical User Interface adalah shell dalam berbentuk grafis visual dimana user berinteraksi dengan icon dan button (contohnya : windows 10)
- `computer/film/annable.mov` “computer” adalah root dari data structure
- Navigation
    `pwd` : Mengetahui posisi saat ini berada dimana
    `ls` : Mengetahui list isi direktori
    `cd` : untuk berpindah direktori
- Manipulation
    `touch` : Membuat file baru
    `mkdir` : Membuat direktori baru
    `cp` : Menyalin file ke tempat lain
    `mv` : Memindahkan lokasi file atau rename nama file
    `rm` : Menghapus file
    `rm -r` : menghapus direktori bersama isinya
- Melihat isi file
    `head` : Melihat beberapa baris awal dari file
    `tail` : Melihat beberapa baris akhir dari file
    `cat` : Menampilkan seluruh isi file


### Git & Github
- Git adalah aplikasi untuk melacak perubahan yang ada di sebuah file atau direktori. Digunakan untuk menyimpan file agar lebih efektif
- Github merupakan salah satu tempat untuk menyimpan kode kita (contoh lain ada gitlab dan bitbucket)
- Origin adalah variabel dari branch yang kita buat
- Main merupakan sebutan dari branch utama project kita
- Command
`git config` : dilakukan di awal instalasi git untuk setup username dan email
`git init` : memasukkan git ke dalam kode project kita (dilakukan hanya sekali)
`git add` : Menambahkan perubahan ke dalam git
`git commit` : Menyimpan hasil add yang sebelumnya agar terdata
(Jika ada perubahan lagi maka lakukan `git add` kemudian `git commit` lagi agar terupdate)
`git push` : Mengupload kode project kita ke github
`git remote` : Menghubungkan project yang sebelumnya ada di local computer ke cloud github
`git clone` : mendownload kode dari github ke local computer

## Day 2 : HTML
- HTML berfungsi sebagai kerangka dasar dalam pembuatan website yang menampung kode kode lain seperti CSS dan Javascript
- Untuk menggunakan HTML diperlukan 2 tools yaitu code editor dan browser
- Code editor ada banyak seperti Sublime, Vim tetapi kita menggunakan Visual Studio Code
- Dalam VS Code terdapat banyak extension yang dapat mempermudah proses coding salah satunya adalah live server
- Kegunaan live server adalah kita dapat melihat kode di browser tanpa harus refresh lagi
- Struktur dari element HTML adalah:
`<p>` opening tag
`text` content 
`</p>` closing tag
Contoh tag HTML yang populer atau sering digunakan adalah `<img>`, `<video>`, `<table>`
- Semantic HTML adalah penggunaan element HTML sesuai dengan kebutuhan konten (contohnya penggunaan tag `<header>`,`<nav>`, `<footer>`)
- Keunggulan semantic HTML adalah meningkatkan accessibility, meningkatkan SEO dan mudah dimaintain
- Deployment adalah proses untuk menyebarkan web atau aplikasi yang sudah kita buat agar bisa digunakan oleh orang lain.  untuk mendeploy website bisa menggunakan [netlify]https://www.netlify.com/
    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <link rel="stylesheet" type="text/css" href="style.css" />
        <script src="script.js"></script>
    </head>
    <body> 
        <h1> hello </h1> 
    </body>
    </html>
    ```

## Day 3 : CSS
- CSS bertugas untuk memberi styling seperti warna, tata letak dan lainnya untuk tampilan visual sebuah website
- Struktur dasar CSS adalah `.elementHTML {property : value}`
- Penulisan CSS ada 3 macam:
    - Inline : Menyisipkan CSS ke dalam tag HTML `<p style=”color: red”> hello </p>`
    - Internal : Meletakkan CSS `<style>`di bagian `<head>` HTML
    - Eksternal : Membuat file terpisah dengan format `.css`
- Untuk memanggil class bisa menggunakan `.className` sedangkan id `#idName`
- Flexbox adalah metode untuk mengatur tata letak items yang bisa digunakan untuk mengatur alignment, direction dan order
    ```
    #Name {
    color : white
    Background-color : blue
    }
    ```

## Day 4 : Algoritma & Intro to javascript
### Algoritma
- Algoritma adalah langkah-langkah untuk menyelesaikan suatu masalah
- Contoh sederhananya adalah prosedur membuat kopi panas dalam cangkir
- Data struktur digunakan untuk mengelola data dan algoritma yang akan menyelesaikan masalah menggunakan data tersebut.
- Untuk bisa menggunakan bahasa pemrograman maka kita harus memahami dan mempelajari algoritma
- Pseudocode adalah penulisan algoritma yang biasanya dalam bahasa inggris sebelum dimasukkan kedalam bahasa pemrograman
- Penulisan dalam pseudocode
    - READ and SAVE "first number"
    - READ and SAVE "second number"
    - COMPUTE "first number" added by "second number"
    - SAVE previous computation result
    - SHOW the computation result
- Penulisan dalam javascript
    ```
    let a,b,c;
    a = prompt ("first number");
    b = prompt ("second number");
    c = Number (a) + Number (b);
    
    console.log ( c );
    alert ("Result = " + c");
    ```
### Intro to javascript
- Javascript adalah bahasa pemrograman yang berguna agar website menjadi interaktif dan dinamis
- Console log menjadi tempat yang sering digunakan untuk memeriksa kode kita
- Ada 2 cara yaitu memasukkan tag `<script>` di bagian bawah sebelum closing tag `</body>` dan membuat file terpisah dengan format `.js`
- Tipe data
    - Number : 1 2 3
    - String : “text”
    - Boolean : true false
    - Null : variable/data tidak memiliki nilai.
    - Undefined : disebabkan oleh error sehingga data tidak memiliki nilai
    - Object : dapat menampung beberapa tipe data
- 3 cara untuk mendeklarasikan variable var, let, dan const


## Day 5 : Js Dasar-Conditional dan Js Dasar-Looping
### Conditional
- Statement yang akan menjalankan perintah sesuai dengan kondisi yang sesuai
- Contoh sederhana : Jika lampu berwarna merah maka berhenti, jika berwarna hijau maka jalan
- Ada beberapa jenis conditional:
    - If else if
    - Switch case
    - Ternary operator
### Looping
- Looping adalah statement yang akan menjalankan perintah jika kondisi berhenti sudah tercapai
- Macam-macam looping
    - For loop (saat kita tahu butuh berapa kali pengulangan)
    - While
    - Do while

