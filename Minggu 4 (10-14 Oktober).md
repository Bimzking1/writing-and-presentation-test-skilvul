- Paulus Bimo Satrio Aji
- Politeknik Elektronika Negeri Surabaya
- Frontend Web Development
- FEBE-32 and FE-8
---

# Writing and Presentation Test Week 4

## Senin, 10 Oktober 2022

### A. **Asynchronous**
- Promise 
  ```
    function GetUser(id) {
        return new Promise((resolve, reject) => {
            if (id !== "" && id !== undefined) {
                resolve (id);
            } else {
                reject ("ID Harus di Isi");
            }
        });
    }
    
    GetUser( ) // memanggil fungsinya GetUser
    .then((response) => {
        console.log(response);
    })
    .catch((error) => {
        console.log(error);
    });
   ```
- Fetch
  ```
    let getDataDigimon = asnyc() => {
        let URL = "https://digimon-api.vercel.app/api/digimon";
        let response = await fetch(URL);
        let digimons = await response.json();

        digimons.slice(0, 10).forEach(item => {
            console.log(item);
        });
    }

    getDataDigimon();
  ```
- HTTP Request berfungsi sebagai alat komunikasi frontend dengan backend
- HTTP Request Method
   - GET untuk mengambil data 
   - POST untuk mengirimkan data
   - PUT untuk mengirimkan atau memperbaharui data
   - DELETE untuk menghapus data
   
## Selasa, 11 Oktober 2022

### A. Git & GitHub Lanjutan

- Perintah `git log` dapat **digunakan** untuk **melihat** catatan log dari **commit** yang pernah **dilakukan**.
    #### Melihat log menggunakan nomor version - commit.
    ` git log 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff`
    #### Melihat log file tertentu
    `git log index.html`
    #### Melihat log berdasarkan author
    `git log --author='Fabyan Kindarya'`
#### Membatalkan Perubahan
- Jika perubahan yang sedang dilakukan terjadi kesalahan dan kita ingin mengembalikan keadaan seperti sebelumnya maka dapat dilakukan menggunakan beberapa perintah git.
    #### Kondisi Belum Staged dan Belum Commit
    - Belum di git add.
        `git checkout index.html`
    #### Kondisi Sudah Staged dan Belum Commit
    - Sudah di git add.
        `git reset index.html` lalu melakukan `git checkout index.html`.
    #### Kondisi Sudah Commit
    - Kita bisa mengembalikan commit hanya pada file tertentu.
        `git checkout 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff index.html` lalu melakukan `git reset index.html`.
    - Kita bisa mengembalikan commit untuk semua file.
        `git checkout 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff`
    - Jika ingin mengembalikan 3 commit sebelumnya
        `git checkout HEAD~3 index.html`
- Git Revert membatalkan semua perubahan yang ada tanpa menghapus commit terakhir. 
    `git revert -n <nomor commit>`
#### Git Branch
- Fitur yang wajib digunakan jika berkolaborasi dengan developer atau dalam tim. Untuk menghindari conflict code yang dikembangkan, kita tidak boleh berkolaborasi dalam project di satu branch yang sama.
    - Untuk membuat branch, gunakan perintah :
        `git branch <branch>`
    - Melihat list branch, gunakan perintah :
        `git branch`
    - Pindah ke branch tertentu, gunakan perintah :
        `git checkout <branch>` atau `git switch <branch>`
    - Delete branch, gunakan perintah :
        `git branch -d <branch>`
#### Git Merge
- Setelah membuat branch baru dan melakukan commit. Saatnya menyatukan pekerjaan ke master file / branch utama. Untuk menyatukan branch yang telah kita buat, gunakan perintah :
    1. `git checkout main`
    2. `git merge <branch>`
   
## Rabu, 12 Oktober 2022

 ### A. **Responsive Web Design**
- **Responsive Web Design** yaitu suatu tampilan website yang dapat menyesuikan dengan perangkat yang digunakan
- Dalam menggunakan Responsive Web Design pada bagian HTML perlu ditambahkan **viewport** pada bagian head agar tampilan website dapat menyesuaikan dengan berbagai device
- Untuk membuat suatu gambar pada halaman website agar menjadi responsive dapat dilakukan dengan menambahkan atribut Max - width = 100% pada bagian gambar

### B. **Media Query**
- **Media Query** adalah salah satu cara untuk mengatur suatu website agar bisa terdiri dari beberapa jenis 
- Penggunaan media query yang umum digunakan adalah min-width dan max-width
- Contoh penerapan media query 
  `` @media screen and (max-width: 500px)``
- Cara mengkondisikan Media Query ada 2 cara yaitu:
  - Memisahkan beberapa file css sesuai dengan tampilan device yang ingin dibuat 
  - Menggabungkan semua styling css device menjadi 1 
- Breakpoint yaitu istilah saat terjadi perubahan ukuran pada suatu website ketika berganti device
- Terdapat 3 jenis breakpoint yaitu desktop, tablet, dan mobile phone
- Penggunaan breakpoint pada media query dapat dilakukan dengan membuat range ukuran sesuai dengan tampilan device yang ingin dibuat
- Contoh breakpoint dapat ditulis seperti ini
  ```
    @media screen and (min-width: 500px) and (max-width: 700px) {
        body {
            background-color: grey 
        }
    }
  ```
- Flexbox bertujuan untuk membuat website yang lebih efisien dalam mengatur, menata dan item pada dalam sebuah wadah bahkan ketika ukurannya tidak diketahui dan/atau dinamis (dengan menggunakan kata "flex").
- Flexbox properties :
  - Flex direction: menetapkan sumbu utama item, sehingga menentukan arah item fleksibel ditempatkan di wadah fleksibel. 
    - Row : Kiri ke kanan
    - Row-Reverse : Kanan ke kiri
    - Column : Atas ke bawah
    - Column-Reverse : Bawah ke atas
  - Flex Wrap: Secara default, semua item pada flexbox akan mencoba berada dalam satu baris. Maka dengan flex wrap kita dapat mengubah hal tersebut.
    - nowrap : semua item flex akan berada dalam satu baris
    - wrap : item fkex akan membungkus ke beberapa baris, dari atas ke bawah.
    - wrap-reverse :item flex akan membungkus beberapa baris dari bawah ke atas.
  - Flex flow: cara singkat untuk properti flex-direction dan flex-wrap, yang bersama-sama menentukan sumbu utama dan sumbu silang container flex. Nilai default adalah baris nowrap.
- Grid merupakan sistem tata letak berbasis dua dimensi.
- Pada Grid ada 2 jenis yaitu grid container dan grid item.

### C. **Bootstrap**
- Bootstrap adalah salah satu framework opensource yang berfungsi membuat suatu responsive website
- Komponen utama bootstrap :
  - bootstrap.css
  - bootstrap.js
- Cara konfigurasi bootstrap :
  - Membuat tag boostrap di head. Cara memanggil css bootstrap dengan menggunakan href lalu mengganti link href css lokal dengan link boostrap online.
- Contoh penggunaan content bootstrap :
  - CSS : bootstrap.min.css, bootstrap-grid.css, dll
  - JS : bootstrap.bundle.js, bootstrap.min.js, dll
- Komponen Bootstrap sebagian besar dibangun dengan base-modifier nomenclature.Contohnya mengelompokkan beberapa properti kedalam kelas dasar seperti .btn, seperti .btn-primary or .btn-success.
- Penggunaan theme color pada boostrap dapat menggunakan keyword berikut :
  ```
  $theme-colors: (
    "primary":    $primary,
    "secondary":  $secondary,
    "success":    $success,
    "info":       $info,
    "warning":    $warning,
    "danger":     $danger,
    "light":      $light,
    "dark":       $dark
  );
  ```

- Boostrap digunakan ketika membuat website sederhana dan tidak memerlukan load lama.
- Layout pada boostrap :
  - Breakpoints merupakan suatu cara yang dilakukan untuk membuat desain responsif dengan mengontrol kapan tata letak yang disesuaikan dengan ukuran perangkat
    tertentu.
    - Breakpoints pada bootstrap ada 5 yaitu sm, md, lg, xl dan xxl.
    - Setiap breakpoint dipilih untuk menampung container yang lebarnya 12 dengan sehingga tersusun rapi. Breakpoint juga mewakili subset ukuran perangkat umum dan
    dimensi area pandang.
 - Container adalah blok dasar atau pembungkus boostrap yang terdiri dari contain, pad dan align  yang menyelaraskan konten website dalam perangkat atau area      
    pandang tertentu.
   - Terdapat 3 container pada boostrap yaitu :
    - .container, yang menerapkan lebar maksimum pada setiap breakpoint responsif
    - .container-{breakpoint}, menerapkan lebar 100% sampai dengan breakpoint yang ditentukan.
    - .container-fluid, menerapkan 100% ukurannya dari breakpoints
 - Grid System pada bootstrap yang terdiri dari 12 kolom default.
 - Grid system pada bootstrap menggunakan container,baris dan kolom untuk menata dan menyelaraskan konten,yang dibangun menggunakan flexbox dan itu sudah responsive.
 
  - contoh penggunaan grid system
   ``` 
     <div class="container text-center">
        <div class="row">
            <div class="col">
                Column
            </div>
            <div class="col">
                Column
            </div>
            <div class="col">
                Column
            </div>
        </div>
     </div>
   ```
- Grid system bootstrap :
  - .col-lg digunakan untuk mengatur grid pada ukuran monitor yang besar
  - .col-md digunakan pada monitor komputer berukuran sedang
  - .col-sm digunakan untuk mengatur monitor pada tablet
  - .col-xs digunakan untuk mengatur monitor pada handphone 
