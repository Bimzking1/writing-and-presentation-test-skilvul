- Paulus Bimo Satrio Aji
- Politeknik Elektronika Negeri Surabaya
- Frontend Web Development
- FEBE-32 and FE-8
---

# Writing and Presentation Test Week 2

## Senin-Selasa, 26-27 September 2022

### A. Javascript Looping

### Looping

- ***Looping*** merupakan statement yang mengulang suatu perintah hingga kondisi terpenuhi atau ada perintah untuk **stop**.

- Looping *<strong>For*</strong>
  - Digunakan saat tahu jumlah perulangan dan kapan harus berhenti.
    - Code
      ```
      for (let i = 0; i < 3; i++) {
        console.log('Hello World');
      }
      ```
    - Output
      ```
      Hello World
      Hello World
      Hello World
      ```

- Looping *<strong>While*</strong>
  - Digunakan saat tidak tahu jumlah perulangan tetapi tahu kapan harus berhenti. Pengecekan dilakukan di awal.
    - Code
      ```
      let maxWord = 0 ;

      while (maxWord < 3) {
          console.log('Hello World ke-', maxWord);
          maxWord ++ ;
      }
      ```
    - Output
      ```
      Hello World ke- 0
      Hello World ke- 1
      Hello World ke- 2
      ```

- Looping *<strong>Do While*</strong>
  - Digunakan saat tidak tahu jumlah perulangan tetapi tahu kapan harus berhenti. Pengecekan dilakukan di akhir.
    - Code
      ```
      let maxWord = 0 ;
      
      do {
          console.log('Hello World ke-', maxWord);
          maxWord ++ ;
      } while (maxWord <= 3)
      ```
    - Output
      ```
      Hello World ke- 0
      Hello World ke- 1
      Hello World ke- 2
      ```

- Looping *<strong>Nested*</strong>
  - Digunakan jika ingin membuat perulangan di dalam perulangan. Biasa digunakan dalam matrix.
    - Code
      ```
      for (let i = 0; i < 3; i++) {
          for (let j = 0; j < 3; j++) {
              console.log('i:', i, 'dan j:', j);
          }
      }
      ```
    - Output
      ```
      i: 0 dan j: 0
      i: 0 dan j: 1
      i: 0 dan j: 2
      i: 1 dan j: 0
      i: 1 dan j: 1
      i: 1 dan j: 2
      i: 2 dan j: 0
      i: 2 dan j: 1
      i: 2 dan j: 2
      ```

### B. Scope dan Function
- **Scope** merupakan konsep dalam flow data variabel. 
Menentukan suatu variabel apakah bisa diakses pada scope atau tidak.
  - Scope ada 2 macam, yaitu:
      ```
      let name = "Bimo" ; 
      function sayHello()
          let surName = "Paul"
          return name;
      {
      console.log(name);
      ```
    - Global scope: variabel *name* berada di global scope.
    - Local scope: variabel *surName* berada di local scope.

- **Function** merupakan blok dalam sebuah grup yang berfungsi untuk menyelesaikan 1 task.
  - Cara membuat function:
    ```
    function sayHello()
        console.log('Hello World')
    {
    ```
  - Cara memanggil function:
    ```
    sayHello()
    console.log(sayHello()); 
    ```
- **Argumen dan Parameter**
  - Argumen adalah nilai yang digunakan saat memanggil function. Jumlah argumen harus sama dengan jumlah parameternya. <br />
  - Parameter berfungsi untuk menerima sebuah inputan data yang digunakan untuk melakukan task. <br />
  - Contoh:
    ```
    function penjumlahan(a,b){
      return a + b;
    }
    penjumlahan(5,5)
    ```
    ***5,5*** adalah argumen dan ***(a,b)*** adalah parameter.

- **Arrow Function** merupakan cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6.
- Contoh arrow function:
    ```
    const penjumlahan = (a,b) => {
        return a + b;
    }
    ```

## Rabu-Jumat, 28-30 September 2022

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

- Cara memanggil DOM Value ada beberapa macam:
  - Memanggil tag HTML berdasarkan ID
    ```
    console.log(document.getElementByID("header"))
    ```
  - Memanggil tag HTML berdasarkan Class Name
    ```
    console.log(document.getElementByClassName("text-color-red"))
    ```
  - Memanggil tag html dengan Query Selector
    ```
    console.log(document.querySelector("#footer"))
    console.log(document.querySelector(".text-color-red"))
    ```
- Memanipulasi content
  - Deklarasi varible header sebagai wadah untuk menyimpan tag HTML
    ```
    let header = document.getElementById("header");
    ```
  - Memanipulasi Content pada Header Content dari pemilik element dengan ID Header dengan text.Content
    ```
    document.getElementById("header").textContent = "Teks Heading"
    ```

- Memanipulasi Content didalam sebuah element dengan .innerHTML
  ```
  <ul id= "list"></ul>

  document.getElementById("list").innerHTML = "<li> item1 </li> <li> item2 </li>"
  ```
- Membuat Element HTML
  ```
  <div id ="header"></div>

  const heading = document.createElement("h1)
  heading.textContent = "Ini Heading"

  document.getElemntByID("header").appendChild(heading)
  ```

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
    - EventListener - Blur
      - Event dimana sebuah element kehilangan fokus dari user 
      - Contoh: <br/>
        Validasi isi dari ``<input id = "username" />`` agar panjangnya minimal 6 karakter

        ```
        const input = document.getElementById("username")
        ```

        ```
        input.addEventListener("blur", () => {
          if(input.value.length < 6) alert("Panjang username minimal 6")
        })
        ```

    - EventListener - Form Submission
      - Contoh: <br/>
        ```
        <input name="email"/>
        ```
        ```
        <input type="password" name="password"/>
        ```
        Untuk mendapatkan isi dari kedua inputan tersebut terdapat 2 cara:
          - Memasang event listener di kedua input dan tombol submit, lalu saat tombol diklik, baca value dari kedua input tersebut
          - Memasang event listener di form, lalu gunakan FormData untuk menggambil data dari masing-masing input
        
            ``` 
            const form = document.getElementById("form")

            form.addEventListener("submit", function(event)){
                event.preventDefault()

                const formData = new FormData(form)
                const values = Object.fromEntries(formData) {
                    email: ....
                }
            })
            ```



                
 



