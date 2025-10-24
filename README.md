
# Lab5Web - Laporan Praktikum JavaScript

#### Nama = [NAMA LENGKAP ANDA]
#### Kelas = [KELAS ANDA]
#### NIM = [NOMOR INDUK MAHASISWA ANDA]
#### Matkul = Pemograman Web 1

-----

## Belajar Memprogram Web dengan JavaScript

[cite\_start]Pada Praktikum 5 ini, saya mempelajari **JavaScript (nama resminya adalah ECMAScript [cite: 12][cite\_start])** yang berperan memprogram perilaku halaman web[cite: 14]. [cite\_start]Kode JavaScript disisipkan di antara tag `<script>` dan dapat diletakkan di `<head>`, `<body>`, atau pada file eksternal[cite: 21, 22]. [cite\_start]Saya mempelajari bagaimana JavaScript dapat mengubah konten HTML, atribut, gaya (CSS), serta menyembunyikan atau menampilkan elemen[cite: 15, 17, 18, 19].

### Persiapan Dokumen HTML (`lab5_javascript.html`)

Saya memulai dengan kerangka HTML dasar. [cite\_start]Di sini, saya mempraktikkan dua metode output data paling umum: **`document.write()`**, yang menulis langsung ke output HTML [cite: 45][cite\_start], dan **`console.log()`**, yang menulis ke konsol *browser* dan sangat berguna untuk *debugging*[cite: 47].

#### Kode:

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
```

#### Screenshot:

*[Sertakan screenshot kode `lab5_javascript.html` dan hasil output "Hello World" di browser beserta Console-nya (Gambar 5.1)]*

-----

### Javascrip Dasar: Interaksi, Method, dan Fungsi

Saya mempraktikkan interaksi langsung dengan pengguna dan cara menggunakan *method* dalam objek. [cite\_start]Secara total, ada empat cara utama JavaScript menampilkan data, dan saya mencoba tiga di antaranya: `document.write()`, `window.alert()`, dan `console.log()`[cite: 43].

1.  [cite\_start]**Pemakaian Alert dan Method Objek**: Saya menggunakan **`window.alert()`** sebagai *property* dari objek `window` untuk menampilkan kotak peringatan yang bersifat *blocking*[cite: 93]. [cite\_start]Kemudian, saya menggunakan *method* **`document.write()`** untuk mencetak beberapa baris teks di dalam `<body>`[cite: 115, 116].
2.  [cite\_start]**Pemakaian Prompt**: Fungsi **`prompt()`** digunakan untuk meminta masukan data dari pengguna[cite: 124]. [cite\_start]Nilai yang dimasukkan pengguna disimpan ke variabel (`nama`) dan ditampilkan kembali dengan `document.write()`[cite: 132].
3.  [cite\_start]**Pembuatan Fungsi**: Saya mendefinisikan fungsi **`pesan()`** di bagian `<head>` dan memanggilnya secara otomatis menggunakan *event handler* **`onload=pesan()`** pada tag `<body>`[cite: 144, 148]. Ini memastikan fungsi dieksekusi setelah seluruh elemen halaman dimuat.

#### Kode Dasar dan Fungsi:

```html
<script>
    window.alert("ini merupakan pesan untuk anda");
    var nama = prompt("siapa nama anda?", "masukkan nama anda");
    document.write("hai, " + nama);
</script>

<head>
<script>
function pesan(){
    alert ("memanggil javascript lewat body onload")
}
</script>
</head>
<body onload=pesan()>
```

#### Screenshot Hasil Dasar dan Fungsi:

*[Sertakan screenshot kotak alert, hasil document.write, kotak prompt, dan output fungsi onload]*

-----

### Dasar Pemrograman Di Javascript: Logika Kontrol

Saya fokus pada logika kontrol yang merupakan inti dari pemrograman.

1.  [cite\_start]**Operasi Dasar Aritmatika**: Saya mendefinisikan fungsi `test(val1, val2)` yang menerima dua nilai dan melakukan semua operasi aritmatika dasar: perkalian, pembagian, penjumlahan, pengurangan, dan **modulus**[cite: 164, 177]. Fungsi ini dipanggil melalui tombol menggunakan *event* `onclick`.
2.  [cite\_start]**Seleksi Kondisi (`if..else`)**: Saya menggunakan `prompt` untuk mengambil nilai, lalu menggunakan struktur `if (nilai >= 60)` untuk menentukan apakah hasilnya "lulus" atau "tidak lulus"[cite: 193, 195].
3.  **Penggunaan Operator `switch`**: Saya mempraktikkan `switch` sebagai cara yang lebih efisien untuk menangani seleksi dari banyak nilai. [cite\_start]Program mencocokkan input dengan serangkaian `case` dan menggunakan `break` untuk menghentikan eksekusi, serta `default` untuk kondisi di luar yang ditentukan[cite: 207].

#### Kode Logika Kontrol:

```javascript
// Operasi Aritmatika
function test (val1, val2) {
    document.write("perkalian: " + (val1*val2) + "<br>");
    document.write("modulus: " + (val1%val2) + "<br>");
    // ... operasi lainnya
}

// Seleksi if..else
if (nilai >= 60)
    hasil = "lulus";
else
    hasil = "tidak lulus";
```

#### Screenshot Hasil Logika:

*[Sertakan screenshot hasil operator aritmatika, hasil seleksi kondisi if..else, dan hasil operator switch]*

-----

### Pembuatan Form dan Manipulasi Objek `document`

Saya membuat form interaktif dan belajar memanipulasi properti dari objek **`document`**.

1.  [cite\_start]**Form Input (Cek Ganjil/Genap)**: Saya menggunakan `document.kirim.T1.value` untuk mengambil nilai dari *input field*[cite: 219]. [cite\_start]Logika pengecekan Genap/Ganjil ditentukan oleh **operator modulus (`val1%2==0`)**[cite: 219].
2.  [cite\_start]**Form Button (Objek `document`)**: Saya mendefinisikan fungsi yang mengubah warna latar belakang halaman menggunakan properti **`document.bgColor`** [cite: 246] [cite\_start]dan warna teks menggunakan **`document.fgColor`**[cite: 250]. [cite\_start]Selain itu, saya juga menampilkan informasi kapan dokumen terakhir kali dimodifikasi menggunakan **`document.lastModified`**[cite: 266].

#### Kode Form Input dan Button:

```javascript
// Form Input (Ganjil/Genap)
function test () {
    var val1 = document.kirim.T1.value
    if (val1%2==0)
        document.kirim.T2.value="bilangan genap"
    else
        document.kirim.T2.value="bilangan ganjil"
}

// Form Button (Objek document)
function ubahwarnaLB (warna) {
    document.bgColor = warna;
}
document.write("Dimodifikasi terakhir pada " + document.lastModified);
```

#### Screenshot Hasil Form:

*[Sertakan screenshot form Ganjil/Genap yang berfungsi dan screenshot halaman dengan warna latar/teks yang sudah diubah]*

-----

### HTML DOM: CheckBox Perhitungan Otomatis

[cite\_start]Bagian ini berfokus pada **HTML DOM (Document Object Model)**, di mana saya memprogram perilaku *checkbox* untuk menghitung total secara otomatis[cite: 275]. Fungsi **`hitung(ele)`** dipanggil saat *checkbox* diubah. Fungsi ini:

1.  Mengambil nilai total yang ada menggunakan `document.getElementById('total').value`.
2.  [cite\_start]Mengecek status **`ele.checked`** (apakah dicentang)[cite: 275].
3.  Melakukan penjumlahan atau pengurangan nilai harga dari total, memastikan total diperbarui secara *real-time*.

#### Kode Perhitungan Otomatis:

```javascript
function hitung(ele) {
    var total = document.getElementById('total').value;
    total = (total ? parseInt(total) : 0); 
    var harga = ele.value;

    if (ele.checked) {
        total = total + parseInt(harga);
    } else {
        total = total - parseInt(harga);
    }

    document.getElementById('total').value = total;
}
```

#### Screenshot Hasil DOM:

*[Sertakan screenshot tampilan daftar menu dengan hasil total bayar yang berubah otomatis]*

-----

### Pertanyaan dan Tugas: Validasi Form

Sebagai tugas akhir, saya membuat **script validasi form** untuk memastikan *field* wajib (misalnya Nama dan Email) tidak kosong. Fungsi **`validasi()`** dipanggil oleh *event* `onsubmit`. Jika validasi gagal, fungsi menampilkan `alert()`, mengarahkan kursor ke *field* yang salah (`.focus()`), dan mengembalikan nilai **`false`** untuk menghentikan pengiriman data form.

#### Kode Validasi:

```javascript
function validasi() {
    var nama = document.myForm.nama.value;
    
    if (nama == "") {
        alert("Nama harus diisi!");
        document.myForm.nama.focus(); 
        return false; // Menghentikan pengiriman form
    }
    
    // ... logika validasi field lain (misal: email)
    
    alert("Validasi Berhasil! Data siap diproses.");
    return true; 
}
```

#### Screenshot Hasil Validasi Form:

*[Sertakan screenshot kotak alert yang muncul ketika pengguna mencoba submit form dalam keadaan kosong]*

-----

### Kesimpulan dan Repository

Semua langkah praktikum, dari sintaks dasar, logika kontrol, hingga manipulasi HTML DOM (perhitungan otomatis dan validasi form), telah saya pelajari dan implementasikan. Dengan ini, saya memahami bahwa Javascript adalah kunci untuk menciptakan interaksi dan mengontrol perilaku halaman web. Seluruh pekerjaan ini telah di-*commit* ke *repository* di bawah ini.

**URL Repository:** [Masukkan URL GitHub Repository Anda di sini]

```
```
