# Mengenal Bahasa Pemrograman `Julia`

Pemrograman dengan `Julia` dapat dilakukan dengan menggunakan `Julia` REPL (Read-Eval-Print Loop). Biasanya `Julia` REPL dapat dieksekusi dari command line dengan mengetikkan perintah `julia` (jika path instalasi `Julia` sudah dikonfigurasi). Berikut ini adalah contoh tampilan `Julia` REPL dari *console*.

```Julia
julia>
```

## Program pertama `Julia`

Program pertama yang wajib dikerjakan saat mempelajari bahasa baru tentunya adalah program "Hello World". Dalam `Julia` program mencetak teks "Hello World" ke layar *console* adalah sebagai berikut.

```Julia
julia> println("Hello World")
Hellow World
```

## Operasi aritmatika dalam `Julia`

Bahasa pemrograman `Julia` menyediakan berbagai macam operator aritmatika untuk melakukan komputasi. Sebagai contoh, operator `+` digunakan untuk penjumlahan, `-` untuk pengurangan, `*` untuk perkalian, `/` untuk pembagian, dan `^` untuk operasi pangkat.

```Julia
julia>1 + 2
3
julia>4 - 3
1
julia>2 * 4
8
julia>8 / 4
2.0
julia>2^3 - 5
3
```

## Tipe data dalam `Julia`

Jika diperhatikan pada beberapa contoh sebelumnya, kita dapat melihat beberapa bentuk nilai dalam bahasa pemrograman julia: `3` merupakan tipe bilangan bulat (*integer*), `2.0` merupakan tipe bilangan *floating-point*, dan `"Hello World"` merupakan tipe *string*. `Julia` menyediakan perintah untuk mengetahui tipe data dari sebuah nilai.

```Julia
julia>typeof(3)
Int64
julia>typeof(2.0)
Float64
julia>typeof("Hello World")
String
```

Tipe data `Int64` termasuk dalam tipe bilangan *integer*, `Float64` termasuk dalam tipe bilangan *floating point*, sedangkan `String` sesuai namanya merepresentasikan tipe bilangan *string*. Tipe data `String` selalu diapit oleh tanda petik dua.

```Julia
julia>typeof("290")
String
julia>typeof("12.789")
String
```
