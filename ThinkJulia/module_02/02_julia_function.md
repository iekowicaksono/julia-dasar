# Sub-program (fungsi) dalam Julia (2)

Pada [materi pendahuluan](01_julia_function.md) terkait fungsi dalam `Julia` sebelumnya, kita membahas mengenai bagaimana fungsi dalam `Julia` dipanggil. Kita memanggil fungsi bawaan dalam julia dengan menyebutkan nama fungsi dan menspesifikasikan paramter (argumen) yang sesuai.

Pada meteri ini akan membahas bagaimana prosedur membuat fungsi yang kita definisikan sendiri dalam `Julia`. Perhatikan contoh berikut:

```Julia
function hello()
    println("Halo!")
end
```

Contoh diatas merupakan fungsi sederhana bernama `hello` (dan fungsi tidak menerima parameter) yang jika dipanggil akan mencetak "Halo!" di layar console. Kita dapat mendefinisikan fungsi melalui REPL maupun pada file skrip julia (ini akan kita bahas pada pembahasan yang lainnya).

Untuk mendefinisikan fungsi melalui REPL, kita menyatakannya menggunakan kata kunci `function` diikuti dengan nama fungsi dan definisi variabel argumen (jika ada). Jika kita mengetikkan kata kunci `function` pada REPL, secara otomatis kata kunci `end` akan mengakhiri definisi fungsi.

```bash
julia> function hello()
       println("Halo!")
       end
hello (generic function with 1 method)
julia> hello()
Halo!
```

Definisi fungsi yang dilakukan pada REPL (atau konsol interaktif) berlaku dalam sesi yang sama. Jika REPL ditutup, fungsi yang telah kita definisikan pada sesi terdahulu tidak dapat digunakan kembali. Kita harus mendefinisikan kembali fungsi tersebut pada sesi yang baru. Untuk itu, kita dapat menulis fungsi dalam skrip julia yang dapat dijalankan setiap kali kita membuat sesi baru tanpa perlu menuliskan kembali definisi fungsinya.

Dalam definisi sebuah fungsi, kita juga dapat melakukan pemanggilan fungsi lainnya yang didefinisikan sebelumnya (pada sesi yang sama), ataupun fungsi itu sendiri (rekursif&mdash;akan dibahas pada materi tersendiri).

```bash
julia> function greetings(name)
       hello()
       hello()
       println("Apa kabar ", name)
       end
greetings (generic function with 2 methods)
julia> greetings("Andi")
Halo!
Halo!
Apa kabar Andi
```

Pada kode diatas, kita membuat fungsi `greetings` yang menerima sebuah parameter yang disimpan dalam variabel `name`. Dalam fungsi, kita memanggil fungsi Pemanggilan fungsi `halo()` sebanyak dua kali, lalu mencetak `Apa kabar` dan dilanjutkan dengan isi variabel `nama` yang nantinya akan diisi dengan nilai yang diberikan saat fungsi `greetings` dipanggil. Perlu dicatat juga, bahwa argumen/variabel `nama` merupakan variabel lokal, yang hanya dapat diakses dalam blok fungsi tersebut.

Dalam konsep matematika, fungsi bertujuan untuk memetakan sebuah nilai ke nilai lainnya. Sama halnya dalam pemrograman, fungsi pada umumnya mengembalikan sebuah nilai jika dipanggil. Namun, coba perhatikan dengan baik fungsi `hello` dan `greetings` yang telah kita definsikan sebelumnya. Kedua fungsi ini tidak menghasilkan sebuah nilai. Kedua fungsi ini hanya mencetak ke layar tanpa menghasilkan sebuah nilai. Tidak seperti fungsi bawaan `Julia` yang telah kita gunakan pada pembahasan sebelmumnya seperti fungsi `log`, `sin`, `sqrt`, dan lain sebagainya. Fungsi yang tidak mengembalikan sebuah nilai sering disebut sebagai fungsi `void`. Fungsi yang bersifat `void` tidak mengembalikan nilai (`nothing`).

```bash
julia> result = greetings("Mawar")
Halo!
Halo!
Apa kabar Mawar
julia> show(result)
nothing
```

Fungsi `show` dapat menunjukkan pada kita nilai yang disimpan dalam sebuah variabel. Dalam hal ini, variabel `result` seharusnya berisi nilai kembalian dari pemanggilan fungsi `greetings`. Namun, karena fungsi `greetings` ini merupakan fungsi `void`, variabel `result` memang seharusnya tidak berisi sebuah nilai. Dalam `Julia`, `nothing` merupakan  tipe data khusus yang menyatakan bahwa sebuah variabel tidak berisi sebuah nilai (kosong).
