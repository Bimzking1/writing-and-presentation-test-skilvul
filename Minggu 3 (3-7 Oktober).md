- Paulus Bimo Satrio Aji
- Politeknik Elektronika Negeri Surabaya
- Frontend Web Development
- FEBE-32 and FE-8
---

# Writing and Presentation Test Week 3

## Senin, 3 Oktober 2022

### A. Array

- **Array** merupakan sebuah tipe data yang dapat menyimpan banyak data seperti string, number, boolean, hingga object. Contoh: 
  ``` 
  Let randomData = ['ini string', 20, true];
  ```
  - Diatas adalah contoh Array yang berisi beberapa tipe data berbeda.
- **Array** pada dihitung mulai dari index ke-0 . Contoh:
  ``` 
  Let randomData = ['ini string', 20, true];
  console.log(randomDaData[1]); 
  
  Output: 20
  ```
  - Index ke-0 adalah 'ini string' dan index pertama adalah 20.
  
- **Deklarasi Array**
  - Let:
    - Array dapat diubah dengan nilai yang baru (re-declare).
  - Const:
    - Array tidak dapat melakukan update data. Namun dapat melakukan update konten di dalam array tersebut. Contohnya state.
    - Contoh:
      ``` 
      const cars = ['tesla', 'honda', 'toyota'];
      cars[2] = ['nissan'];

      console.log(cars)
      
      Output: ['tesla','honda','nissan']
      ```
      - Konten index kedua (toyota) berubah menjadi (nissan), tetapi data tersebut tetap milik ***cars***.
- Array biasa memiliki 5 properti yang sering digunakan, yaitu:
  - constructor
  - length
  - index 
  - input
  - prototype
  
- **Array Method** adalah function bawaan yang biasa digunakan ketika bekerja dengan array. Diantaranya:
  - ***length***: mengembalikan nilai dari jumlah panjang data suatu array.
    ``` 
    let cars = ['tesla', 'honda', 'toyota'];
    console.log(cars.length)
    
    Output: 3
    ```
  - ***push***: menambahkan item pada array dari urutan yang paling akhir.
    ```
    let cars = ['tesla', 'honda', 'toyota'];
    cars.push('hyundai')
    console.log(cars)
    
    Output: ['tesla','honda','toyota','hyundai']
    ```
  - ***pop***: mengeluarkan item index terakhir dari array.
    ``` 
    let cars = ['tesla', 'honda', 'toyota'];
    cars.pop()
    console.log(cars)
    
    Output: ['tesla','honda']
    ```
  - ***shift***: mengeluarkan item index pertama dari array.  
    ``` 
    let cars = ['tesla', 'honda', 'toyota'];
    cars.shift()
    console.log(cars)
    
    Output: ['honda','toyota']
    ```
  - ***unshift***: menambahkan item pada array dari index pertama.
    ``` 
    let cars = ['tesla', 'honda', 'toyota'];
    cars.unshift('hyundai')
    console.log(cars)
    
    Output: ['hyundai','tesla','honda','toyota',]
    ```
   - ***sort***: mengurutkan array secara ascending atau descending.
      ``` 
      const numbers = [1,3,5,2,4];
      numbers.sort();
      console.log(numbers)
      
      Output: [1,2,3,4,5]
      ```
- **Array Looping**
    - ***forEach***: method untuk melakukan looping pada setiap elemen array.
      ```
      const cars = ['tesla', 'honda', 'toyota'];

      cars.forEach(element => {
        console.log(element);
      });

      Output:
        tesla
        honda
        toyota
      ```
    - ***map***: method untuk melakukan perulangan dengan membuat variabel array baru.
      ```
      let arr = [1,2,3,4,5];
      
      let doubled = arr.map(num => {
          return num * 2;
      });
      console.log(doubled);

      Output: [ 2, 4, 6, 8, 10 ]
      ```
- **Array Multidimensi**
  - Array multidimensi adalah array yang berbentuk seperti matriks 2 dimensi **(x,y)**.
    ```
    let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
    ];
    console.log(inventory);
    ```
  - **Indexing** array multidimensi sama seperti matriks
      ```
      let inventory = [
        ['Kaos Polos' , 10],
        ['Jaket' , 5],
        ['Topi' , 12],
        ['Celana' , 4],
      ];
      console.log(inventory[1][0]);
      ```
  - **Array Method** pada array multidimensi
      ```
      let inventory = [
          ['Kaos Polos' , 10],
          ['Jaket' , 5],
          ['Topi' , 12],
          ['Celana' , 4],
      ];
      
      inventory.push(['Hoodie', 2]);
      ```
  - **Array Multidimensi Looping**
      ```
      let inventory = [
          ['Kaos Polos' , 10],
          ['Jaket' , 5],
          ['Topi' , 12],
          ['Celana' , 4],
      ];

      inventory.forEach((baris) => {
          baris.forEach((kolom) => {
              console.table(kolom);
          });
      });
      ```

## Selasa, 4 Oktober 2022

### A. Javascript Object

- **Object** adalah sebuah tipe data pada variabel yg menyimpan properti dan fungsi (method).
- Properti adalah data lengkap dari sebuah object.
- Contoh object:
    ```
    let siswa = {
        nama : 'terra',
        umur : 17,
        hobi : 'memancing',
        "nomor handphone" : 1234567
    }
    ```
- Cara mengakses object diatas:
  - Dot Notation
    ```
    console.log(siswa.nama);
    Output: terra
    ```
  - Bracket
    ```
    console.log(siswa["nama"]);
    console.log(siswa["nomor handphone"]);
    ```

- Menambahkan properti object
  ```
  let buku = {
    judul: "mantan jadi manten",
    penulis: "hayati",
    "jumlah halaman": 250
  }

  buku["penerbit"] = "Gramedia"
  ```
- Mengupdate properti object 
  ```
  let buku = {
    judul: "mantan jadi manten",
    penulis: "hayati",
    "jumlah halaman": 250
  }

  buku.penulis = "Andrea Hirata"
  ```
- Menghapus properti object
  ```
  let buku = {
    judul: "mantan jadi manten",
    penulis: "hayati",
    "jumlah halaman": 250
  }

  delete buku.penulis;
  ```

### B. Array of Object

- **Array of Object** adalah tipe data array yang berisi banyak object.
- Contoh Array of Object
  ```
  let users = [
    {
      nama: "dila",
      umur: 17,
      alamat: "bandung"
    },
    {
      nama: "auzan",
      umur: 18,
      alamat: "jakarta"
    },
    {
      nama: "dolton",
      umur: 19,
      alamat: "sulawesi"
    }
  ]
  ```
- Cara mengakses
  ```
  let data = users.map((elemen) => {
    console.log(elemen.nama)
  })
  ```
  ```
  console.log(users[0].nama)    // Output: dila
  console.log(users[2].alamat)  // Output: sulawesi
  ```

### C. Method

- **Method** adalah function yang memiliki tugas atau fungsi spesifik.
- Method termasuk action dari sebuah object. 
- Contoh method:
  ```
  const greeting = {
    welcome: function () {
      return: "halo selamat datang";
    },
    afterPay: function () {
      return "Terimakasih sudah membeli produk kami";
    }
  }

  console.log(greeting.welcome());
  console.log(greeting.afterPay());
  ```

## Rabu, 5 Oktober 2022

### A. JavaScript Modules

- **Javascript Modules** adalah cara untuk memecah kode menjadi file terpisah sehingga mempermudah untuk maintain code.
- JavaScript Modules bergantung pada pernyataan import dan export.
- Contoh javascript modules:
  - jepang.js
    ```
    export let motor = ["Suzuki", "Yamaha", "Honda", "Kawasaki"]
    ```
  - indonesia.js
    ```
    import { motor as motorJepang } from "./jepang.js"
    console.log(motorJepang)
    ```
    ```
    Output:
    ["Suzuki", "Yamaha", "Honda", "Kawasaki"]
    ```

### B. Javascript Rekursif

- **Rekursif** adalah fungsi yang memanggil dirinya sendiri sampai suatu kondisi tertentu terpenuhi.
- Ciri dari rekursif:
  - Fungsi rekursif memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. 
  - fungsi rekursif selalu memaanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.
- Contoh rekursif:
    ```
    Mencari Pangkat

    function pow(x,n) {
      if (n=1){
          return x;
      } else {
          return x * pow(x, n-1);
      }
    }
    console.log(pow(2,3))
    
    Output: 8
    ```

## Kamis, 6 Oktober 2022

### A. Asynchronous

- **Asynchronous** adalah teknik yang menyelesaikan fungsi secara paralel.
- Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Sehingga function lain dapat dikerjakan bersamaan secara paralel.
- **Callbacks** adalah suatu function namun cara pengeksekusiannya yang berbeda yaitu hanya mengeksekusi pada point tertentu.
- Contoh asynchronous:
  ```
  function p1() {
    console.log('p1 done')
  }
  
  function p2() {
    setTimeout(
      function() {
        console.log('p2 done')
      },2000
    )
  }
  
  function p3() {
    console.log('p3 done')
  }

  p1()
  p2()
  p3()
  ```
- Contoh Penggunaan Callback pada Asynchronous
  ```
  function p1() {
    console.log('p1 done')
  }

  function p2(callback) {
    setTimeout(
    function() {
      console.log('p2 done')
        callback()
      },100
    )
  }

  function p3() {
    console.log('p3 done')
  }

  p1()
  p2(p3)
  ```

- **Asynchronous - Promise** merupakan suatu object dan digunakan hanya untuk satu event dengan menyimpan hasil dari sebuah operasi asynchronous baik itu hasil yang diinginkan (resolved value) atau alasan kenapa operasi itu gagal (failure reason)
  ```
    function GetUser(id) {
    return new Promise((resolve, reject) => {
    if (id !== "" && id !== undefined) {
      reesolve (id);
    } else {
      reject ("ID Harus di Isi");
        }
    });
    }
    
    GetUser( ) 
    .then((response) => {
    console.log(response);
     })
     .catch((error) => {
    console.log(error);
    });
  ```
- **Asynchronous - Async-Await** merupakan fitur yang hadir sejak ES2017 bekerja dengan cara menunda eksekusi hingga proses asynchronous selesai
- **Asynchronous - Fetch** merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karen Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah **then** jika promise mengembalikan resolve dan **catch** jika promise mengembalikan nilai reject
  ```
    fetch("https://pokeapi.co/api/v2/pokemon/pikachu/", {
    method: "GET"
    })
     .then((response) => {
      return response.json();
    })
    .then((data) => {
     console.log(data);
     })
    .catch((error) => {
    console.log(error);
    });
  ```

## Jumat, 7 Oktober 2022

### A. DOM HTML

- ***DOM*** (Document Object Model) merupakan cara memanipulasi elemen HTML supaya website lebih dinamis dan interaktif.

- ***DOM Events*** merupakan object model yang bertugas untuk membantu interaksi user dengan document HTML. Contohnya:
  - events
  - Click
  - Scroll
  - Change
  - Focus
  - Hover
  - Submit
  - Blur
  - 
- Menangkap Interaksi User
  ```
  - Element.addEventListener("event")
  - Element.onevent
  ```

- ***EventListener***
  - EventListener berfungsi untuk membuat event (click, change, mouseout, dll) untuk keperluan manipulasi DOM.
    ```
    Element.addEventListener("event")
    ```
  - Contoh EventListener :
    - EventListener - Click 
      - HTML
        ```
        <input id="user-input"/>
        <button id="alert-button">show</button>
        ```

      - Pemanggilan element
        ```
        const input = document.getElementById("user-input")
        const button = dosument.getElementById("alert-button")
        ```

      - Pemanggilan element
        ```
        button.addEventListener("click", function()) {
          alert(input.value)
        } 
        ```