# Day 3 — Perulangan

> Sekarang kita akan belajar membuat program **mengulangi sesuatu tanpa harus menulis kode yang sama berkali-kali**.

---

## 1. Kenapa kita membutuhkan perulangan?

Misalnya kita ingin menampilkan:

```text
Halo
Halo
Halo
Halo
Halo
```

Tanpa perulangan, kita bisa saja menulis:

```php
echo "Halo";
echo "Halo";
echo "Halo";
echo "Halo";
echo "Halo";
```

Masalahnya, bagaimana kalau kita ingin menampilkan `Halo` sebanyak **100 kali**?

Kita tentu tidak ingin menulis:

```php
echo "Halo";
```

sebanyak 100 kali.

Di sinilah **perulangan** digunakan.

Dengan perulangan, kita bisa mengatakan:

> "Jalankan kode ini beberapa kali."

---

# 2. Jenis perulangan di PHP

Ada beberapa jenis perulangan yang akan kita pelajari:

```text
for
while
do...while
foreach
```

Masing-masing memiliki kegunaan yang sedikit berbeda.

Kita mulai dari `for`.

---

# 3. `for`

`for` biasanya digunakan ketika kita sudah mengetahui berapa kali sesuatu akan dilakukan.

Bentuk dasarnya:

```php
for (nilai_awal; kondisi; perubahan) {
    // kode yang diulang
}
```

Contoh:

```php
for ($i = 1; $i <= 5; $i++) {
    echo $i;
}
```

Hasil:

```text
12345
```

Kalau ingin terlihat lebih jelas:

```php
for ($i = 1; $i <= 5; $i++) {
    echo $i . "\n";
}
```

Hasil:

```text
1
2
3
4
5
```

---

# 4. Memahami bagian `for`

Bagian ini mungkin terlihat aneh pada awalnya:

```php
for ($i = 1; $i <= 5; $i++)
```

Sebenarnya ada tiga bagian:

```text
$i = 1
$i <= 5
$i++
```

Kita bahas satu-satu.

### Bagian pertama

```php
$i = 1
```

Ini adalah nilai awal.

Artinya:

> Mulai dari angka 1.

---

### Bagian kedua

```php
$i <= 5
```

Ini adalah kondisi.

Artinya:

> Selama `$i` masih kurang dari atau sama dengan 5, jalankan perulangannya.

---

### Bagian ketiga

```php
$i++
```

Ini berarti nilai `$i` bertambah 1.

Jadi:

```text
1
2
3
4
5
```

Setelah `$i` menjadi:

```text
6
```

kondisinya:

```text
6 <= 5
```

salah.

Maka perulangan berhenti.

---

# 5. Apa itu `++`?

Di Day 1 kita sudah mengenal operator matematika.

Sekarang kita bertemu:

```php
++
```

`++` berarti menambahkan nilai sebesar 1.

Contoh:

```php
$i = 1;

$i++;
```

Setelah itu nilai `$i` menjadi:

```text
2
```

Kalau:

```php
$i = 5;

$i++;
```

hasilnya:

```text
6
```

Kita juga bisa menggunakan:

```php
$i--;
```

yang berarti mengurangi nilai sebesar 1.

Contoh:

```php
$i = 5;

$i--;
```

hasil:

```text
4
```

---

# 6. Contoh perulangan dari 1 sampai 10

```php
for ($i = 1; $i <= 10; $i++) {
    echo $i . "\n";
}
```

Hasil:

```text
1
2
3
4
5
6
7
8
9
10
```

---

# 7. Menghitung mundur

Perulangan tidak harus selalu bertambah.

Kita bisa menghitung mundur:

```php
for ($i = 5; $i >= 1; $i--) {
    echo $i . "\n";
}
```

Hasil:

```text
5
4
3
2
1
```

Perhatikan:

```php
$i--
```

Sekarang nilainya berkurang satu setiap perulangan.

---

# 8. Menampilkan teks berkali-kali

Kita tidak harus menggunakan angka sebagai output.

Contoh:

```php
for ($i = 1; $i <= 5; $i++) {
    echo "Halo!\n";
}
```

Hasil:

```text
Halo!
Halo!
Halo!
Halo!
Halo!
```

Variabel `$i` tetap digunakan untuk menghitung jumlah perulangannya.

---

# 9. `while`

Sekarang kita masuk ke jenis perulangan kedua.

`while` digunakan ketika kita ingin:

> "Selama kondisi masih benar, lakukan kode ini."

Bentuk dasarnya:

```php
while (kondisi) {
    // kode
}
```

Contoh:

```php
$i = 1;

while ($i <= 5) {
    echo $i . "\n";

    $i++;
}
```

Hasil:

```text
1
2
3
4
5
```

---

# 10. Kenapa `$i++` harus ada?

Perhatikan:

```php
$i = 1;

while ($i <= 5) {
    echo $i . "\n";
}
```

Program akan terus menjalankan:

```text
1
1
1
1
1
1
...
```

dan tidak pernah berhenti.

Kenapa?

Karena nilai `$i` tidak pernah berubah.

Kondisinya selalu:

```text
1 <= 5
```

yang berarti selalu benar.

Ini disebut **infinite loop** atau perulangan tanpa akhir.

Karena itu kita perlu:

```php
$i++;
```

Contoh yang benar:

```php
$i = 1;

while ($i <= 5) {
    echo $i . "\n";

    $i++;
}
```

Sekarang `$i` berubah:

```text
1
2
3
4
5
6
```

Ketika menjadi 6:

```text
6 <= 5
```

bernilai `false`.

Perulangan berhenti.

---

# 11. `for` vs `while`

Keduanya bisa digunakan untuk melakukan hal yang sama.

Contoh dengan `for`:

```php
for ($i = 1; $i <= 5; $i++) {
    echo $i . "\n";
}
```

Dengan `while`:

```php
$i = 1;

while ($i <= 5) {
    echo $i . "\n";

    $i++;
}
```

Hasilnya sama.

Perbedaannya lebih kepada **cara kita memikirkan perulangannya**.

Secara sederhana:

```text
for
→ cocok ketika struktur perulangannya jelas,
  misalnya dari 1 sampai 10.

while
→ cocok ketika perulangan bergantung pada kondisi
  yang bisa berubah.
```

Tidak perlu terlalu memikirkan aturan ini dulu. Dengan semakin banyak latihan, penggunaannya akan terasa lebih natural.

---

# 12. `do...while`

Sekarang ada satu lagi:

```php
do...while
```

Bentuknya:

```php
do {
    // kode
} while (kondisi);
```

Contoh:

```php
$i = 1;

do {
    echo $i . "\n";

    $i++;
} while ($i <= 5);
```

Hasil:

```text
1
2
3
4
5
```

---

# 13. Apa bedanya `while` dan `do...while`?

Perbedaannya cukup penting.

### `while`

Kondisi diperiksa **sebelum** kode dijalankan.

```php
$i = 10;

while ($i <= 5) {
    echo $i;
}
```

Tidak ada output.

Karena:

```text
10 <= 5
```

sudah salah sejak awal.

---

### `do...while`

Kode dijalankan **minimal satu kali**, baru kondisi diperiksa.

```php
$i = 10;

do {
    echo $i;
} while ($i <= 5);
```

Hasil:

```text
10
```

Walaupun kondisi salah, kode di dalam `do` tetap dijalankan satu kali.

Cara mudah mengingat:

```text
while
→ cek dulu, baru jalankan

do...while
→ jalankan dulu, baru cek
```

---

# 14. `break`

Kita sudah pernah melihat `break` di `switch`.

`break` juga bisa digunakan untuk menghentikan perulangan.

Contoh:

```php
for ($i = 1; $i <= 10; $i++) {

    if ($i == 6) {
        break;
    }

    echo $i . "\n";
}
```

Hasil:

```text
1
2
3
4
5
```

Ketika `$i` menjadi 6:

```php
if ($i == 6)
```

benar.

Kemudian:

```php
break;
```

menghentikan perulangan.

---

# 15. `continue`

Selain `break`, ada:

```php
continue;
```

`continue` tidak menghentikan seluruh perulangan.

Ia hanya **melewati iterasi yang sedang berjalan** dan melanjutkan ke iterasi berikutnya.

Contoh:

```php
for ($i = 1; $i <= 5; $i++) {

    if ($i == 3) {
        continue;
    }

    echo $i . "\n";
}
```

Hasil:

```text
1
2
4
5
```

Ketika `$i` adalah 3:

```php
continue;
```

dijalankan.

Jadi bagian:

```php
echo $i;
```

dilewati untuk angka 3.

Tetapi perulangannya tetap berjalan.

---

# 16. Perbedaan `break` dan `continue`

Ini penting untuk dibedakan.

```text
break
→ keluar dari perulangan

continue
→ lewati putaran sekarang
  lalu lanjut ke putaran berikutnya
```

Bayangkan kamu sedang menaiki tangga:

```text
1
2
3
4
5
```

Kalau menggunakan `break` di 3:

```text
1
2
3 → berhenti
```

Kalau menggunakan `continue` di 3:

```text
1
2
3 → dilewati
4
5
```

---

# 17. `foreach`

Sekarang kita sampai pada perulangan yang sangat penting.

`foreach` biasanya digunakan untuk membaca isi **array** satu per satu.

Contoh:

```php
$buah = ["Apel", "Mangga", "Jeruk"];

foreach ($buah as $item) {
    echo $item . "\n";
}
```

Hasil:

```text
Apel
Mangga
Jeruk
```

Kita memang belum membahas array secara khusus.

Array akan menjadi materi Day 4.

Untuk sekarang cukup kenali pola:

```php
foreach ($buah as $item)
```

Artinya kurang lebih:

> Ambil setiap isi dari `$buah`, satu per satu, dan simpan sementara ke `$item`.

---

# 18. Kenapa `foreach` berguna?

Misalnya ada 100 data.

Kita tidak ingin melakukan:

```php
echo $buah[0];
echo $buah[1];
echo $buah[2];
...
```

Dengan `foreach`, kita bisa mengatakan:

```php
foreach ($buah as $item) {
    echo $item;
}
```

PHP akan mengambil datanya satu per satu.

Nanti setelah belajar array lebih dalam, `foreach` akan menjadi jauh lebih masuk akal.

---

# 19. Nested Loop

Sekarang kita coba sesuatu yang sedikit lebih menarik.

Kita bisa membuat perulangan di dalam perulangan.

Ini disebut:

**nested loop**

Contoh:

```php
for ($i = 1; $i <= 3; $i++) {

    for ($j = 1; $j <= 3; $j++) {
        echo "i = $i, j = $j\n";
    }
}
```

Hasil:

```text
i = 1, j = 1
i = 1, j = 2
i = 1, j = 3

i = 2, j = 1
i = 2, j = 2
i = 2, j = 3

i = 3, j = 1
i = 3, j = 2
i = 3, j = 3
```

Memang terlihat sedikit membingungkan.

Untuk sekarang tidak perlu menghafalnya.

Yang penting pahami:

```text
perulangan luar
    ↓
    perulangan dalam
```

Setiap satu putaran dari perulangan luar, perulangan dalam akan berjalan sampai selesai.

---

# 20. Contoh membuat pola

Nested loop sering digunakan untuk membuat pola.

Contoh:

```php
for ($i = 1; $i <= 5; $i++) {

    for ($j = 1; $j <= $i; $j++) {
        echo "*";
    }

    echo "\n";
}
```

Hasil:

```text
*
**
***
****
*****
```

Perhatikan hubungan antara `$i` dan `$j`.

Ketika:

```text
i = 1
```

hanya ada satu `*`.

Ketika:

```text
i = 2
```

ada dua `*`.

Dan seterusnya.

---

# 21. Menggabungkan perulangan dengan percabangan

Sekarang kita gabungkan Day 2 dengan Day 3.

Misalnya kita ingin menampilkan angka 1 sampai 10, tetapi hanya angka genap.

```php
for ($i = 1; $i <= 10; $i++) {

    if ($i % 2 == 0) {
        echo $i . "\n";
    }
}
```

Hasil:

```text
2
4
6
8
10
```

Di sini:

```php
$i % 2
```

digunakan untuk mencari sisa pembagian.

Kalau hasilnya:

```text
0
```

berarti angka tersebut genap.

---

# 22. Contoh program sederhana

Sekarang kita gabungkan beberapa materi yang sudah dipelajari.

Program:

```text
Masukkan angka: 5

1 adalah ganjil
2 adalah genap
3 adalah ganjil
4 adalah genap
5 adalah ganjil
```

Kode:

```php
$angka = readline("Masukkan angka: ");

for ($i = 1; $i <= $angka; $i++) {

    if ($i % 2 == 0) {
        echo $i . " adalah genap\n";
    } else {
        echo $i . " adalah ganjil\n";
    }
}
```

Perhatikan apa saja yang kita gunakan:

```text
readline()
variabel
for
if
else
operator %
```

Artinya materi mulai saling terhubung.

---

# Latihan

## Latihan 1 — Angka 1 sampai 10

Buat program yang menampilkan:

```text
1
2
3
4
5
6
7
8
9
10
```

Gunakan `for`.

---

## Latihan 2 — Angka mundur

Buat program yang menampilkan:

```text
10
9
8
7
6
5
4
3
2
1
```

Gunakan `for`.

---

## Latihan 3 — Angka genap

Tampilkan semua angka genap dari:

```text
1 sampai 20
```

Contoh hasil:

```text
2
4
6
8
10
...
20
```

Gunakan:

```php
if
%
```

---

## Latihan 4 — Angka ganjil

Lakukan hal yang sama untuk angka ganjil:

```text
1
3
5
7
...
19
```

---

## Latihan 5 — `while`

Buat ulang program angka 1 sampai 10 menggunakan:

```php
while
```

Bukan `for`.

---

## Latihan 6 — Hitung mundur

Buat program:

```text
5
4
3
2
1
Mulai!
```

Gunakan perulangan.

---

## Latihan 7 — Lewati angka

Buat program yang menampilkan angka 1 sampai 10 tetapi **tidak menampilkan angka 5**.

Gunakan:

```php
continue;
```

---

## Latihan 8 — Berhenti di angka tertentu

Buat program yang menghitung dari 1 sampai 10 tetapi berhenti ketika mencapai angka 7.

Gunakan:

```php
break;
```

Hasil:

```text
1
2
3
4
5
6
```

---

# Latihan kecil — Tabel perkalian

Sekarang kita membuat sesuatu yang lebih menarik.

Buat program yang meminta angka:

```text
Masukkan angka: 5
```

Kemudian menghasilkan:

```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

Petunjuk:

Kita membutuhkan:

```text
readline()
for
variabel
perkalian
```

Coba buat sendiri sebelum melihat solusi.

---

# Latihan kecil 2 — Segitiga

Buat pola:

```text
*
**
***
****
*****
```

Gunakan nested loop.

Kalau sudah berhasil, coba buat kebalikannya:

```text
*****
****
***
**
*
```

Latihan ini bukan karena pola bintang sangat penting.

Tujuannya adalah supaya kita mulai terbiasa memahami **perulangan di dalam perulangan**.

---

# Yang perlu dipahami setelah Day 3

Setelah materi ini, kita sudah mengenal:

* `for`
* `while`
* `do...while`
* `foreach`
* `break`
* `continue`
* `++`
* `--`
* nested loop
* menggabungkan loop dengan `if`
* penggunaan `%` untuk mengecek genap/ganjil

Tetapi yang paling penting bukan menghafal bentuk syntax.

Pahami ide dasarnya:

```text
for
→ ulangi dengan struktur penghitung yang jelas

while
→ ulangi selama kondisi benar

do...while
→ jalankan minimal sekali, lalu periksa kondisi

foreach
→ ambil data satu per satu dari kumpulan data

break
→ berhenti

continue
→ lewati putaran sekarang
```

---

# Setelah ini

Di **Day 4**, kita akan membahas **Array**.

Sampai sekarang kita menyimpan data seperti:

```php
$nama = "Ivan";
$umur = 20;
$jurusan = "Informatika";
```

Bayangkan kalau kita mempunyai 100 nama.

Tidak masuk akal kalau kita membuat:

```php
$nama1
$nama2
$nama3
...
$nama100
```

Array dibuat untuk menangani kumpulan data seperti itu.

Dan setelah memahami array, `foreach` yang kita pelajari hari ini akan jauh lebih mudah dipahami.

---

## Catatan

Kalau `for` masih terasa membingungkan, jangan langsung menghafal bentuk:

```php
for ($i = 1; $i <= 10; $i++)
```

Coba baca sebagai kalimat:

> Mulai dari 1, selama masih sampai 10, setiap putaran tambahkan 1.

Kalau cara membacanya sudah mulai terasa natural, berarti konsep dasarnya sudah mulai masuk.
