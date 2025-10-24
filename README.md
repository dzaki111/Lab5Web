
# Lab5Web - Laporan Praktikum JavaScript
#### Nama = [NAMA LENGKAP ANDA]
#### Kelas = [KELAS ANDA]
#### NIM = [NOMOR INDUK MAHASISWA ANDA]
#### Matkul = Pemograman Web 1

---

## 💡 Mahasiswa Belajar: Dasar-Dasar Javascript dan DOM

Pada Praktikum 5 ini, saya mempelajari bagaimana **Javascript (ECMAScript)** digunakan untuk memprogram perilaku halaman web, mengubah konten, hingga membuat form interaktif. Konsep utama yang dipelajari adalah manipulasi **HTML DOM (Document Object Model)** dan logika kontrol program.

---

### A. Kontrol Output dan Log

Saya belajar menggunakan **`document.write()`** untuk langsung menulis konten ke dokumen HTML dan **`console.log()`** untuk mengirim pesan ke *console* browser, yang sangat penting untuk *debugging*.

#### Kode:
```html
<script>
    document.write("<strong>Output dari document.write berhasil!</strong>"); 
    console.log("Hello World: Output ini ada di Console browser.");
</script>
````

#### Screenshot:

*[Sertakan screenshot browser yang menampilkan output di halaman dan di Console browser (F12)]*

-----

### B & D. Interaksi Dasar dengan Pengguna (`alert` dan `prompt`)

Saya mempelajari fungsi-fungsi dasar untuk berinteraksi dengan pengguna. **`window.alert()`** menampilkan kotak peringatan *blocking*, dan **`prompt()`** meminta input data dari pengguna, yang kemudian datanya dapat disimpan ke variabel.

#### Kode `prompt_example.html`:

```javascript
var nama = prompt("siapa nama anda?", "masukkan nama anda");
document.write("<h1>Hai, " + nama + "</h1>");
```

#### Screenshot:

*[Sertakan screenshot kotak alert yang muncul, dan kotak prompt beserta hasil tampilannya di browser]*

-----

### F. Logika Kontrol: Operator Aritmatika dan Fungsi

Saya belajar mendefinisikan dan memanggil fungsi, serta menerapkan **operator aritmatika** (penjumlahan, perkalian, hingga **modulus `%`**). Modulus penting untuk mengecek sisa pembagian (misalnya untuk menentukan bilangan ganjil/genap).

#### Kode Fungsi Aritmatika:

```javascript
function test (val1, val2) {
    document.write("Perkalian: val1 * val2 = " + (val1*val2) + "<br>");
    document.write("Modulus: val1 % val2 = " + (val1%val2) + "<br>");
    // ... operasi lainnya
}
```

#### Screenshot:

*[Sertakan screenshot hasil semua operasi aritmatika (misalnya hasil dari 9 dan 4)]*

-----

### G & H. Logika Kontrol: `if..else` dan `switch`

Saya memahami cara membuat keputusan dalam kode:

1.  **`if..else`** digunakan untuk seleksi kondisi biner atau bertingkat (misalnya menentukan **lulus/tidak lulus**).
2.  **`switch`** digunakan untuk membuat seleksi kondisi dari banyak nilai yang mungkin (*multiple case*), yang lebih rapi daripada menggunakan banyak `if..else if`.

#### Kode `if..else` (Logika Kelulusan):

```javascript
if (nilai >= 60)
    hasil = "lulus";
else
    hasil = "tidak lulus";
```

#### Screenshot:

*[Sertakan screenshot hasil seleksi kondisi if..else dan hasil operator switch]*

-----

### I & J. Manipulasi Objek `document`

Saya belajar memanipulasi properti dari objek **`document`** (halaman web itu sendiri):

1.  Mengubah warna latar belakang dengan **`document.bgColor`**.
2.  Mengubah warna teks dengan **`document.fgColor`**.
3.  Membuat form interaktif (Cek Ganjil/Genap) dengan mengambil dan mengatur nilai properti elemen form (`document.nama_form.T1.value`).

#### Kode Pengubah Warna:

```javascript
function ubahwarnaLB (warna) {
    document.bgColor = warna;
}
```

#### Screenshot:

*[Sertakan screenshot form Ganjil/Genap yang berfungsi dan screenshot halaman dengan warna latar/teks yang sudah diubah]*

-----

### K. HTML DOM: Perhitungan Otomatis (Tugas Utama)

Ini adalah bagian paling penting, di mana saya menerapkan **HTML DOM**. Saya membuat kalkulator menu sederhana yang menghitung total harga secara *real-time* saat *checkbox* dicentang.

**Prinsip yang digunakan:**

1.  Mengambil elemen total (`document.getElementById('total')`).
2.  Mengecek status **`ele.checked`** (apakah dicentang).
3.  Menambahkan (`+`) atau mengurangi (`-`) nilai harga dari total berdasarkan status centang.

#### Kode Fungsi `hitung(ele)`:

```javascript
function hitung(ele) {
    var total = document.getElementById('total').value;
    total = (total ? parseInt(total) : 0); 
    var harga = parseInt(ele.value);

    if (ele.checked) {
        total = total + harga;
    } else {
        total = total - harga;
    }

    document.getElementById('total').value = total;
}
```

#### Screenshot:

*[Sertakan screenshot tampilan daftar menu dan hasil total bayar yang berubah otomatis]*

-----

## 📝 Tugas: Validasi Form

### 1\. Buat script untuk melakukan validasi pada isian form.

Saya membuat fungsi **`validasi()`** yang dieksekusi saat *form* disubmit (`onsubmit="return validasi()"`). Tujuan utamanya adalah mencegah form terkirim jika *field* wajib (Nama dan Email) kosong, sekaligus memberikan *feedback* kepada pengguna.

#### Kode Validasi:

```javascript
function validasi() {
    var nama = document.myForm.nama.value;
    var email = document.myForm.email.value;

    if (nama == "") {
        alert("Nama harus diisi!");
        document.myForm.nama.focus(); 
        return false; // Mencegah submit
    }
    
    if (email == "") {
        alert("Email harus diisi!");
        document.myForm.email.focus(); 
        return false; // Mencegah submit
    }
    
    alert("Validasi Berhasil! Data siap diproses.");
    return true; 
}
```

#### Screenshot Hasil Validasi:

*[Sertakan screenshot kotak alert yang muncul ketika pengguna mencoba submit form dalam keadaan kosong]*

-----

## ✅ Kesimpulan dan Repository

Semua materi praktikum dan tugas telah diselesaikan dengan sukses. Saya telah belajar bagaimana Javascript memberikan nyawa pada HTML dengan menambahkan logika dan interaktivitas yang kuat.

**URL Repository:** [Masukkan URL GitHub Repository Anda di sini]

```
```
