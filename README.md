
# Lab5Web - Praktikum JavaScript

#### Nama = Dzaki Arif Rahman
#### Kelas = TI.24.A4
#### NIM = 312410312
#### Matkul = Pemograman Web 

-----
# Tugas

<img width="954" height="335" alt="image" src="https://github.com/user-attachments/assets/399d0168-5f41-4719-8ff4-8191ed5590f1" />

## Belajar Memprogram Web dengan JavaScript

Pada Praktikum 5 ini, saya mempelajari **JavaScript (nama resminya adalah ECMAScript** yang berperan memprogram perilaku halaman web. Kode JavaScript disisipkan di antara tag `<script>` dan dapat diletakkan di `<head>`, `<body>`, atau pada file eksternal.Saya mempelajari bagaimana JavaScript dapat mengubah konten HTML, atribut, gaya (CSS), serta menyembunyikan atau menampilkan elemen

### Persiapan Dokumen HTML (`lab5_javascript.html`)

## 1. Persiapan Dokumen HTML dan Metode Output

### Deskripsi
Bagian ini bertujuan untuk memahami cara kerja dasar JavaScript dalam menampilkan data.  
JavaScript dapat menulis output ke beberapa tempat, di antaranya langsung ke halaman HTML, ke konsol browser, ke elemen HTML tertentu, atau melalui popup pesan.

### Kode Program
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Mengenal JavaScript</title>
</head>
<body>
    <h1>Pengenalan JavaScript</h1>
    <h3>Contoh document.write dan console.log</h3>
    <script>
        document.write("Hello World");
        console.log("Hello World");
    </script>
</body>
</html>
````

### Penjelasan

1. **`document.write()`** digunakan untuk menulis teks langsung ke halaman web.
   Metode ini cocok untuk pembelajaran dasar, namun tidak disarankan digunakan setelah halaman selesai dimuat karena dapat mengganti seluruh isi dokumen.
2. **`console.log()`** digunakan untuk menampilkan teks di konsol browser.
   Biasanya digunakan untuk debugging karena tidak mengubah tampilan halaman.
3. Kode JavaScript dapat diletakkan di dalam tag `<script>` baik di dalam `<head>` maupun `<body>`.

### Screenshot

<img width="1581" height="823" alt="image" src="https://github.com/user-attachments/assets/cb57bf6b-9d56-4faf-9d89-180dea21d53f" />


---

## 2. JavaScript Dasar: Interaksi, Method, dan Fungsi

### Deskripsi

Bagian ini menjelaskan penggunaan **method bawaan JavaScript** untuk berinteraksi dengan pengguna secara langsung, yaitu `alert()` dan `prompt()`, serta implementasi **fungsi** yang dipicu oleh *event* **`onload`**.


### Kode Program

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Interaksi JavaScript</title>
    <script>
        function pesan(){
            // Alert 1: Dipanggil saat body selesai dimuat
            alert("Memanggil JavaScript lewat body onload");
        }
    </script>
</head>

<body onload="pesan()">
    <h2>Interaksi JavaScript</h2>
    <script>
        // Alert 2: Dijalankan langsung saat script di body di-parse
        window.alert("Ini merupakan pesan untuk anda");
        
        // Prompt: Meminta input dari user
        var nama = prompt("Siapa nama anda?", "Masukkan nama anda");

        // Cek jika pengguna menekan Cancel (null) atau tidak mengisi apa pun ("")
        if (nama == null || nama.trim() === "") {
            // document.write menimpa seluruh konten halaman setelah loading
            document.write("Hai, Pengunjung tanpa nama!");
        } else {
            // document.write menimpa seluruh konten halaman setelah loading
            document.write("Hai, " + nama);
        }
    </script>
</body>
</html>
```

-----

### Penjelasan

Program ini mengeksekusi tiga interaksi *pop-up* secara berurutan dan kemudian menampilkan hasil akhirnya di layar:

1.  **Fungsi `pesan()` dan *Event* `onload`:**

      * Fungsi `pesan()` didefinisikan di bagian `<head>` (Baris 6-8).
      * Fungsinya dipanggil otomatis segera setelah semua konten `<body>` selesai dimuat (sebuah *event* bernama **`load`**) melalui atribut **`onload="pesan()"`** pada tag `<body>` (Baris 12).
      * Interaksi pertama yang muncul adalah **Alert** dengan pesan: `"Memanggil JavaScript lewat body onload"`.

2.  **Dua *Pop-up* di *Body***

      * Setelah *Alert* pertama ditutup, skrip di dalam `<body>` akan dieksekusi secara berurutan.
      * **`window.alert()`** (Baris 15) akan menampilkan *Alert* kedua.
      * **`prompt()`** (Baris 16) akan muncul setelah *Alert* kedua ditutup, berfungsi sebagai **kotak *input* pop-up** tempat pengguna dapat mengetik nama.

3.  **Logika Kondisional dan Penulisan Output:**

      * Program menggunakan kondisi **`if (nama == null || nama.trim() === "")`** untuk mengecek hasil dari `prompt()`:
          * Jika pengguna menekan **Cancel**, `prompt()` mengembalikan nilai **`null`**.
          * Jika pengguna meninggalkan *input* kosong, nilai `nama` adalah `""`.
      * Jika kondisi ini terpenuhi (`null` atau kosong), program menampilkan pesan *default* **"Hai, Pengunjung tanpa nama\!"**.
      * **Penting:** Penggunaan **`document.write()`** (Baris 20/23) di sini akan **menghapus semua konten HTML** yang sudah dimuat (termasuk judul `<h2>` dan hasil *Alert*) dan menggantinya dengan teks hasil, karena fungsi ini dieksekusi setelah halaman selesai di-*parse*.

-----

### Screenshot

<img width="1567" height="881" alt="Screenshot 2025-10-24 225254" src="https://github.com/user-attachments/assets/7ac38dae-a5b2-4a80-8a94-09a4239afa94" />


---

## 3. Dasar Pemrograman: Logika dan Operasi

### Deskripsi

Materi ini membahas operasi aritmatika, struktur kontrol `if..else`, dan `switch`.
Ketiganya merupakan bagian penting dalam membuat logika program di JavaScript.

### Kode Program 1 – Operasi Aritmatika

```javascript
function test(val1, val2) {
    document.write("Perkalian: " + (val1 * val2) + "<br>");
    document.write("Modulus: " + (val1 % val2) + "<br>");
}
```

### Kode Program 2 – Struktur Kondisi

```javascript
var nilai = 85;
if (nilai >= 60) {
    hasil = "Lulus";
} else {
    hasil = "Tidak Lulus";
}
document.write("Status: " + hasil);
```

### Kode Program 3 – Struktur Switch

```javascript
var grade = "B";
switch (grade) {
    case "A": document.write("Sangat Baik"); break;
    case "B": document.write("Baik"); break;
    case "C": document.write("Cukup"); break;
    default: document.write("Tidak Diketahui");
}
```

### Penjelasan

1. **Operator aritmatika** seperti `+`, `-`, `*`, `/`, `%` digunakan untuk melakukan perhitungan matematis.
   Operator `%` (modulus) mengembalikan sisa hasil bagi, sering digunakan untuk menentukan bilangan ganjil atau genap.
2. **Struktur `if..else`** memungkinkan pengambilan keputusan berdasarkan kondisi tertentu.
3. **`switch`** digunakan untuk menggantikan banyak `if..else` ketika ada banyak nilai yang harus dibandingkan.
   Setiap `case` diakhiri dengan `break` untuk menghentikan eksekusi.

### Screenshot

<img width="1535" height="934" alt="image" src="https://github.com/user-attachments/assets/d0a8466d-1786-4587-a26e-ab9f3ca7dfac" />


---

## 4. Form dan Manipulasi Objek Document

### Deskripsi

Bagian ini menjelaskan cara mengakses elemen HTML melalui objek `document`, memproses input form, serta memodifikasi tampilan halaman.

### Kode Program 1 – Cek Ganjil atau Genap

```javascript
function test() {
    var val1 = document.kirim.T1.value;
    if (val1 % 2 == 0)
        document.kirim.T2.value = "Bilangan Genap";
    else
        document.kirim.T2.value = "Bilangan Ganjil";
}
```

### Kode Program 2 – Manipulasi Warna Halaman

```javascript
function ubahWarna() {
    document.bgColor = "lightblue";
    document.fgColor = "darkblue";
    document.write("Terakhir diubah: " + document.lastModified);
}
```

### Penjelasan

1. Objek `document` merepresentasikan seluruh halaman HTML yang sedang aktif.
2. **`document.kirim.T1.value`** mengambil nilai dari elemen input dengan nama `T1` dalam form bernama `kirim`.
3. Logika `if (val1 % 2 == 0)` digunakan untuk menentukan apakah bilangan yang dimasukkan adalah genap atau ganjil.
4. **`bgColor`** dan **`fgColor`** digunakan untuk mengubah warna latar dan teks halaman.
5. **`document.lastModified`** menampilkan informasi waktu terakhir file HTML tersebut diubah.

### Screenshot

<img width="1381" height="874" alt="image" src="https://github.com/user-attachments/assets/3a41b838-6730-4204-9f84-30931c475a71" />


---

## 5. HTML DOM: CheckBox dengan Perhitungan Otomatis

### Deskripsi

Bagian ini memperkenalkan penggunaan **HTML DOM (Document Object Model)** untuk memanipulasi elemen halaman secara dinamis.
Contohnya digunakan pada perhitungan otomatis menggunakan checkbox.

### Kode Program

```javascript
function hitung(ele) {
    var total = document.getElementById('total').value;
    total = (total ? parseInt(total) : 0);
    var harga = ele.value;

    if (ele.checked)
        total += parseInt(harga);
    else
        total -= parseInt(harga);

    document.getElementById('total').value = total;
}
```

### Penjelasan

1. **`getElementById()`** digunakan untuk mengambil elemen HTML berdasarkan nilai atribut `id`.
2. Nilai yang diambil dari elemen input bertipe checkbox dikonversi ke angka menggunakan **`parseInt()`**.
3. Jika checkbox dicentang (`ele.checked == true`), nilainya ditambahkan ke total.
   Jika tidak, nilainya dikurangi.
4. Nilai akhir ditampilkan pada elemen input lain dengan `id="total"`.
   Proses ini berjalan otomatis setiap kali pengguna mencentang atau menghapus tanda centang pada checkbox.

### Screenshot

<img width="1429" height="817" alt="image" src="https://github.com/user-attachments/assets/35700ae8-6845-4f3b-b71d-ffe918b5da39" />


---

# Tugas Validasi Form

### Deskripsi

Bagian ini menjelaskan cara menggunakan JavaScript untuk melakukan **validasi formulir sisi klien (client-side validation)**. Tujuannya adalah untuk mencegah formulir dikirimkan jika bidang penting (wajib diisi) kosong.

saya akan menggunakan *event handler* **`onsubmit`** pada elemen `<form>` dan fungsi JavaScript untuk memeriksa nilai *input*.

-----

### Kode Program

Dalam contoh ini, kita membuat formulir sederhana dengan satu bidang *input* wajib.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Validasi Formulir</title>
    <style>
        .error { color: red; }
    </style>
    <script>
        function validasiForm() {
            // 1. Ambil nilai dari elemen input
            var nama = document.getElementById("namaInput").value;
            var pesanError = document.getElementById("errorPesan");

            // 2. Cek apakah bidang nama kosong
            if (nama.trim() === "") {
                // Tampilkan pesan error
                pesanError.innerHTML = "Nama harus diisi!";
                
                // Kembalikan false untuk MENCEGAH formulir dikirim
                return false; 
            } else {
                // Hapus pesan error jika valid
                pesanError.innerHTML = "";
                
                // Kembalikan true untuk MENGIZINKAN formulir dikirim
                alert("Formulir berhasil divalidasi dan akan dikirim!");
                return true;
            }
        }
    </script>
</head>
<body>
    <h2>Formulir Validasi</h2>
    
    <form onsubmit="return validasiForm()" action="/submit-data" method="post">
        
        <label for="namaInput">Nama Wajib Diisi:</label>
        <input type="text" id="namaInput" name="nama_user">
        
        <p id="errorPesan" class="error"></p>
        
        <button type="submit">Kirim Formulir</button>
    </form>
</body>
</html>
```

-----

### Penjelasan

1.  ***Event Handler* `onsubmit`:**

      * Atribut **`onsubmit="return validasiForm()"`** diletakkan pada tag `<form>`. Ini berarti bahwa setiap kali tombol *submit* diklik, fungsi **`validasiForm()`** akan dijalankan *sebelum* formulir benar-benar dikirim ke server.
      * Nilai *return* (yaitu `true` atau `false`) dari fungsi `validasiForm()` menentukan tindakan selanjutnya:
          * Jika mengembalikan **`false`**, proses pengiriman formulir akan **dibatalkan**.
          * Jika mengembalikan **`true`**, proses pengiriman formulir akan **dilanjutkan**.

2.  **Mengambil Nilai *Input***:

      * Di dalam fungsi `validasiForm()`, kita menggunakan **`document.getElementById("namaInput").value`** untuk mendapatkan teks yang diketik pengguna di dalam kotak *input*.

3.  **Validasi (*Trim* dan Cek Kosong):**

      * Kondisi **`if (nama.trim() === "")`** adalah inti dari validasi.
          * Metode **`.trim()`** digunakan untuk menghapus spasi kosong di awal atau akhir teks.
          * Jika setelah spasi dihapus, nilai *input* sama dengan string kosong (`""`), maka bidang dianggap **kosong** dan tidak valid.

4.  **Menampilkan Pesan *Error*:**

      * Jika validasi gagal (bidang kosong), kita menggunakan **`document.getElementById("errorPesan").innerHTML = "..."`** untuk menyisipkan teks kesalahan di bawah *input* tanpa menimpa seluruh halaman.

5.  **Mengontrol Pengiriman Formulir:**

      * Jika validasi **gagal**, fungsi mengembalikan **`return false;`** (Baris 20), yang menghentikan pengiriman formulir.
      * Jika validasi **berhasil**, fungsi mengembalikan **`return true;`** (Baris 25), yang memungkinkan formulir dikirim (disertai *alert* pemberitahuan).

-----

### Screenshot
<img width="1449" height="830" alt="image" src="https://github.com/user-attachments/assets/5303eeca-1dc1-4b3c-a881-6ff16422c56a" />


----
## Kesimpulan


Praktikum 5 ini memberikan pemahaman komprehensif mengenai peran **JavaScript (ECMAScript)** sebagai bahasa pemrograman sisi klien yang mengendalikan perilaku halaman web. Pembelajaran dimulai dengan metode *output* dasar seperti **`document.write()`** untuk menampilkan konten langsung ke HTML dan **`console.log()`** untuk *debugging*. Konsep interaksi pengguna diterapkan melalui fungsi bawaan **`alert()`** dan **`prompt()`**, yang memunculkan *pop-up* dan meminta *input* dari pengguna. Selain itu, praktik ini menekankan pentingnya **fungsi** dan **event handler** seperti **`onload`** dan **`onsubmit`**, yang memungkinkan kode JavaScript bereaksi terhadap peristiwa tertentu pada halaman. Pemahaman berlanjut ke **Dasar Pemrograman**, mencakup operasi aritmatika, struktur kontrol **`if...else`**, dan **`switch`** untuk pengambilan keputusan logis. Akhirnya, pengenalan **HTML DOM (Document Object Model)** dan penerapannya pada **validasi formulir** menunjukkan kemampuan JavaScript dalam **memanipulasi elemen HTML secara dinamis** (misalnya, mengambil nilai *input* dan mencegah pengiriman formulir jika data kosong), serta membuat fitur interaktif seperti perhitungan otomatis menggunakan *checkbox*. Secara keseluruhan, praktik ini menunjukkan bahwa JavaScript adalah fondasi penting untuk menciptakan halaman web yang dinamis, interaktif, dan valid.
