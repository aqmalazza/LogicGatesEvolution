# Pengujian Gerbang Logika Menggunakan CircuitVerse

## Deskripsi

Repositori ini berisi file praktik **Pengujian Gerbang Logika** menggunakan simulator web [CircuitVerse](https://circuitverse.org/). Praktik ini dibuat untuk memahami konsep dasar rangkaian digital, mulai dari gerbang logika sederhana hingga rangkaian penjumlah biner seperti **Half Adder**, **Full Adder**, dan **4-bit Adder**.

Pengujian ini disusun sebagai bagian dari Tugas Ujian Akhir Mata Kuliah **Arsitektur Komputer**.

## Pengujian yang Dilakukan

Pengujian pada repositori ini meliputi:

1. **Gerbang Logika Dasar**

   * `AND`
   * `OR`
   * `NOT`

2. **Gerbang Logika Universal**

   * `NAND`
   * `NOR`

3. **Gerbang Logika Kombinasi**

   * `XOR`
   * `XNOR`

4. **Half Adder**

   * Metode `XOR` dan `AND`
   * Metode `AND`, `OR`, dan `NOT`
   * Metode `NAND Only`
   * Metode `NOR Only`

5. **Full Adder**

   * Metode standar `XOR`, `AND`, dan `OR`
   * Metode `AND`, `OR`, dan `NOT`
   * Metode `NAND Only`
   * Metode `NOR Only`

6. **4-bit Adder**

   * Cooming Soon

7. **Rangkaian Lanjutan**

   * Subtractor
   * Multiplexer
   * ALU sederhana

## Konsep Dasar

### Half Adder

Half Adder digunakan untuk menjumlahkan dua bit, yaitu `A` dan `B`.

```text
SUM   = A XOR B
Carry = A AND B
```

### Full Adder

Full Adder digunakan untuk menjumlahkan tiga input, yaitu `A`, `B`, dan `Cin`.

```text
S1   = A XOR B
C1   = A AND B
SUM  = S1 XOR Cin
C2   = S1 AND Cin
Cout = C1 OR C2
```

### 4-bit Adder

4-bit Adder disusun dari empat Full Adder yang saling terhubung. `Cout` dari bit sebelumnya menjadi `Cin` untuk bit berikutnya.

```text
FA0 -> FA1 -> FA2 -> FA3
```

## Daftar File

| Nama File        | Keterangan                                                                                                       |
| ---------------- | ---------------------------------------------------------------------------------------------------------------- |
| `TestingGate.cv` | Berisi pengujian gerbang logika, Half Adder, Full Adder, 4-bit Adder, Subtractor, Multiplexer, dan ALU sederhana |

## Struktur Folder

```text
.
├── assets/
│   ├── importfile.png
│   └── subcircuit.png
├── TestingGate.cv
└── README.md
```

## Langkah Mencoba Hasil Pengujian

1. Unduh file `TestingGate.cv` yang tersedia pada repositori ini.

2. Buka simulator CircuitVerse melalui tautan berikut:

   https://circuitverse.org/simulator

3. Pada menu `Project`, pilih `Import File`.

   <img src="assets/importfile.png" alt="Menu Import File pada CircuitVerse" width="250">

4. Pilih file `TestingGate.cv`.

5. Jika rangkaian berhasil muncul pada simulator, proses import telah berhasil.

6. Beberapa rangkaian tersedia dalam bentuk circuit atau subcircuit. Pilih tab circuit yang ingin diuji.

   <img src="assets/subcircuit.png" alt="Tampilan subcircuit pada CircuitVerse" width="250">

7. Ubah nilai input pada rangkaian, lalu amati perubahan output yang dihasilkan.

## Contoh Pengujian

### Half Adder

Contoh input:

```text
A = 1
B = 1
```

Hasil:

```text
SUM   = 0
Carry = 1
```

Sehingga hasil biner ditulis sebagai:

```text
10
```

### Full Adder

Contoh input:

```text
A   = 1
B   = 1
Cin = 1
```

Hasil:

```text
SUM  = 1
Cout = 1
```

Sehingga hasil biner ditulis sebagai:

```text
11
```

### 4-bit Adder

Contoh penjumlahan:

```text
  0101
+ 0011
------
  1000
```

Artinya:

```text
5 + 3 = 8
```

## Tujuan Pengujian

Praktik ini bertujuan untuk memahami cara kerja gerbang logika dalam sistem digital. Selain itu, pengujian ini menunjukkan bagaimana gerbang logika dapat disusun menjadi rangkaian yang lebih kompleks, mulai dari Half Adder, Full Adder, 4-bit Adder, hingga ALU sederhana.

Melalui pengujian ini, konsep arsitektur komputer dapat dipahami secara lebih konkret karena proses perhitungan biner dapat diamati langsung melalui perubahan input dan output pada rangkaian.

## Catatan

File `.cv` hanya dapat dibuka melalui CircuitVerse. Pastikan file berhasil di-import sebelum melakukan pengujian rangkaian.

Jika tampilan rangkaian terlihat terlalu kecil, gunakan fitur zoom pada simulator CircuitVerse agar setiap koneksi dan output dapat diamati dengan jelas.
