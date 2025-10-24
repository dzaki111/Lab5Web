
# Lab5Web - Praktikum JavaScript

#### Nama = Dzaki Arif Rahman
#### Kelas = TI.24.A4
#### NIM = 312410312
#### Matkul = Pemograman Web 

-----

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

![Screenshot](img/ss1.png)

---

## 2. JavaScript Dasar: Interaksi, Method, dan Fungsi

### Deskripsi

Bagian ini menjelaskan penggunaan method bawaan JavaScript seperti `alert()`, `prompt()`, dan implementasi fungsi yang dijalankan melalui event `onload`.

### Kode Program

```html
<script>
    window.alert("Ini merupakan pesan untuk anda");
    var nama = prompt("Siapa nama anda?", "Masukkan nama anda");
    document.write("Hai, " + nama);
</script>

<head>
<script>
function pesan(){
    alert("Memanggil JavaScript lewat body onload");
}
</script>
</head>
<body onload="pesan()">
<!-- Konten lainnya -->
</body>
```

### Penjelasan

1. **`window.alert()`** digunakan untuk menampilkan kotak pesan sederhana ke pengguna.
   Sifatnya *blocking*, artinya pengguna harus menekan “OK” sebelum dapat melanjutkan interaksi dengan halaman.
2. **`prompt()`** digunakan untuk meminta input teks dari pengguna. Nilai yang dimasukkan pengguna disimpan dalam variabel.
3. **`document.write()`** menampilkan hasil input ke halaman.
4. **`function pesan()`** didefinisikan di bagian `<head>` dan dipanggil secara otomatis ketika halaman selesai dimuat menggunakan atribut `onload="pesan()"`.
   Ini menunjukkan konsep **event handler**, di mana JavaScript merespons kejadian tertentu pada halaman.

### Screenshot

![Screenshot](img/ss2.png)

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

![Screenshot](img/ss3.png)

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

![Screenshot](img/ss4.png)

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

![Screenshot](img/ss5.png)

---

## 6. Validasi Form

### Deskripsi

Materi ini menjelaskan cara membuat validasi sederhana pada form untuk memastikan data yang dikirim telah diisi dengan benar.

### Kode Program

```javascript
function validasi() {
    var nama = document.myForm.nama.value;
    
    if (nama == "") {
        alert("Nama harus diisi!");
        document.myForm.nama.focus();
        return false;
    }

    alert("Validasi Berhasil! Data siap diproses.");
    return true;
}
```

### Penjelasan

1. Fungsi **`validasi()`** digunakan untuk memeriksa apakah field tertentu sudah diisi sebelum form dikirim ke server.
2. Jika `nama` kosong, maka akan muncul peringatan `alert()`, dan fokus dikembalikan ke kolom input dengan **`.focus()`**.
3. `return false` digunakan untuk mencegah pengiriman form jika validasi gagal.
4. Validasi dijalankan ketika form dikirim menggunakan atribut **`onsubmit="return validasi()"`** pada tag `<form>`.

### Screenshot

![Screenshot](img/ss6.png)

---

## Kesimpulan

JavaScript merupakan bahasa pemrograman utama yang berfungsi untuk mengendalikan perilaku halaman web.
Dari praktikum ini diperoleh pemahaman dasar mengenai:

