# Operator, Ekspresi, dan Peryataan dalam Julia

**Eksperesi** merupakan kombinasi dari nilai, variabel, dan operator. Contoh ekspresi dalam `Julia`:

```bash
julia> 3.14
3.14
julia> jarijari
10
julia> 3.14 * jarijari * jarijari
314
```

Jika menggunakan REPL, ekspresi akan dievaluasi sehingga kita dapat melihat nilai dari sebuah ekspresi. Dalam contoh sebelumnya, nilai variabel `jarijari` adalah `10`, maka `3.14 * jarijari * jarijari` bernilai `314`.

**Pernyataan** dalam `Julia` merupakan unit terkecil dalam program yang memberikan sebuah efek tertentu. Contohnya seperti memberikan nilai kedalam sebuah variabel dan melakukan evaluasi fungsi.

```bash
julia> jarijari = 10
10
julia> println(jarijari)
10
```

Perlu dicatat bahwa, dalam mode eksekusi skrip program (bukan menggunakan REPL), nilai sebuah ekspresi dan pernyataan tidak akan ditampilkan kecuali kita mencetaknya ke layar dengan fungsi mencetak ke layar seperti `println()`.

Sebuah ekspresi dapat mengandung satu atau lebih operator. Urutan evaluasi operator dalam `Julia` mengikuti kaidah evaluasi operator matematika pada umumnya. Aturan ini sering disebut sebagai aturan **PEMDAS**:

- **P**arenthesis (dalam kurung) memiliki prioritas tertinggi dalam evaluasi ekspresi.
- Selanjutnya adalah **E**xponentiation (pangkat).
- Diikuti dengan **M**ultiplication dan **D**ivison.
- Lalu yang terakhir adalah operator **A**ddition `+` dan **S**ubstraction `-`.
- Aturan pelengkap nya, jika ada operator yang memiliki prioritas yang sama, maka urutan evaluasi dimulai dari kiri menuju kanan.

Pada dasarnya operator dalam `Julia` digunakan untuk melakukan operasi matematika. Namun, selain operasi matematika, beberapa operator matematika dapat diterapkan pada tipe data `String`. Contoh operator yang berlaku untuk tipe data `String` dalam `Julia` adalah sebagai berikut:

```bash
julia> str_a = "Belajar"
"Belajar"
julia> str_b = "Julia"
"Julia"
julia> str_a * str_b
"BelajarJulia"
```

Dapat dilihat bahwa operator perkalian `*` dalam tipe data `String` berperan untuk melakukan penyambungan antara dua buah `String`. Selain itu, operator pangkat `^` dalam tipe data `String` dapat melakukan duplikasi `String`.

```bash
julia> str_a = "Belajar"
"Belajar"
julia> str_a ^ 3
"BelajarBelajarBelajar"
```

Komentar dalam bahasa `Julia` diawali dengan simbol pagar `#`. Dalam skrip program, disarankan untuk menuliskan komentar untuk memberikan penjelasan kode yang tidak secara eksplisit jika dilihat dari kode.

Beberapa operator aritmatika lain dalam julia adalah `÷` atau `\div` <kbd>TAB</kbd> (hasil bagi pembulatan kebawawah), `/` (hasil bagi pecahan) dan `%` (sisa bagi). Perhatikan contoh berikut:

```bash
julia> t_detik = 90
70
julia> t_menit_pecahan = t_detik / 60
1.5
julia> t_menit_integer = t_detik ÷ 60
1
julia> t_detik_sisa = t_detik % 60
30
```