# Day 1 — Mengenal PHP dan Dasar Pemrograman

> Materi ini dibuat sebagai titik awal belajar PHP dari nol.
>
> Tujuannya bukan untuk menghafal syntax, tetapi supaya kita tahu apa yang sedang kita tulis dan kenapa kita menulisnya.

---

## 1. Sebelum mulai

PHP adalah bahasa pemrograman yang banyak digunakan untuk membuat aplikasi web.

Kalau baru pertama kali belajar pemrograman, jangan terlalu memikirkan istilah-istilah yang banyak. Untuk sekarang cukup pahami satu hal:

**Program adalah kumpulan instruksi yang kita berikan kepada komputer untuk melakukan sesuatu.**

Contohnya:

```php
<?php

echo "Halo dunia!";
```

Program tersebut memberikan instruksi kepada PHP untuk menampilkan tulisan:

```text
Halo dunia!
```

---

## 2. Apa itu PHP?

PHP adalah bahasa pemrograman yang biasanya digunakan untuk membuat bagian yang berjalan di sisi server (server-side).

Contoh sederhananya, ketika seseorang membuka sebuah website:

```text
Browser
   ↓
Request
   ↓
Server
   ↓
PHP menjalankan program
   ↓
Hasil dikirim kembali
   ↓
Browser
```

Jadi PHP tidak harus dibayangkan sebagai sesuatu yang langsung "menggambar website".

PHP bisa digunakan untuk mengolah data, menjalankan logika program, berkomunikasi dengan database, mengatur login, dan banyak hal lainnya.

---

## 3. Menjalankan PHP

Untuk belajar PHP di komputer sendiri, kita membutuhkan PHP yang sudah terpasang.

Coba buka terminal dan jalankan:

```bash
php -v
```

Kalau PHP sudah terpasang, akan muncul informasi versi PHP.

Contohnya:

```text
PHP 8.x.x
```

Kalau perintah tersebut tidak ditemukan, berarti PHP belum tersedia di sistem dan kita perlu memasangnya terlebih dahulu.

---

## 4. File PHP

File PHP biasanya menggunakan ekstensi:

```text
.php
```

Contohnya:

```text
belajar.php
```

Isi paling sederhana:

```php
<?php

echo "Halo!";
```

Bagian:

```php
<?php
```

menandakan bahwa kita mulai menulis kode PHP.

Sedangkan:

```php
echo "Halo!";
```

digunakan untuk menampilkan tulisan.

---

## 5. `echo`

`echo` digunakan untuk menampilkan sesuatu.

Contoh:

```php
<?php

echo "Halo dunia!";
```

Hasil:

```text
Halo dunia!
```

Kita juga bisa menampilkan beberapa hal:

```php
<?php

echo "Nama saya Ivan";
echo "Saya sedang belajar PHP";
```

Hasilnya bisa terlihat menempel karena kita belum memberikan pemisah.

Kita bisa menggunakan HTML `<br>` jika menjalankannya melalui web server:

```php
<?php

echo "Nama saya Ivan<br>";
echo "Saya sedang belajar PHP";
```

---

## 6. String

Tulisan yang berada di dalam tanda kutip disebut string.

Contoh:

```php
"Hello"
"PHP"
"Belajar pemrograman"
```

Contoh di PHP:

```php
<?php

echo "Saya sedang belajar PHP";
```

Ada dua bentuk tanda kutip yang sering digunakan:

```php
"Hello"
```

dan:

```php
'Hello'
```

Untuk tahap awal, keduanya tidak perlu terlalu dipikirkan. Nanti kita akan melihat perbedaan keduanya ketika membahas variabel dan string.

---

## 7. Komentar

Komentar adalah tulisan di dalam kode yang tidak dijalankan oleh PHP.

Komentar berguna untuk memberikan catatan kepada diri sendiri atau orang lain.

Satu baris:

```php
// Ini komentar
```

atau:

```php
# Ini juga komentar
```

Beberapa baris:

```php
/*
   Ini komentar
   yang terdiri dari
   beberapa baris
*/
```

Contoh:

```php
<?php

// Menampilkan nama
echo "Ivan";
```

PHP tidak akan menampilkan tulisan:

```text
// Menampilkan nama
```

Yang ditampilkan hanya:

```text
Ivan
```

---

## 8. Variabel

Sekarang kita masuk ke bagian yang penting.

Variabel adalah tempat untuk menyimpan sebuah nilai.

Contohnya:

```php
$nama = "Ivan";
```

Kita bisa membayangkannya seperti sebuah kotak:

```text
$nama
┌─────────────┐
│    Ivan     │
└─────────────┘
```

Kemudian nilai tersebut bisa kita gunakan lagi:

```php
<?php

$nama = "Ivan";

echo $nama;
```

Hasil:

```text
Ivan
```

Di PHP, nama variabel diawali dengan `$`.

Contoh:

```php
$nama
$umur
$nilai
$alamat
```

---

## 9. Mengubah nilai variabel

Nilai sebuah variabel dapat diubah.

```php
<?php

$nama = "Ivan";

echo $nama;

$nama = "Budi";

echo $nama;
```

Awalnya:

```text
Ivan
```

Kemudian nilai `$nama` diganti menjadi:

```text
Budi
```

Jadi variabel tidak harus memiliki nilai yang sama selamanya.

---

## 10. Beberapa tipe data dasar

Untuk sekarang kita kenalan dulu dengan beberapa tipe data.

### String

Untuk teks:

```php
$nama = "Ivan";
```

### Integer

Untuk bilangan bulat:

```php
$umur = 20;
```

### Float

Untuk bilangan desimal:

```php
$tinggi = 170.5;
```

### Boolean

Nilainya hanya:

```php
true
```

atau:

```php
false
```

Contoh:

```php
$isLogin = true;
```

Jangan terlalu memaksakan diri untuk menghafal semuanya sekarang. Yang penting tahu bahwa tidak semua data yang kita simpan bentuknya sama.

---

## 11. Operator aritmatika

PHP juga bisa digunakan untuk melakukan perhitungan.

```php
$a = 10;
$b = 5;

echo $a + $b;
```

Hasil:

```text
15
```

Operator dasar:

```text
+   penjumlahan
-   pengurangan
*   perkalian
/   pembagian
%   sisa pembagian
```

Contoh:

```php
<?php

$a = 10;
$b = 3;

echo $a + $b;
echo $a - $b;
echo $a * $b;
echo $a / $b;
echo $a % $b;
```

Untuk sekarang tidak perlu menghafal contoh yang panjang. Cukup pahami bahwa PHP bisa melakukan operasi matematika seperti kalkulator.

---

## 12. Menggabungkan teks dan variabel

Misalnya kita mempunyai:

```php
$nama = "Ivan";
```

Kita ingin menghasilkan:

```text
Halo, nama saya Ivan
```

Kita bisa menggunakan concatenation dengan operator `.`:

```php
<?php

$nama = "Ivan";

echo "Halo, nama saya " . $nama;
```

Perhatikan titik:

```php
.
```

Titik tersebut digunakan untuk menggabungkan string.

Contoh lain:

```php
$nama = "Ivan";
$umur = 20;

echo "Nama: " . $nama;
echo "Umur: " . $umur;
```

---

## 13. Input sederhana dengan `readline()`

Kalau menjalankan PHP melalui terminal, kita bisa meminta input dari pengguna.

Contoh:

```php
<?php

$nama = readline("Masukkan nama: ");

echo "Halo, " . $nama;
```

Ketika program dijalankan:

```text
Masukkan nama:
```

Kita bisa mengetik:

```text
Ivan
```

Kemudian program menghasilkan:

```text
Halo, Ivan
```

Ini merupakan contoh sederhana bahwa program tidak harus selalu menggunakan data yang kita tulis langsung di dalam kode.

---

# Latihan

Jangan langsung melihat contoh jawaban. Coba kerjakan sendiri terlebih dahulu.

## Latihan 1

Buat program yang menampilkan:

```text
Halo, saya sedang belajar PHP.
```

---

## Latihan 2

Buat tiga variabel:

```text
nama
umur
jurusan
```

Kemudian tampilkan semuanya.

Contoh hasil:

```text
Nama: Ivan
Umur: 20
Jurusan: ...
```

---

## Latihan 3

Buat dua variabel angka:

```text
$a = 15
$b = 4
```

Tampilkan:

- hasil penjumlahan
- hasil pengurangan
- hasil perkalian
- hasil pembagian
- sisa pembagian

---

## Latihan 4

Buat program yang meminta nama menggunakan `readline()`.

Kemudian tampilkan:

```text
Halo, [nama yang dimasukkan]!
Selamat belajar PHP.
```

---

# Yang perlu dipahami setelah Week 1

Sebelum lanjut, setidaknya kita sudah mengenal:

- apa itu PHP
- file `.php`
- `<?php`
- `echo`
- komentar
- variabel
- string
- integer
- float
- boolean
- operator aritmatika
- menggabungkan string dengan `.`
- input sederhana menggunakan `readline()`

Tidak masalah kalau belum hafal semua syntax.

Yang lebih penting adalah ketika melihat:

```php
$nama = "Ivan";
```

kita sudah tahu bahwa program sedang membuat sebuah variabel bernama `$nama` dan memberikan nilai `"Ivan"`.

Dan ketika melihat:

```php
echo $nama;
```

kita tahu bahwa program sedang menampilkan isi dari variabel tersebut.

---

# Setelah ini

Materi berikutnya akan membahas **percabangan dan logika**.

Kita akan mulai membuat program yang bisa mengambil keputusan, misalnya:

```text
Jika nilai >= 75
    → Lulus

Jika nilai < 75
    → Tidak lulus
```

Dari sini program mulai terasa seperti program sungguhan, bukan cuma menampilkan tulisan.

---

## Catatan

Jangan buru-buru lanjut kalau bagian variabel dan operator masih terasa membingungkan.

Kalau ada kode yang tidak dimengerti, lebih baik berhenti sebentar dan membongkar kode tersebut daripada sekadar menyalin dan menjalankannya.
