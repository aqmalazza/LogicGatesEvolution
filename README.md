# Pengujian Gerbang Logika Menggunakan CircuitVerse

Repositori ini berisi praktik pengujian rangkaian digital menggunakan simulator web [CircuitVerse](https://circuitverse.org/). Praktik ini dibuat untuk memahami cara kerja gerbang logika dari tingkat dasar sampai rangkaian penjumlah biner, seperti **Half Adder**, **Full Adder**, dan **4-bit Adder**.

Proyek ini disusun sebagai bagian dari Tugas Ujian Akhir Mata Kuliah **Arsitektur Komputer**. Melalui simulasi ini, proses kerja rangkaian digital dapat diamati secara langsung berdasarkan perubahan input dan output.

## Daftar Isi

* [Pengujian yang Dilakukan](#pengujian-yang-dilakukan)
* [Konsep Dasar](#konsep-dasar)
* [Daftar File](#daftar-file)
* [Struktur Folder](#struktur-folder)
* [Cara Mencoba Rangkaian](#cara-mencoba-rangkaian)
* [Contoh Pengujian](#contoh-pengujian)
* [Tujuan Pengujian](#tujuan-pengujian)
* [Catatan](#catatan)

## Pengujian yang Dilakukan

Pengujian dalam repositori ini mencakup beberapa rangkaian berikut:

### 1. Gerbang Logika Dasar

* `AND`
* `OR`
* `NOT`

### 2. Gerbang Logika Universal

* `NAND`
* `NOR`

### 3. Gerbang Logika Kombinasi

* `XOR`
* `XNOR`

### 4. Half Adder

Half Adder diuji menggunakan beberapa pendekatan rangkaian, yaitu:

* Metode `XOR` dan `AND`
* Metode `AND`, `OR`, dan `NOT`
* Metode `NAND Only`
* Metode `NOR Only`

### 5. Full Adder

Full Adder diuji menggunakan beberapa metode pembentukan rangkaian, yaitu:

* Metode standar `XOR`, `AND`, dan `OR`
* Metode `AND`, `OR`, dan `NOT`
* Metode `NAND Only`
* Metode `NOR Only`

### 6. 4-bit Adder

4-bit Adder dibuat dengan menghubungkan empat rangkaian Full Adder secara berurutan. Rangkaian ini digunakan untuk menjumlahkan dua bilangan biner 4-bit.

### 7. Rangkaian Lanjutan

Selain rangkaian dasar dan adder, repositori ini juga memuat pengujian rangkaian lanjutan, seperti:

* Subtractor
* Multiplexer
* ALU sederhana

## Konsep Dasar

### Half Adder

Half Adder adalah rangkaian penjumlah sederhana yang digunakan untuk menjumlahkan dua bit, yaitu `A` dan `B`.

Rangkaian ini menghasilkan dua output:

* `SUM` sebagai hasil penjumlahan
* `Carry` sebagai nilai bawaan jika hasil penjumlahan melebihi 1 bit

Rumus Half Adder:

```text
SUM   = A XOR B
Carry = A AND B
```

Contoh:

```text
A = 1
B = 1
```

Hasilnya:

```text
SUM   = 0
Carry = 1
```

Jika ditulis dalam bentuk biner, hasilnya adalah:

```text
10
```

### Full Adder

Full Adder digunakan untuk menjumlahkan tiga input, yaitu `A`, `B`, dan `Cin`.

`Cin` adalah carry input yang berasal dari proses penjumlahan sebelumnya. Karena itu, Full Adder lebih lengkap dibandingkan Half Adder dan dapat digunakan sebagai dasar untuk membuat rangkaian penjumlah multi-bit.

Rumus Full Adder:

```text
S1   = A XOR B
C1   = A AND B
SUM  = S1 XOR Cin
C2   = S1 AND Cin
Cout = C1 OR C2
```

Keterangan:

* `SUM` adalah hasil penjumlahan pada bit tersebut
* `Cout` adalah carry output yang diteruskan ke bit berikutnya

### 4-bit Adder

4-bit Adder adalah rangkaian penjumlah yang digunakan untuk menjumlahkan dua bilangan biner 4-bit.

Rangkaian ini disusun dari empat Full Adder yang saling terhubung. Carry output dari Full Adder sebelumnya akan menjadi carry input untuk Full Adder berikutnya.

Ilustrasi sederhana:

```text
FA0 -> FA1 -> FA2 -> FA3
```

Alur carry-nya:

```text
Cin -> FA0 -> C1 -> FA1 -> C2 -> FA2 -> C3 -> FA3 -> Cout
```

Dengan susunan ini, rangkaian dapat menjumlahkan dua bilangan biner seperti:

```text
  A3 A2 A1 A0
+ B3 B2 B1 B0
-------------
  S3 S2 S1 S0
```

Jika hasil penjumlahan melebihi kapasitas 4-bit, maka nilai lebihnya akan keluar melalui `Cout`.

## Daftar File

| Nama File               | Keterangan                                                                                                                                    |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `GatesTest.cv`          | File utama CircuitVerse yang berisi pengujian gerbang logika, Half Adder, Full Adder, 4-bit Adder, Subtractor, Multiplexer, dan ALU sederhana |
| `assets/importfile.png` | Gambar petunjuk menu import file pada CircuitVerse                                                                                            |
| `assets/subcircuit.png` | Gambar petunjuk tampilan circuit atau subcircuit pada CircuitVerse                                                                            |

## Struktur Folder

```text
.
├── assets/
│   ├── importfile.png
│   └── subcircuit.png
├── GatesTest.cv
└── README.md
```

## Cara Mencoba Rangkaian

Ikuti langkah berikut untuk membuka dan mencoba rangkaian di CircuitVerse.

### 1. Unduh File Project

Unduh file berikut dari repositori:

```text
GatesTest.cv
```

File ini merupakan file utama yang berisi rangkaian digital yang sudah dibuat.

### 2. Buka CircuitVerse

Masuk ke simulator CircuitVerse melalui tautan berikut:

```text
https://circuitverse.org/simulator
```

### 3. Import File ke CircuitVerse

Pada halaman simulator, buka menu:

```text
Project -> Import File
```

Kemudian pilih file `GatesTest.cv` yang sudah diunduh.

<img src="assets/importfile.png" alt="Menu Import File pada CircuitVerse" width="250">

### 4. Pilih Rangkaian yang Ingin Diuji

Setelah file berhasil di-import, rangkaian akan muncul di dalam simulator.

Beberapa rangkaian tersedia dalam bentuk circuit atau subcircuit. Pilih tab rangkaian yang ingin diuji, misalnya:

* Gerbang logika dasar
* Half Adder
* Full Adder
* 4-bit Adder
* Subtractor
* Multiplexer
* ALU sederhana

<img src="assets/subcircuit.png" alt="Tampilan subcircuit pada CircuitVerse" width="250">

### 5. Ubah Nilai Input

Klik bagian input pada rangkaian untuk mengubah nilai dari `0` menjadi `1`, atau sebaliknya.

Setelah input diubah, perhatikan output yang dihasilkan. Output akan berubah sesuai dengan logika rangkaian yang sedang diuji.

## Contoh Pengujian

### Half Adder

Input:

```text
A = 1
B = 1
```

Output:

```text
SUM   = 0
Carry = 1
```

Hasil biner:

```text
10
```

Artinya, nilai `1 + 1` dalam biner menghasilkan `10`.

### Full Adder

Input:

```text
A   = 1
B   = 1
Cin = 1
```

Output:

```text
SUM  = 1
Cout = 1
```

Hasil biner:

```text
11
```

Artinya, nilai `1 + 1 + 1` menghasilkan `3` dalam desimal, atau `11` dalam biner.

### 4-bit Adder

Contoh penjumlahan:

```text
  0101
+ 0011
------
  1000
```

Penjelasan:

```text
0101 = 5
0011 = 3
1000 = 8
```

Jadi, rangkaian 4-bit Adder menghasilkan:

```text
5 + 3 = 8
```

Contoh lain:

```text
  1111
+ 0001
------
1 0000
```

Pada contoh tersebut, hasil penjumlahan membutuhkan 5 bit. Karena 4-bit Adder hanya menampilkan 4 bit utama, maka hasilnya menjadi:

```text
SUM  = 0000
Cout = 1
```

## Tujuan Pengujian

Tujuan dari praktik ini adalah untuk memahami hubungan antara gerbang logika dan rangkaian digital yang lebih kompleks.

Melalui pengujian ini, kita dapat melihat bahwa rangkaian seperti Half Adder, Full Adder, dan 4-bit Adder sebenarnya dibangun dari kombinasi gerbang logika sederhana. Dengan kata lain, operasi penjumlahan biner yang digunakan dalam sistem komputer dapat dijelaskan melalui susunan gerbang logika.

Praktik ini juga membantu memperjelas konsep dasar arsitektur komputer, terutama pada bagian bagaimana komputer melakukan operasi aritmetika secara digital.

## Catatan

File dengan format `.cv` hanya dapat dibuka menggunakan CircuitVerse.

Jika tampilan rangkaian terlihat terlalu kecil, gunakan fitur zoom pada simulator agar koneksi antar gerbang dan output dapat diamati dengan lebih jelas.

Pastikan setiap input diuji secara bertahap agar perubahan output lebih mudah dipahami.
