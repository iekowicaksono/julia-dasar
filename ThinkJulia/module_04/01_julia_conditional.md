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

Dalam menulis program kita membutuhkan kemampuan untuk melakukan kontrol terhadap alur eksekusi program yang mengakibatkan perubahan alur eksekusi (sering disebut juga sebagai percabangan) yang diinginkan. Dengan menggunakan kata kunci `if`, kita dapat melakukan perubahan alur eksekusi program.

```julia
if x > 0
    println("x bilangan positif")
end
```

Program diatas akan mencetak kalimat `x bilangan positif` jika nilai `x` dalam program bernilai lebih besar dari `0`. Ketika nilai `x` bernilai `0` atau negatif, kalimat tidak akan dicetak.  