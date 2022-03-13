# Mengenal Bahasa Pemrograman `Julia`

Pemrograman dengan `Julia` dapat dilakukan dengan menggunakan `Julia` REPL (Read-Eval-Print Loop). Biasanya `Julia` REPL dapat dieksekusi dari command line dengan mengetikkan perintah `julia` (jika path instalasi `Julia` sudah dikonfigurasi). Berikut ini adalah contoh tampilan `Julia` REPL dari *console*.

```console
julia>
```

## Program pertama `Julia`

Program pertama yang wajib dikerjakan saat mempelajari bahasa baru tentunya adalah program "Hello World". Dalam `Julia` program mencetak teks "Hello World" ke layar *console* adalah sebagai berikut.

```console
julia> println("Hello World")
Hello World
```

## Operasi aritmatika dalam `Julia`

Bahasa pemrograman `Julia` menyediakan berbagai macam operator aritmatika untuk melakukan komputasi. Sebagai contoh, operator `+` digunakan untuk penjumlahan, `-` untuk pengurangan, `*` untuk perkalian, `/` untuk pembagian, dan `^` untuk operasi pangkat.

```console
julia> 1 + 2
3
julia> 4 - 3
1
julia> 2 * 4
8
julia> 8 / 4
2.0
julia> 2^3 - 5
3
```

## Tipe data dalam `Julia`

Jika diperhatikan pada beberapa contoh sebelumnya, kita dapat melihat beberapa bentuk nilai dalam bahasa pemrograman julia: `3` merupakan tipe bilangan bulat (*integer*), `2.0` merupakan tipe bilangan *floating-point*, dan `"Hello World"` merupakan tipe *string*. `Julia` menyediakan perintah untuk mengetahui tipe data dari sebuah nilai.

```console
julia> typeof(3)
Int64
julia> typeof(2.0)
Float64
julia> typeof("Hello World")
String
```

Tipe data `Int64` termasuk dalam tipe bilangan *integer*, `Float64` termasuk dalam tipe bilangan *floating point*, sedangkan `String` sesuai namanya merepresentasikan tipe bilangan *string*. Tipe data `String` selalu diapit oleh tanda petik dua.

```console
julia> typeof("290")
String
julia> typeof("12.789")
String
```

## Exercise 1-1

Whenever you are experimenting with a new feature, you should try to make mistakes. For example, in the `“Hello, World!”` program, what happens if you leave out one of the quotation marks? What if you leave out both? What if you spell println wrong?

This kind of experiment helps you remember what you read; it also helps when you are programming, because you get to know what the error messages mean. It is better to make mistakes now and on purpose rather than later and accidentally.

- In a print statement, what happens if you leave out one of the parentheses, or both?
- If you are trying to print a string, what happens if you leave out one of the quotation marks, or both?
- You can use a minus sign to make a negative number like `-2`. What happens if you put a plus sign before a number? What about `2++2`?
- In math notation, leading zeros are okay, as in `02`. What happens if you try this in Julia?
- What happens if you have two values with no operator between them?

### Answer

- Terjadi kesalahan. `print` merupakan sebuah fungsi dalam julia. Pemanggilan sebuah fungsi biasanya harus dalam format `nama_fungsi` dan selanjutnya diapit oleh tanda kurung buka dan kurung tutup.
- Terjadi kesalahan. Dikarenakan sebuah nilai yang diapit tanda petik dua menandakan tipe data `string`. Sedangkan dalam bahasa pemrograman, statement yang tidak diapit tanda petik dua biasanya merupakan sebuah variabel.
- Terjadi kesalahan karena simbol `++` tidak terdefinisi.
- Ekspresi `02` sah dan memiliki arti sama dengan notasi matematikanya yaitu 2.
- Terjadi kesalahan bahwa ekspresi tidak sah.
