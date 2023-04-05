# Tugas Skilvul #Tech4Impact Front-End Web Development - JavaScript DOM

## Deskripsi Tugas
1. Pada artikel: https://www.javascripttutorial.net/javascript-dom/ terdapat 8 section
3. Berdasarkan artikel buatlah code yang mencakup:
    - Section 2-4: Masing Masing Minimal 3 contoh dengan 1 usecase
    - Section 4-6: Masing lasing Minimal 2 contoh dengan 1 usecase
    - Section 7-8: Masing Masing Minimal 2 contoh dengan 2 usecase
4. Tambahkan Readme Penjelasan
5. Push ke Github Masing Masing
6. Pastikan Github Repo untuk Tugas Ini Bersifat Open to Public
7. Add @ariefdfaltah as partcipant
8. Deadline Sampai Kamis, 6 April 2023
9. Pengerjaan Bersifat WAJIB

---
⠀  
Berikut merupakan implementasi dari tugas tersebut.  
⠀

## Section 2 - Selecting elements
"Selecting elements" pada JavaScript merujuk pada proses memilih atau mengambil elemen HTML dari dokumen web untuk digunakan dalam manipulasi atau perubahan pada halaman web tersebut.  

Pada dasarnya, "Selecting elements" dapat dilakukan dengan menggunakan berbagai metode dan teknik di dalam JavaScript, seperti menggunakan metode getElementById(), getElementsByTagName(), getElementsByClassName(), dan lain-lain.  
⠀
### 1. getElementById
```
<html>
	<head>
		<title>getElementById</title>
	</head>
	<body>
		<h1 id="heading">Jelang Fikri Ramadhan</h1>
		<script>
			const h1 = document.getElementById('heading');
			console.log(h1);
		</script>
	</body>
</html>
```
Terdapat satu elemen `<h1>` dengan ID `"heading"` dan satu blok script JavaScript yang menggunakan metode `getElementById()` untuk memilih elemen tersebut dan menampilkannya di console.  
⠀

### 2. getElementByTagName
```
<html>
	<head>
		<title>getElementsByTagName</title>
	</head>
	<body>
		<h1>Jelang</h1>
		<h1>Fikri</h1>
		<h1>Ramadhan</h1>

		<script>
			var paragraphs = document.getElementsByTagName("h1");

			for (var i = 0; i < paragraphs.length; i++) {
			paragraphs[i].style.color = "red";
			}
		</script>
	</body>
</html>
```
Kode tersebut adalah contoh penggunaan `getElementsByTagName` untuk mengambil semua elemen `<h1>` pada halaman web dan mengubah warna teksnya menjadi merah.

Pertama-tama, browser akan mengambil semua elemen `<h1>` pada halaman web menggunakan perintah `document.getElementsByTagName("h1")`. Kemudian, semua elemen tersebut akan disimpan dalam variabel `paragraphs`.

Setelah itu, akan dilakukan looping dengan `for` untuk setiap elemen `<h1>` yang ditemukan. Dalam setiap perulangan, properti `style.color` dari elemen tersebut akan diubah menjadi `"red"`, sehingga warna teksnya menjadi merah.

Setelah kode tersebut dijalankan, semua elemen `<h1>` pada halaman web akan berubah warna teksnya menjadi merah.  
⠀

### 3. getElementsByClassName
```
<html>
    <head>
        <title>getElementsByClassName</title>
        <style>
            .warning {
                background-color: red;
            }
        </style>
    </head>
    <body>
        <h1 class="warning">Peringatan!</h1>
        <p class="warning">Jelang Fikri Ramadhan sudah tidak JOMBLO!!!</p>

        <script>
            var elements = document.getElementsByClassName("warning");
            for (var i = 0; i < elements.length; i++) {
                elements[i].style.backgroundColor = "yellow";
            }
        </script>
    </body>
</html>
```
Terdapat sebuah tag `<h1>` dan `<p>` yang memiliki kelas `"warning"` dan background-color berwarna merah. 

Kemudian JavaScript mencari semua elemen yang memiliki kelas `"warning"` dengan menggunakan method `getElementsByClassName()` dan menyimpan hasilnya dalam variabel `elements`.

Selanjutnya, dengan menggunakan perulangan `for`, setiap elemen yang disimpan dalam variabel `elements` akan diubah style background-color nya menjadi `"yellow"`.  
⠀

---  
⠀

## Section 3 - Traversing elements
Traversing elements pada JavaScript merujuk pada proses navigasi atau penelusuran melalui struktur dokumen HTML atau DOM (Document Object Model) dengan menggunakan metode atau properti yang tersedia di dalam JavaScript.

Proses traversing dapat digunakan untuk mengakses dan memanipulasi elemen-elemen HTML atau DOM di dalam halaman web, seperti menambahkan atau menghapus elemen, mengubah nilai atribut, dan lain sebagainya.  

Beberapa metode dan properti yang sering digunakan dalam proses traversing antara lain:
1. `parentNode`  
Digunakan untuk mendapatkan elemen induk atau elemen parent dari elemen tersebut. Setiap elemen memiliki sebuah parent element yang dapat diakses menggunakan method `parentNode`.

2. `childNodes`  
Digunakan untuk mengambil elemen-elemen anak atau child nodes dari elemen tertentu di dalam dokumen HTML. Metode `childNodes` akan mengambil semua node yang termasuk dalam elemen induk, termasuk node teks dan komentar. Sementara itu, metode `children` hanya akan mengambil elemen-elemen anak yang merupakan elemen HTML yang valid. Metode `querySelectorAll` memungkinkan kita untuk menggunakan selektor CSS untuk mencari elemen anak tertentu dari sebuah elemen induk.
3. `Siblings`  
Digunakan untuk mengakses dan memanipulasi elemen-elemen HTML yang terkait dalam sebuah dokumen, seperti mengubah warna latar belakang atau mengatur nilai teks pada elemen-elemen tersebut. Siblings dapat diakses menggunakan properti `parentNode`, `nextSibling`, `previousSibling`, atau `childNodes` pada objek DOM (Document Object Model) yang mewakili elemen HTML yang ingin diakses.  
⠀
### 1. Get the Parent Element
```
<html>
    <head>
        <title>Get the Parent Element</title>
    </head>
    <body>
        <p>List :</p>
        <ul>
            <li id="myLI">Kopi</li>
            <li>Teh</li>
        </ul>
        <p>Klik tombol untuk mendapatkan node name dari parent node dari elemen li dalam daftar.</p>
        <button onclick="myFunction()">Click</button>

        <p id="demo"></p>

        <script>
            function myFunction() {
                var x = document.getElementById("myLI").parentNode.nodeName;
                document.getElementById("demo").innerHTML = x;
            }
        </script>
    </body>
</html>
```
Terdapat sebuah button element yang ketika di-click akan memanggil fungsi JavaScript `myFunction()`. Fungsi tersebut akan mendapatkan `parentNode` dari sebuah element dengan id `myLI`, yaitu sebuah `li` element, dan menampilkan nama nodenya pada sebuah paragraph element dengan id `demo`.  
⠀
### 2. Get Child Elements
```
<html>
    <head>
        <title>Get Child Elements</title>
    </head>
    <body>
        <p>List:</p>
        <ul id="myList">
            <li>Kopi</li>
            <li>Teh</li>
        </ul>
        <p>Klik untuk mendapatkan first child node dari list.</p>
        <button onclick="myFunction()">Click</button>
        
        <p id="demo"></p>

        <script>
            function myFunction() {
                var list = document.getElementById("myList").firstElementChild.innerHTML.trim();
                document.getElementById("demo").innerHTML = list;
            }
        </script>
    </body>
</html>
```
Terdapat sebuah button element yang ketika di-click akan memanggil fungsi JavaScript `myFunction()`. Fungsi ini akan mengambil elemen pertama dari daftar (list) dengan menggunakan metode `getElementById("myList")` dan `firstElementChild`.

Kemudian, konten teks dari elemen tersebut diambil dengan menggunakan properti `innerHTML`, kemudian dihapus spasi di depan dan belakang teks dengan menggunakan metode `trim()`. Setelah itu, hasil ini ditampilkan pada elemen dengan id `"demo"` menggunakan properti `innerHTML` pada elemen tersebut.  
⠀
### 3. Get Siblings Of An Element
```
<html>
    <head>
        <title>Get Siblings Of An Element</title>
    </head>
    <body>
        <p>List:</p>
        <ul id="myList">
            <li>Kopi</li>
            <li>Teh</li>
        </ul>
        <p>Klik untuk mendapatkan first child node dari list.</p>
        <button onclick="myFunction()">Click</button>
        
        <p id="demo"></p>

        <script>
            function myFunction() {
                var listItem = document.getElementById("myList").firstElementChild.nextSibling.nextSibling.innerHTML.trim();
                document.getElementById("demo").innerHTML = listItem;
            }
        </script>
    </body>
</html>
```
Terdapat sebuah button element yang ketika di-click akan memanggil fungsi JavaScript `myFunction()`. Fungsi ini akan mengambil elemen pertama dari daftar (list) dengan menggunakan metode `getElementById("myList")` dan `firstElementChild`, kemudian properti `nextSibling` yang digunakan untuk mendapatkan sibling node selanjutnya (yang merupakan elemen kedua dalam list), dan lagi `nextSibling` untuk mendapatkan sibling node selanjutnya setelahnya (yang merupakan elemen ketiga dalam list). Sehingga output yang ditampilkan adalah element kedua dalam list, yaitu Teh.  
⠀

---  
⠀
## Section 4 - Manipulating elements
Manipulating elements pada JavaScript merujuk pada kemampuan untuk memanipulasi elemen HTML di halaman web menggunakan JavaScript. Ini bisa meliputi mengubah isi dari sebuah elemen, menambahkan atau menghapus elemen, mengubah properti CSS dari sebuah elemen, atau memanipulasi posisi dari sebuah elemen di halaman.  
⠀
### 1. CreateElement
```
<html>
    <head>
        <title>CreateElement</title>
    </head>
    
    <body>
        <script>
        const newElement = document.createElement("h1");

        const text = document.createTextNode("Jelang Fikri Ramadhan");
        newElement.appendChild(text);

        document.body.appendChild(newElement);
        </script>
    </body>
</html>
```
Kode tersebut adalah contoh sederhana penggunaan JavaScript untuk membuat sebuah elemen HTML menggunakan `document.createElement()`, menambahkan teks heading ke dalam elemen menggunakan `document.createTextNode()` dan menambahkan elemen ke dalam halaman HTML menggunakan `appendChild()`.  
⠀
### 2. removeChild
```
<html>
    <head>
        <title>removeChild</title>
    </head>
    
    <body>
        <ul id="myList">
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
            <li>Item 4</li>
        </ul>

        <p>Klik 2x untuk menghapus salah satu list di atas</p>
        <button onclick="removeListItem()">Remove Item</button>
    </body>
    <script>
        function removeListItem() {
            var list = document.getElementById("myList");
            list.removeChild(list.childNodes[0]);
        }
    </script>
</html>
```
Terdapat sebuah tombol "Remove Item" yang apabila diklik akan menjalankan sebuah fungsi `removeListItem()`. Fungsi ini akan menghapus item pertama dari daftar (ul) dengan menggunakan metode `removeChild()` dari objek list yang diperoleh melalui pemanggilan document.`getElementById("myList")`.  
⠀
### 3. cloneNode
```
<html>
    <head>
        <title>cloneNode</title>
    </head>

    <body>
        <div id="original">
            <h1>Jelang Fikri Ramadhan</h1>
          </div>
          
          <button onclick="clone()">Clone</button>
          
          <div id="clone"></div>          
    <script>
        function clone() {
            var original = document.getElementById("original");
            var clone = original.cloneNode(true);
            clone.setAttribute("id", "clone");
            document.getElementById("clone").appendChild(clone);
        }
    </script>
</html>
```
Terdapat sebuah tombol "Clone" yang apabila diklik akan menjalankan sebuah fungsi `clone()`. Fungsi ini akan mencari elemen dengan id `"original"` dan kemudian menggunakan metode `cloneNode(true)` untuk membuat salinannya dengan semua elemen anaknya. Salinan kemudian diberi atribut id yang baru, `"clone"`. Akhirnya, salinan ditambahkan sebagai elemen anak dari elemen dengan id `"clone"`. Dalam hal ini, elemen asli adalah sebuah `div` yang memiliki id `"original"` dan satu elemen `h1` di dalamnya, sementara elemen salinan yang dibuat dengan menggunakan `cloneNode()` disimpan dalam `div` lain yang memiliki id `"clone"`.  
⠀

---  
⠀
## Section 5 - Working with Attributes
Attributes mengacu pada properti yang dimiliki oleh objek. Setiap objek memiliki properti dan atribut yang memungkinkan Anda untuk mengakses dan memodifikasi nilai dari objek tersebut.

Berikut adalah beberapa fungsi dan metode atribut pada JavaScript:
1. `getAttribute(name)`: Metode ini digunakan untuk mendapatkan nilai dari atribut yang disebutkan. Ini mengembalikan nilai atribut sebagai string atau null jika atribut tidak ada.
2. `setAttribute(name, value)`: Metode ini digunakan untuk menetapkan nilai untuk atribut yang disebutkan.
3. `hasAttribute(name)`: Metode ini digunakan untuk memeriksa apakah objek memiliki atribut yang disebutkan. Ini mengembalikan nilai boolean true jika objek memiliki atribut tersebut, dan false jika tidak.
4. `removeAttribute(name)`: Metode ini digunakan untuk menghapus atribut yang disebutkan dari objek.
5. `attributes`: Ini adalah properti yang digunakan untuk mengembalikan kumpulan semua atribut pada objek sebagai NamedNodeMap. Dengan menggunakan metode ini, Anda dapat mengambil daftar semua atribut pada objek dan menerapkan operasi yang berbeda pada setiap atribut.
6. `classList`: Ini adalah properti yang digunakan untuk mengakses daftar kelas CSS yang terkait dengan elemen. Ini memungkinkan Anda untuk menambahkan, menghapus, dan memeriksa kelas dengan mudah.  
⠀
### 1. setAttribute
```
<html>
    <head>
        <title>setAttribute</title>
    </head>

    <body>
        <button id="btn" onclick="changeText()">Klik Tombol</button>

        <script>
            function changeText() {
                var btn = document.getElementById("btn");
                btn.setAttribute("style", "color: red; font-weight: bold;");
                btn.innerHTML = "Tombol Sudah Berubah!";
            }
        </script>
    </body>
</html>
```
Terdapat sebuah tombol "Klik Tombol" yang akan menjalankan sebuah fungsi `changeText()`. Fungsi tersebut digunakan untuk merubah atribut dan isi elemen ketika button di klik. Lalu fungsi `changeText()` dan `document.getElementById("btn")` digunakan untuk mendapatkan elemen HTML dengan ID "btn" dan menyimpannya ke dalam variabel `'btn'`.

Kemudian, `setAttribute("style", "color: red; font-weight: bold;")` digunakan untuk menambahkan style `color: red` dan `font-weight: bold` pada button. Selanjutnya, `btn.innerHTML` digunakan untuk mengubah isi teks pada button menjadi `"Tombol Sudah Berubah!"` setelah style pada button berubah.  
⠀
### 2. getAttribute
```
<html>
    <head>
        <title>getAttribute</title>
    </head>

    <body>
        <h1 id="judul" class="warna-merah">Ini adalah judul</h1>
        <p id="paragraf">Ini adalah paragraf</p>
      
        <script>
            const judul = document.getElementById("judul");
            const idJudul = judul.getAttribute("id");
            console.log("ID Judul: " + idJudul);
        
            const classJudul = judul.getAttribute("class");
            console.log("Class Judul: " + classJudul);
        
            const paragraf = document.getElementById("paragraf");
            const idParagraf = paragraf.getAttribute("id");
            console.log("ID Paragraf: " + idParagraf);
        </script>
    </body>
</html>
```
Metode `getAttribute()` digunakan untuk mendapatkan nilai dari atribut `id` dan `class` dari elemen `h1`. Kemudian, kita juga menggunakan metode `getAttribute()` untuk mendapatkan nilai dari atribut `id` dari elemen `p`.

Setelah itu, kita mencetak nilai atribut ke dalam konsol menggunakan `console.log()`. Program ini akan mencetak nilai atribut dari elemen HTML yang dipilih ke dalam konsol.  
⠀
### 3. removeAttribute
```
<html>
    <head>
        <title>removeAttribute</title>
    </head>

    <body>
        <h1 id="judul" style="color: red;">Jelang Fikri Ramadhan</h1>
        <p>
            Klik tombol di bawah ini untuk menghapus atribut "style" dari elemen di atas.
        </p>
        <button onclick="hapusAtribut()">Hapus Atribut</button>
    
        <script>
            function hapusAtribut() {
                var judul = document.getElementById("judul");
                judul.removeAttribute("style");
            }
        </script>
    </body>
</html>
```
Program di atas memiliki satu elemen judul dengan id "judul". Elemen ini memiliki atribut "style" yang didefinisikan dalam tag `<h1>`. Ketika tombol "Hapus Atribut" ditekan, fungsi `hapusAtribut()` akan dipanggil. Fungsi ini akan mendapatkan elemen dengan id "judul" menggunakan metode `getElementById`, dan kemudian menghapus atribut "style" dari elemen tersebut menggunakan metode `removeAttribute`.

Dengan menggunakan program ini, Anda dapat memahami penggunaan metode `removeAttribute` pada JavaScript untuk menghapus atribut dari elemen HTML.  
⠀

---  
⠀
## Section 6 - Manipulating Element’s Styles
Manipulasi gaya elemen adalah proses mengubah tampilan suatu elemen pada halaman web dengan menggunakan kode JavaScript. Dalam JavaScript, Anda dapat mengakses dan memanipulasi gaya elemen dengan menggunakan properti DOM.

Beberapa contoh properti DOM yang digunakan untuk memanipulasi gaya elemen adalah sebagai berikut:
1. `style.setProperty(propertyName, value, priority)`: Metode ini digunakan untuk menetapkan nilai properti gaya tertentu pada suatu elemen. Parameter pertama adalah nama properti, parameter kedua adalah nilai properti, dan parameter ketiga (opsional) adalah prioritas properti.roperti, dan parameter kedua adalah nilai properti.
2. `getComputedStyle(element[, pseudoElt])`: Metode ini digunakan untuk mendapatkan nilai gaya yang dihitung secara komputasi dari suatu elemen. Parameter pertama adalah elemen yang akan dihitung, dan parameter kedua (opsional) adalah elemen pseudo yang akan dihitung.  
⠀
### 1. style property
```
<html>
    <head>
        <title>style property</title>
    </head>

    <body>
        <h1 id="judul">Jelang Fikri Ramadhan</h1>
        <p id="paragraf">Skilvul #Tech4Impact Kampus Merdeka Cycle 4: Front-End Web Development</p>
      
        <button onclick="ubahStyle()">Ubah Gaya</button>
      
        <script>
          function ubahStyle() {
            var elemenJudul = document.getElementById("judul");
            var elemenParagraf = document.getElementById("paragraf");
      
            elemenJudul.style.color = "blue";
            elemenParagraf.style.backgroundColor = "yellow";
            elemenParagraf.style.padding = "20px";
          }
        </script>
    </body>
</html>
```
Pada contoh di atas, saat tombol "Ubah Gaya" ditekan, fungsi `ubahStyle()` akan dipanggil. Fungsi ini akan mengambil elemen judul dan paragraf menggunakan `getElementById()`, lalu mengubah gaya elemen tersebut dengan menggunakan properti `style`. Elemen judul diubah warnanya menjadi biru, sedangkan elemen paragraf diubah warna latar belakangnya menjadi kuning dan ditambahkan padding 20 piksel.  
⠀
### 2. getComputedStyle()
```
<html>
    <head>
        <title>getComputedStyle()</title>
        <style>
            #box {
              width: 200px;
              height: 200px;
              background-color: blue;
            }
          </style>
    </head>

    <body>
        <div id="box"></div>

        <script>
          var elemenBox = document.getElementById("box");
          var styleBox = window.getComputedStyle(elemenBox);
          var lebarBox = styleBox.getPropertyValue("width");
          var tinggiBox = styleBox.getPropertyValue("height");
          var warnaBox = styleBox.getPropertyValue("background-color");
      
          alert("Lebar kotak: " + lebarBox);
          alert("Tinggi kotak: " + tinggiBox);
          alert("Warna kotak: " + warnaBox);
        </script>
    </body>
</html>
```
Pada contoh di atas, sebuah kotak dengan id "box" dibuat menggunakan CSS. Kemudian, menggunakan JavaScript, elemen "box" diambil menggunakan `document.getElementById()`. Metode `getComputedStyle()` digunakan untuk mendapatkan nilai gaya yang dihitung secara komputasi dari elemen "box". Setelah itu, nilai-nilai properti "width", "height", dan "background-color" diambil dari objek gaya yang dikembalikan oleh `getComputedStyle()`, dan ditampilkan dalam pesan alert.

Program di atas akan menampilkan tiga pesan alert dengan informasi tentang lebar, tinggi, dan warna kotak.  
⠀

---  
⠀
## Section 7 - Working with Events  
⠀
### A. Page Load Events
Page Load Events pada JavaScript adalah serangkaian acara atau event yang terjadi ketika sebuah halaman web atau dokumen HTML telah dimuat sepenuhnya di browser. Event ini terjadi secara otomatis pada saat browser menyelesaikan rendering seluruh elemen HTML, CSS, dan JavaScript yang dibutuhkan untuk menampilkan halaman web.

Berikut adalah beberapa contoh dari Page Load Events pada JavaScript:
1. `onload`: Event ini terjadi ketika seluruh dokumen HTML telah selesai dimuat, termasuk gambar, script, dan elemen lainnya.
2. `onbeforeunload`: Event ini terjadi ketika pengguna akan meninggalkan halaman web. Hal ini dapat digunakan untuk meminta konfirmasi dari pengguna sebelum meninggalkan halaman.
3. `onunload`: Event ini terjadi ketika pengguna telah meninggalkan halaman web sepenuhnya.
4. `DOMContentLoaded`: Event ini terjadi ketika DOM (Document Object Model) telah selesai dimuat, tanpa harus menunggu gambar atau file eksternal lainnya.
5. `onerror`: Event ini terjadi ketika terjadi kesalahan saat memuat dokumen atau elemen halaman web, seperti gambar atau script.  
⠀

### 1. Use Case Pertama - Meminta konfirmasi sebelum keluar dari halaman web
```
<html>
    <head>
        <title>beforeunload1</title>
    </head>

    <body>
        <h1>Selamat datang di dunia tak selamanya indah :)</h1>
        <p>Jika anda mereload page ini, akan muncul notifikasi peringatan untuk konfirmasi.</p>
        
        <script>
            window.addEventListener('beforeunload', function (event) {
                event.preventDefault();
                event.returnValue = '';
            });
        </script>
    </body>
</html>
```
Ketika pengguna mencoba untuk meninggalkan halaman ini, `pesan konfirmasi` akan muncul untuk meminta pengguna untuk mengonfirmasi tindakan mereka. Jika pengguna memilih untuk tetap di halaman ini, halaman akan tetap ditampilkan. Jika pengguna memilih untuk keluar dari halaman ini, pengguna akan diarahkan ke halaman baru.  
⠀
### 2. Use Case Kedua - Menyimpan data yang belum disimpan sebelum keluar dari halaman web
```
<html>
    <head>
        <title>beforeunload2</title>
    </head>
    <body>
        <h1>Login</h1>
        <form>
            <label for="username">Username:</label>
            <input type="text" id="username" name="username"><br><br>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password"><br><br>
            <button type="submit">Masuk</button>
        </form>
        
        <script>
            window.addEventListener('beforeunload', function (event) {
                event.preventDefault();
                if (document.getElementById('username').value || document.getElementById('password').value) {
                    event.returnValue = 'Data yang belum disimpan akan hilang. Apakah Anda yakin ingin keluar dari halaman ini?';
                }
            });
        </script>
    </body>
</html>
```
Ketika pengguna mencoba untuk meninggalkan halaman ini dan ada data yang belum disimpan pada form login, `pesan konfirmasi` akan muncul untuk meminta pengguna untuk mengonfirmasi tindakan mereka. Jika pengguna memilih untuk tetap di halaman ini, halaman akan tetap ditampilkan dan pengguna dapat menyimpan data mereka terlebih dahulu. Jika pengguna memilih untuk keluar dari halaman ini, pengguna akan diarahkan ke halaman baru.  
⠀
### B. Mouse Events
Mouse Events pada JavaScript adalah tindakan atau peristiwa yang terjadi ketika pengguna melakukan interaksi dengan mouse di dalam sebuah halaman web. Beberapa contoh dari Mouse Events antara lain:
1. `click` : terjadi ketika pengguna menekan tombol mouse satu kali
2. `double click` : terjadi ketika pengguna menekan tombol mouse dua kali secara cepat
3. `mouseover` : terjadi ketika pointer mouse memasuki area yang ditentukan (biasanya sebuah elemen HTML)
4. `mouseout` : terjadi ketika pointer mouse keluar dari area yang ditentukan
5. `mousedown` : terjadi ketika tombol mouse ditekan dan ditahan
6. `mouseup` : terjadi ketika tombol mouse dilepas setelah ditekan
7. `mousemove` : terjadi ketika pointer mouse bergerak di dalam area yang ditentukan

Ketika sebuah Mouse Event terjadi, JavaScript dapat menangani event tersebut dan mengeksekusi kode yang sesuai dengan aksi yang dilakukan oleh pengguna. Contohnya, jika pengguna mengklik sebuah tombol, maka kode JavaScript dapat dijalankan untuk mengambil tindakan yang sesuai dengan klik tersebut, seperti memunculkan pop-up atau mengubah tampilan halaman web.  
⠀
### 1. Usecase Pertama - Mengubah warna background saat pointer mouse berada di atas elemen
```
<html>
    <head>
        <title>Mouse Events</title>
    </head>

    <body>
        <button id="tombol">Klik di sini!</button>

        <script>
            var tombol = document.getElementById("tombol");

        tombol.addEventListener("mouseover", function() {
            tombol.style.backgroundColor = "red";
        });

        tombol.addEventListener("mouseout", function() {
            tombol.style.backgroundColor = "";
        });
        </script>
    </body>
</html>
```
Ketika pengguna mengarahkan pointer mouse ke sebuah tombol, maka warna background tombol akan berubah untuk memberikan feedback visual yang jelas bahwa tombol tersebut sedang dalam keadaan aktif.  
⠀
### 2. Usecase Kedua - Mengubah nilai teks pada sebuah elemen saat tombol mouse ditekan
```
<html>
    <head>
        <title>Mouse Events</title>
    </head>

    <body>
        <img id="gambar" src="https://github.com/jelangfr13/PersonalWebsite/blob/main/assets/UpCycle.png?raw=true" alt="Gambar" style="max-width: 500px;">
        <p id="keterangan">Klik dan tahan pada gambar untuk melihat interaksi</p>

        <script>
        var gambar = document.getElementById("gambar");
        var keterangan = document.getElementById("keterangan");

        gambar.addEventListener("mousedown", function() {
            keterangan.innerHTML = "Ini adalah gambar banner UpCycle";
        });

        gambar.addEventListener("mouseup", function() {
            keterangan.innerHTML = "Klik dan tahan pada gambar untuk melihat interaksi";
        });
        </script>
    </body>
</html>
```
Ketika pengguna menekan tombol mouse pada sebuah gambar, maka teks pada halaman web akan berubah untuk memberikan keterangan atau informasi tambahan mengenai gambar tersebut.  
⠀

---  
⠀
## Section 8 - Scripting Web Forms
Scripting Web Forms pada JavaScript adalah proses menambahkan interaktivitas pada formulir (form) HTML dengan menggunakan JavaScript. Scripting ini memungkinkan pengembang web untuk mengontrol, memvalidasi, dan mengubah nilai formulir secara dinamis saat pengguna memasukkan atau mengirimkan data melalui formulir.  
⠀
### A. Checkbox
Checkbox adalah salah satu jenis input form pada HTML yang memungkinkan pengguna untuk memilih satu atau lebih opsi dari beberapa opsi yang tersedia. Checkbox biasanya digunakan dalam bentuk formulir untuk memungkinkan pengguna untuk memilih preferensi mereka.  
⠀
### 1. Usecase Pertama - Menggunakan Checkbox untuk Mengaktifkan/Menonaktifkan Fitur
```
<html>
    <head>
        <title>Checkbox</title>
    </head>
    
    <body>
        <label for="feature">Aktifkan Fitur:</label>
        <input type="checkbox" id="feature" name="feature" onclick="toggleFeature()">

        <script>
            function toggleFeature() {
            var feature = document.getElementById("feature");
                if (feature.checked == true) {
                    console.log("Fitur Sudah Aktif")
                } else {
                    console.log("Fitur Sudah Nonaktif")
                }
            }
        </script>
    </body>
</html>
```
Dalam sebuah aplikasi web, terdapat sebuah fitur yang dapat diaktifkan atau dinonaktifkan dengan menggunakan sebuah Checkbox. Ketika Checkbox di ceklis, maka fitur tersebut diaktifkan, dan ketika Checkbox tidak dicentang, fitur tersebut dinonaktifkan.  
⠀
### 2. Usecase Kedua - Menggunakan Checkbox untuk Memilih Banyak Item
```
<html>
    <head>
        <title>Checkbox</title>
    </head>
    
    <body>
        <ul>
            <li>
              <input type="checkbox" id="item1" name="item1">
              <label for="item1">Item 1</label>
            </li>
            <li>
              <input type="checkbox" id="item2" name="item2">
              <label for="item2">Item 2</label>
            </li>
            <li>
              <input type="checkbox" id="item3" name="item3">
              <label for="item3">Item 3</label>
            </li>
          </ul>
          
          <script>
          var items = document.querySelectorAll("input[type='checkbox']");
          for (var i = 0; i < items.length; i++) {
            items[i].addEventListener("click", function() {
              if (this.checked == true) {
                // kode untuk menambahkan item yang dipilih
              } else {
                // kode untuk menghapus item yang dipilih
              }
            });
          }
          </script>          
    </body>
</html>
```
Dalam sebuah daftar item, pengguna dapat memilih banyak item sekaligus dengan menggunakan Checkbox. Ketika Checkbox di ceklis, maka item tersebut dipilih, dan ketika Checkbox tidak dicentang, item tersebut tidak dipilih.

Fungsi `addEventListener` digunakan untuk menambahkan event listener ke masing-masing Checkbox, sehingga program dapat menangani aksi pengguna ketika Checkbox diklik dan mengambil tindakan yang sesuai.  
⠀
### B. Radio Button
Radio button merupakan salah satu jenis elemen input pada form HTML yang dapat digunakan untuk memilih satu nilai dari beberapa pilihan yang tersedia. Radio button biasanya digunakan dalam situasi di mana pengguna hanya dapat memilih satu opsi dari beberapa pilihan yang disediakan.  
⠀
### 1. Usecase Pertama - Menampilkan Jenis Kelamin yang Dipilih Pengguna Pada Alert Notification Ketika Tombol Diklik
```
<html>
    <head>
        <title>Radio Button</title>
    </head>

    <body>
        <h2>Pilih Jenis Kelamin:</h2>
        <input type="radio" name="gender" value="laki-laki">Laki-laki<br>
        <input type="radio" name="gender" value="perempuan">Perempuan<br>
        <input type="button" value="Submit" onclick="displayValue()">

        <script>
            function displayValue() {
                let radioButtons = document.getElementsByName("gender");
                let selectedValue = "";
    
                for (let i = 0; i < radioButtons.length; i++) {
                    if (radioButtons[i].checked) {
                        selectedValue = radioButtons[i].value;
                        break;
                    }
                }
    
                alert("Jenis kelamin yang dipilih adalah: " + selectedValue);
            }
        </script>
    </body>
</html>
```
Radio button digunakan untuk memilih jenis kelamin dari pengguna dan nilai yang dipilih akan ditampilkan dalam sebuah alert box saat tombol "Submit" diklik.  
⠀
### 2. Usecase Kedua - Menampilkan Jumlah Nilai Paket Langganan yang Dipilih Pengguna Pada Alert Notification Ketika Tombol Diklik
```
<html>
    <head>
        <title>Radio Button</title>
    </head>

    <body>
        <h2>Pilih Paket Langganan:</h2>
        <input type="radio" name="subscription" value="100000">Paket Silver (Rp100,000/bulan)<br>
        <input type="radio" name="subscription" value="150000">Paket Gold (Rp150,000/bulan)<br>
        <input type="radio" name="subscription" value="200000">Paket Platinum (Rp200,000/bulan)<br>
        <input type="button" value="Hitung" onclick="calculateTotal()"><br>
        <span id="total"></span>

        <script>
            function calculateTotal() {
                let radioButtons = document.getElementsByName("subscription");
                let selectedValue = 0;
    
                for (let i = 0; i < radioButtons.length; i++) {
                    if (radioButtons[i].checked) {
                        selectedValue = parseInt(radioButtons[i].value);
                        break;
                    }
                }
    
                let total = selectedValue * 12;
                document.getElementById("total").innerHTML = "Total biaya (12 Bulan): Rp" + total;
            }
        </script>
    </body>
</html>
```
Radio button digunakan untuk memilih paket langganan dan total biaya akan dihitung berdasarkan paket yang dipilih dan ditampilkan di halaman web.