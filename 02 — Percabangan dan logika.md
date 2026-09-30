# Day 2 — Percabangan dan Logika

> Di Day 1 kita belajar variabel, tipe data, output, input sederhana, dan operator.
>
> Sekarang kita mulai membuat program yang bisa **mengambil keputusan**.

---

## 1. Apa itu percabangan?

Program sering perlu menentukan tindakan berdasarkan kondisi.

Misalnya kita ingin menentukan apakah seseorang lulus:

```text
Jika nilai >= 75
    Lulus

Jika nilai < 75
    Tidak lulus
```

Program perlu memeriksa kondisi terlebih dahulu.

Dalam PHP, kita bisa menggunakan:

* `if`
* `else`
* `elseif`

---

## 2. `if`

`if` digunakan untuk menjalankan kode ketika suatu kondisi terpenuhi.

Bentuk dasarnya:

```php
if (kondisi) {
    // kode yang dijalankan
}
```

Contoh:

```php
$nilai = 80;

if ($nilai >= 75) {
    echo "Lulus";
}
```

Karena `80 >= 75` bernilai benar, program menghasilkan:

```text
Lulus
```

Kalau nilainya:

```php
$nilai = 60;
```

maka kondisi:

```php
$nilai >= 75
```

bernilai salah.

Akibatnya kode di dalam `if` tidak dijalankan.

---

## 3. Memahami kondisi

Bagian ini:

```php
$nilai >= 75
```

adalah sebuah kondisi.

Program sebenarnya sedang bertanya:

> Apakah nilai lebih besar atau sama dengan 75?

Jawabannya adalah:

```text
true
```

atau:

```text
false
```

Contoh:

```text
80 >= 75 → true

60 >= 75 → false
```

Konsep `true` dan `false` ini akan sering kita gunakan dalam pemrograman.

---

## 4. Operator perbandingan

Untuk membuat kondisi, kita membutuhkan operator perbandingan.

| Operator | Arti                  |
| -------- | --------------------- |
| `==`     | sama dengan           |
| `===`    | sama nilai dan tipe   |
| `!=`     | tidak sama            |
| `!==`    | tidak identik         |
| `>`      | lebih besar           |
| `<`      | lebih kecil           |
| `>=`     | lebih besar atau sama |
| `<=`     | lebih kecil atau sama |

Contoh:

```php
$umur = 20;

if ($umur >= 18) {
    echo "Boleh masuk";
}
```

Karena:

```text
20 >= 18
```

hasilnya adalah `true`.

---

## 5. Perbedaan `==` dan `===`

Ini salah satu hal yang sering membuat pemula bingung.

Misalnya:

```php
5 == "5"
```

PHP membandingkan nilainya dan dalam konteks ini dapat menganggap keduanya sama.

Sedangkan:

```php
5 === "5"
```

juga memperhatikan tipe datanya.

```text
5    → integer
"5"  → string
```

Karena tipe datanya berbeda, hasilnya:

```text
false
```

Untuk sekarang cukup ingat:

```text
==  → membandingkan nilai

=== → membandingkan nilai + tipe data
```

Nanti kita akan membahasnya lebih dalam ketika sudah lebih banyak menggunakan PHP.

---

## 6. `else`

Sekarang coba lihat program ini:

```php
$nilai = 60;

if ($nilai >= 75) {
    echo "Lulus";
}
```

Kalau nilainya 60, tidak ada output.

Kita bisa memberikan pilihan lain menggunakan `else`.

```php
$nilai = 60;

if ($nilai >= 75) {
    echo "Lulus";
} else {
    echo "Tidak lulus";
}
```

Sekarang program mempunyai dua kemungkinan:

```text
nilai >= 75
    ↓
  Lulus

nilai < 75
    ↓
Tidak lulus
```

---

## 7. `elseif`

Bagaimana kalau kondisinya lebih dari dua?

Misalnya kita ingin menentukan nilai huruf:

```text
90 - 100 → A
80 - 89  → B
70 - 79  → C
60 - 69  → D
< 60     → E
```

Kita bisa menggunakan `elseif`.

```php
$nilai = 85;

if ($nilai >= 90) {
    echo "A";
} elseif ($nilai >= 80) {
    echo "B";
} elseif ($nilai >= 70) {
    echo "C";
} elseif ($nilai >= 60) {
    echo "D";
} else {
    echo "E";
}
```

Hasil:

```text
B
```

Kenapa?

Program memeriksa dari atas:

```text
85 >= 90?
    ↓
Tidak

85 >= 80?
    ↓
Ya

B
```

Setelah menemukan kondisi yang benar, PHP tidak perlu melanjutkan ke kondisi berikutnya.

---

## 8. Urutan kondisi itu penting

Perhatikan contoh berikut:

```php
$nilai = 85;

if ($nilai >= 60) {
    echo "D";
} elseif ($nilai >= 80) {
    echo "B";
}
```

Mungkin kita mengira hasilnya:

```text
B
```

Tetapi hasil sebenarnya:

```text
D
```

Kenapa?

Karena:

```text
85 >= 60
```

sudah benar.

PHP langsung menjalankan:

```php
echo "D";
```

dan tidak melanjutkan ke `elseif`.

Karena itu, ketika membuat rentang nilai, biasanya kita mulai dari nilai tertinggi:

```php
if ($nilai >= 90) {
    echo "A";
} elseif ($nilai >= 80) {
    echo "B";
} elseif ($nilai >= 70) {
    echo "C";
} elseif ($nilai >= 60) {
    echo "D";
} else {
    echo "E";
}
```

---

# 9. Operator logika

Kadang satu kondisi saja tidak cukup.

Contohnya:

> Seseorang boleh masuk jika umurnya minimal 18 **dan** mempunyai kartu.

Kita membutuhkan operator logika.

Operator yang akan kita gunakan:

| Operator | Arti        |   |           |
| -------- | ----------- | - | --------- |
| `&&`     | dan / AND   |   |           |
| `        |             | ` | atau / OR |
| `!`      | bukan / NOT |   |           |

---

## 10. `&&` — AND

`&&` berarti **dan**.

Semua kondisi harus benar.

Contoh:

```php
$umur = 20;
$punyaKartu = true;

if ($umur >= 18 && $punyaKartu) {
    echo "Boleh masuk";
}
```

Ada dua syarat:

```text
umur >= 18
DAN
punya kartu
```

Kalau keduanya benar:

```text
Boleh masuk
```

Tetapi kalau:

```php
$umur = 20;
$punyaKartu = false;
```

maka hasilnya tidak boleh masuk.

Karena salah satu syarat tidak terpenuhi.

Cara mudah mengingat:

```text
&& = semua harus benar
```

---

## 11. `||` — OR

`||` berarti **atau**.

Minimal salah satu kondisi harus benar.

Contoh:

```php
$punyaTiket = false;
$punyaUndangan = true;

if ($punyaTiket || $punyaUndangan) {
    echo "Boleh masuk";
}
```

Walaupun tidak mempunyai tiket, orang tersebut mempunyai undangan.

Jadi:

```text
false || true
```

menghasilkan:

```text
true
```

Cara mudah mengingat:

```text
|| = salah satu cukup
```

---

## 12. `!` — NOT

`!` digunakan untuk membalik nilai boolean.

Misalnya:

```php
$isLogin = false;
```

Kalau kita menulis:

```php
!$isLogin
```

hasilnya menjadi:

```text
true
```

Contoh:

```php
$isLogin = false;

if (!$isLogin) {
    echo "Silakan login terlebih dahulu";
}
```

Karena `$isLogin` bernilai `false`, maka:

```php
!$isLogin
```

menjadi `true`.

Cara mudah mengingat:

```text
! = kebalikan
```

---

# 13. Menggabungkan dengan `readline()`

Di Day 1 kita sudah belajar:

```php
readline()
```

Sekarang kita gabungkan dengan percabangan.

```php
$nilai = readline("Masukkan nilai: ");

if ($nilai >= 75) {
    echo "Lulus";
} else {
    echo "Tidak lulus";
}
```

Ketika program dijalankan:

```text
Masukkan nilai:
```

Misalnya kita memasukkan:

```text
80
```

hasilnya:

```text
Lulus
```

Kalau kita memasukkan:

```text
60
```

hasilnya:

```text
Tidak lulus
```

Di sini program sudah mulai terasa berbeda dari Day 1.

Program tidak hanya menampilkan sesuatu.

Program sekarang bisa:

```text
menerima input
      ↓
memeriksa kondisi
      ↓
mengambil keputusan
```

---

# 14. `switch`

Selain `if`, PHP mempunyai `switch`.

`switch` biasanya digunakan ketika kita mempunyai beberapa pilihan berdasarkan satu nilai.

Contoh:

```php
$menu = 2;

switch ($menu) {
    case 1:
        echo "Mulai";
        break;

    case 2:
        echo "Pengaturan";
        break;

    case 3:
        echo "Keluar";
        break;

    default:
        echo "Pilihan tidak tersedia";
}
```

Jika `$menu` bernilai `2`, hasilnya:

```text
Pengaturan
```

---

## 15. `case`

`case` digunakan untuk menentukan kemungkinan yang ingin diperiksa.

Contoh:

```php
case 1:
    echo "Mulai";
    break;
```

Artinya kurang lebih:

> Kalau nilainya 1, jalankan bagian ini.

---

## 16. `break`

Perhatikan:

```php
case 1:
    echo "Mulai";
    break;
```

`break` digunakan untuk menghentikan proses `switch` setelah pilihan yang sesuai ditemukan.

Untuk sekarang cukup ingat:

```text
break = hentikan switch
```

Kita akan bertemu lagi dengan `break` ketika nanti belajar perulangan.

---

# 17. `default`

`default` digunakan ketika tidak ada `case` yang cocok.

Contoh:

```php
$menu = 5;

switch ($menu) {
    case 1:
        echo "Mulai";
        break;

    case 2:
        echo "Pengaturan";
        break;

    case 3:
        echo "Keluar";
        break;

    default:
        echo "Pilihan tidak tersedia";
}
```

Karena tidak ada:

```text
case 5
```

maka program menjalankan:

```text
Pilihan tidak tersedia
```

---

# 18. Kapan menggunakan `if` dan `switch`?

Tidak perlu menganggap salah satu lebih bagus dari yang lain.

Gunakan `if` ketika kita memeriksa kondisi atau rentang nilai.

Contoh:

```php
if ($nilai >= 75) {
    echo "Lulus";
}
```

Gunakan `switch` ketika satu nilai mempunyai beberapa pilihan yang jelas.

Contoh:

```php
switch ($menu) {
    case 1:
        echo "Mulai";
        break;

    case 2:
        echo "Pengaturan";
        break;
}
```

---

# Latihan

Jangan langsung mencari jawabannya.

Coba tulis programnya sendiri terlebih dahulu.

## Latihan 1 — Cek umur

Buat program yang meminta umur pengguna.

Jika umur minimal 17:

```text
Kamu sudah cukup umur.
```

Jika belum:

```text
Kamu belum cukup umur.
```

Gunakan:

```php
readline()
```

dan:

```php
if
else
```

---

## Latihan 2 — Nilai

Buat program yang meminta nilai.

Gunakan aturan:

```text
90 - 100 → A
80 - 89  → B
70 - 79  → C
60 - 69  → D
< 60     → E
```

Gunakan:

```text
if
elseif
else
```

---

## Latihan 3 — Login sederhana

Buat:

```php
$username = "ivan";
$password = "12345";
```

Kemudian minta username dan password dari pengguna.

Jika keduanya benar:

```text
Login berhasil
```

Jika salah:

```text
Username atau password salah
```

**Catatan:** pola ini hanya untuk latihan dasar. Jangan menggunakan password yang ditulis langsung seperti ini untuk aplikasi sungguhan.

---

## Latihan 4 — Operator logika

Buat program dengan:

```php
$umur
$punyaKartu
```

Seseorang boleh masuk jika:

* umur minimal 18
* mempunyai kartu

Gunakan:

```php
&&
```

---

## Latihan 5 — Menu

Buat menu:

```text
1. Mulai
2. Pengaturan
3. Keluar
```

Gunakan `switch`.

Jika pengguna memilih:

```text
1
```

tampilkan:

```text
Memulai program...
```

dan seterusnya.

---

# Latihan kecil — Program pengecekan nilai

Sekarang gabungkan materi Day 1 dan Day 2.

Buat program yang meminta:

```text
Nama
Nilai
```

Kemudian program menentukan:

1. nilai huruf
2. status lulus

Contoh:

```text
=== Program Nilai ===

Nama  : Ivan
Nilai : 85

Hasil : B
Status: Lulus
```

Gunakan:

* variabel
* `readline()`
* operator perbandingan
* `if`
* `elseif`
* `else`

Belum perlu menggunakan:

* array
* function
* class
* object

Karena semuanya belum kita pelajari.

---

# Yang perlu dipahami setelah Day 2

Setelah materi ini, setidaknya kita sudah mengenal:

* `if`
* `else`
* `elseif`
* `switch`
* `case`
* `default`
* `break`
* operator perbandingan
* `&&`
* `||`
* `!`

Tetapi jangan hanya menghafal syntax.

Yang paling penting adalah memahami pola berpikirnya:

```text
Data
 ↓
Periksa kondisi
 ↓
Apakah benar?
 ├── Ya → lakukan A
 └── Tidak → lakukan B
```

---

# Setelah ini

Di **Day 3** kita akan masuk ke **perulangan**.

Sekarang kita baru bisa mengatakan:

```text
Kalau kondisi benar → lakukan sesuatu.
```

Nanti kita akan belajar:

```text
Lakukan sesuatu berkali-kali.
```

Kita akan membahas:

```php
for
while
do...while
foreach
```

dan melihat kapan masing-masing digunakan.

---

## Catatan

Kalau `if` dan `else` sudah masuk akal tetapi `&&`, `||`, atau `!` masih terasa membingungkan, tidak perlu dipaksakan menghafalnya.

Cukup ingat dulu:

```text
&& → dan
|| → atau
!  → kebalikan
```

Nanti ketika program kita semakin kompleks, penggunaannya akan lebih mudah dipahami.
