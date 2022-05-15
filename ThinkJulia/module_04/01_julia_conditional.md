# Kondisi dan Percabangan dalam Julia


## Ekspresi boolean dan operator pembanding

Dalam bahasa pemrograman pada umumnya, kondisi dinyatakan dengan ekspresi boolean. Sebuah ekspresi boolean bernilai `true` (benar) atau `false` (salah). Dalam contoh berikut, kita menggunakan operator pembanding `==` (kesamaan antara dua nilai), dimana ekspresi menghasilkan nilai boolean. Perhatikan perbedaan antara operator pembanding `==` dengan `=` (assignment).

```bash
julia> 1 == 1
true
julia> 1 == 0
false
```

Operator `==` menyatakan ekspresi boolean apakah nilai di sebelah kiri operator **sama dengan** nilai di sebelah kanan. Ekspresi boolean menghasilkan nilai `true` dan `false` jika dievaluasi. Kita dapat mengecek bahwa kedua nilai ini merupakan tipe data `Boool` (boolean).

```bash
julia> typeof(true)
Bool
julia> typeof(false)
Bool
```

Selain operator `==`, ada beberapa operator pembanding lainnya dalam Julia.

```julia
x != y          # x tidak sama dengan y
x ≠ y           # x tidak sama dengan y juga! (cara menulis operator \ne <kbd>TAB</kbd>)
x > y           # x lebih besar dari y
x < y           # x lebih kecil dari y
x >= y          # x lebih besar sama dengan y
x ≥ y           # lebih besar sama dengan (\ge <kbd>TAB</kbd>)
x <= y          # x lebih kecil sama dengan y
x ≤ y           # lebih kecil sama dengan (\le <kbd>TAB</kbd>)
```

## Operator logika

Selain menggunakan operator perbandingan, kita juga dapat menggunakan operator logika untuk menyatakan ekspresi boolean. Ada tiga jenis operator logika dalam Julia: `&&` (and---dan), `||` (or---atau), `!` (not---bukan). Sebagai contoh, ekspresi berikut ini `x > 0 && x < 5` bernilai `true` jika dan hanya jika nilai `x > 0` **DAN** `x < 5`. Perlu dicatat bahwa opearator `&&` dan `||` dievaluasi dari kiri ke kanan dengan prioritas operator `&&` lebih tinggi daripada `||`. Perthatikan contoh berikut

```bash
julia> true || true && false
true
julia> true && false || false
false
```

Operator `!` menghasilkan nilai kebalikan dari sebuah nilai boolean. Misalnya, untuk ekspresi `!(x && y)` bernilai `True` jika `x && y` bernilai `False`, yaitu ketika salah satu atau kedua nilai `x` dan `y` bernilai `False`.

## Percabangan

Dalam menulis program kita membutuhkan kemampuan untuk melakukan kontrol terhadap alur eksekusi program yang mengakibatkan perubahan alur eksekusi (sering disebut juga sebagai percabangan) yang diinginkan. Dengan menggunakan kata kunci `if-end`, kita dapat melakukan perubahan alur eksekusi program.

```julia
if x > 0
    println("x bilangan positif")
end
```

Program diatas akan mencetak kalimat `x bilangan positif` jika nilai `x` dalam program bernilai lebih besar dari `0`. Ketika nilai `x` bernilai `0` atau negatif, kalimat tidak akan dicetak.  

Jika ekspresi `if-end` hanya mengubah alur eksekusi ketika memenuhi sebuah kondisi tertentu, kita dapat menggunakan ekspresi `if-else-end` untuk menyatakan alternatif eksekusi dari sebuah kondisi jika kondisi tersebut tidak dipenuhi.

```julia
if x > 0
    println("x bilangan positif")
else
    println(x bukan bilangan positif)
end
```

Tentu saja kita tidak hanya menggunakan sebuah kondisi dalam sebuah percabangan. Percabangan dengan lebih dari satu kondisi dapat dilakukan dengan menggunakan ekspresen `if-elseif-...-elseif-else-end`. Pengecekan kondisi dilaksanakan pada bagian yang mengandung `if` ataupun `elseif`. Perhatikan contoh berikut:

```julia
if x > 0
    println("x bilangan positif")
elseif x < 0
    println("x bilangan negatif")
else
    println("x adalah 0")
end
```

Kode diatas mengecek apakah x (asumsi adalah berupa bilangan) merupakan bilangan positif, negatif, ataupun bernilai tepat nol. Kata kunci `else` tidak wajib dituliskan dalam program. Contoh program berikut ini secara logika sama dengan contoh sebelumnya.

```julia
if x > 0
    println("x bilangan positif")
elseif x < 0
    println("x bilangan negatif")
elseif x == 0
    println("x adalah 0")
end
```

## Percabangan berasarang

Jenis percabangan lainnya merupakan percabangan bersarang, dimana terdapat pernyataan percabangan kembali didalam sebuah blok `if-elseif-else`. 

```julia
if x == y
    println("x sama dengan y")
else
    if x > y
        println("x lebih besar dari y")
    else
        println("x lebih kecil dari y")
    end
end
```

Pada tingkatan terluar, secara logika terdapat dua jalur kondisi yaitu `x == y` dan `x != y` (tersirat pada penryataan `else`). Jalur kondisi `else` ini, kembali mengandung percabangan `if-else` yang menyatakan kondisi bilangan mana yang lebih besar diantara `x` ataupun `y`.

Penggunaan operator logika dapat menyederhanakan bentuk percabangan bersarang. Sebagai contoh kita dapat menyederhanakan pernyataan percabangan berikut:

```julia
if x > 0
    if x < 10
        println("x bilangan positif kurang dari 10")
    end
end
```

Karena fungsi `println()` akan dipanggil jika memenuhi dua kondisi yang ditentukan `x > 0` dan `x < 10`, maka kita dapat menggabungkan kedua kondisi ini kedalam sebuah kondisi dengan menggunakan operator `&&` (AND).

```julia
if x > 0 && x < 10
    println("x bilangan positif kurang dari 10")
end
```

Julia dapat lebih menyederhanakan kembali penulisan kondisi tersebut menjadi:

```julia
if 0 < x < 10
    println("x bilangan positif kurang dari 10")
end
```
