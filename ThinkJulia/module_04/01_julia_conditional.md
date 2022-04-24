# Kondisi dan Percabangan dalam Julia

Dalam bahasa pemrograman pada umumnya, kondisi dinyatakan dengan menggunakan operator pembanding dan juga operator boolean. Sebuah ekspresi boolean bernilai `true` (benar) atau `false` (salah). Dalam contoh berikut, kita menggunakan operator pembanding `==` (kesamaan antara dua nilai), dimana ekspresi menghasilkan nilai boolean.

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

```python
x != y          # x tidak sama dengan y
x ≠ y           # x tidak sama dengan y juga! (cara menulis operator \ne <kbd>TAB</kbd>)
x > y           # x lebih besar dari y
x < y           # x lebih kecil dari y
x >= y          # x lebih besar sama dengan y
x ≥ y           # lebih besar sama dengan (\ge <kbd>TAB</kbd>)
x <= y          # x lebih kecil sama dengan y
x ≤ y           # lebih kecil sama dengan (\le <kbd>TAB</kbd>)
```