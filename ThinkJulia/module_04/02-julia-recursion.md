# Rekursif

Pada [modul 2](../module_02/) kita telah membahas mengenai fungsi dalam Julia. Dalam sebuah fungsi, diperbolehkan secara sah untuk memanggil fungsi baik fungsi lainnya maupun memanggil kembali fungsi tersebut. Jika sebuah fungsi mengandung pemanggilan dirinya sendiri, fungsi tersebut dapat disebut sebagai fungsi rekursif. Perhatikan contoh berikut.

```julia
function timer(t)
    if t <= 0
        println("Kring-kring....")
    else
        println(t)
        timer(t - 1) # memanggil kembali fungsi timer
    end
end
```

Perhatikan bahwa ketika `t <= 0` (nol atau negatif), fungsi mencetak `"Kring-kring...."`, selain itu fungsi mencetak nilai `t` serta memanggil kembali fungsi `timer` dengan parameter `t - 1`. Contoh program bila dijalankan adalah sebagai berikut:

```console
julia> timer(3)
3
2
1
Kring-kring....
```
