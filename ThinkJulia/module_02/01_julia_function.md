# Sub-program (fungsi) dalam Julia

Sebuah fungsi dalam pemrograman terdiri dari beberapa urutan ekspresi dan pernyataan yang menjadi satu kesatuan untuk melakukan proses komputasi tertentu. Sebagai contoh, kita sudah melihat sebelumnya bahwa dalam `Julia` terdapat fungsi `println()` yang dapat mencetak sebuah nilai ke layar. Cara pemanggilan sebuah fungsi dalam `Julia` hampir sama dengan bahasa pemrograman prosedural lainnya seperti `C++`, `Java`, `Python` yaitu dengan menyebutkan nama fungsi diikuti dengan parameter-parameter yang sesuai dan diapit oleh tanda kurung (parenthesis).

```console
julia> println("Hello Gais!")
Hello Gais!
```

Pada skrip diatas, fungsi bernama `println` diikuti dengan sebuah paramter (atau juga dapat disebut argumen) berupa tipe data `String`. Nilai parameter yang diberikan pada fungsi kemudian dicetak ke layar.

Pada umumnya, fungsi juga dapat mengembalikan sebuah nilai. Nilai ini sering disebut sebagai nilai kembalian (*return value*). Contohnya:

```console
julia> x = parse(Int64, "8")
8
julia> print(x)
8
julia> typeof(x)
Int64
```

Dari potongan program diatas, fungsi `parse` menerima dua buah parameter yaitu `Int64` dan `"8"`. Berdasarkan parameter yang diberikan, fungsi `parse` melakukan konversi dan mengembalikan sebuah bilangan bertipe `Int64` (parameter pertama) yang bernilai sesuai dengan paramter keduanya (yaitu `8`). Tidak semua jenis parameter dalam fungsi parse dapat menghasilkan nilai yang sesuai. Potongan kode berikut menghasilkan pesan kesalahan saat pemanggilan fungsi `parse`.

```console
julia> parse(Int64, "Hello")
ERROR: ArgumentError: invalid base 10 digit 'H' in "Hello"
```

Meskipun kita telah mendefinisikan jumlah parameter yang sesuai, namun fungsi `parse` tidak dapat memroses parameter yang diberikan karena fungsi `parse` tidak dapat melakukan konversi dari tipe data `String` menjadi `Int64`.
