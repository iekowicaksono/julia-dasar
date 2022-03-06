# Variabel dalam `Julia`

Sama seperti dalam notasi matematika, variabel dalam `Julia` dapat menyimpan nilai tertentu. Aturan penamaan variabel dalam `Julia` adalah sebagai berikut:

- Nama variabel pada umumnya mendeskripsikan data yang disimpan. Dapat ditulis dengan karakter huruf kecil maupun kapital.
- Tidak boleh diawali dengan angka.
- Nama variabel dapat mengandung karakter Unicode seperti simbol &#960;, dapat ditulis seperti simbol dalam `LaTex` yaitu dengan mengetikkan `\pi` <kbd>TAB</kbd>, hingga emoji 😊.
- Penggunaan simbol garisbawah (`_`) biasanya digunakan untuk menyambung penulisan nama variabel yang mengandung lebih dari satu kata.
- Nama variabel tidak boleh merupakan salah satu dari **keyword** bawaan bahasa pemrograman `Julia` contohnya seperti `const`, `module`, dll. Lihat [tatuan berikut](https://docs.julialang.org/en/v1/base/base/#Keywords) untuk melihat daftar keyword bawaan bahasa pemrograman `Julia`.

Jika nama variabel yang dibuat tidak memenuhi kriteria, `Julia` REPL akan menghasilkan pesan kesalahan.
