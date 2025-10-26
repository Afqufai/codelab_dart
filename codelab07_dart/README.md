# Pemrograman Mobile - Codelab #07
Codelab #6 - Layout dan Navigasi
NIM: 2341720083
Nama: Afrizal Qurratul Faizin

## Praktikum 1
### Langkah 1
Buatlah sebuah project flutter baru dengan nama flutter_plugin_pubdev. Lalu jadikan repository di GitHub Anda dengan nama flutter_plugin_pubdev.

### Langkah 2
Tambahkan plugin auto_size_text menggunakan perintah berikut di terminal

`flutter pub add auto_size_text`

Jika berhasil, maka akan tampil nama plugin beserta versinya di file pubspec.yaml pada bagian dependencies.

### Langkah 3
Buat file baru bernama red_text_widget.dart di dalam folder lib lalu isi kode seperti berikut.

```
import 'package:flutter/material.dart';

class RedTextWidget extends StatelessWidget {
  const RedTextWidget({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Container();
  }
}
```

### Langkah 4
Masih di file red_text_widget.dart, untuk menggunakan plugin auto_size_text, ubahlah kode return Container() menjadi seperti berikut.

```
return AutoSizeText(
      text,
      style: const TextStyle(color: Colors.red, fontSize: 14),
      maxLines: 2,
      overflow: TextOverflow.ellipsis,
);
```

Setelah Anda menambahkan kode di atas, Anda akan mendapatkan info error. Mengapa demikian? Jelaskan dalam laporan praktikum Anda!

### Langkah 5
Tambahkan variabel text dan parameter di constructor seperti berikut.

```
final String text;

const RedTextWidget({Key? key, required this.text}) : super(key: key);
```

### Langkah 6
Buka file main.dart lalu tambahkan di dalam children: pada class _MyHomePageState

```
Container(
   color: Colors.yellowAccent,
   width: 50,
   child: const RedTextWidget(
             text: 'You have pushed the button this many times:',
          ),
),
Container(
    color: Colors.greenAccent,
    width: 100,
    child: const Text(
           'You have pushed the button this many times:',
          ),
),
```

Run aplikasi tersebut dengan tekan F5, maka hasilnya akan seperti berikut.

![Hasil Akhir](img/image.png
)

## Tugas
1. Selesaikan Praktikum tersebut, lalu dokumentasikan dan push ke repository Anda berupa screenshot hasil pekerjaan beserta penjelasannya di file README.md!
2. Jelaskan maksud dari langkah 2 pada praktikum tersebut!
3. Jelaskan maksud dari langkah 5 pada praktikum tersebut!
4. Pada langkah 6 terdapat dua widget yang ditambahkan, jelaskan fungsi dan perbedaannya!
5. Jelaskan maksud dari tiap parameter yang ada di dalam plugin auto_size_text berdasarkan tautan pada dokumentasi ini !

### Jawaban:
1. Terlampir di atas
2. Langkah kedua dilakukan bermaksud untuk menginstall plugin `auto_size_text` dari `pub.dev` kedalam proyek yang akan muncul di dependency
3. Maksud dari langkah kelima adalah membuat variabel final berupa parameter daari konstruktor, const `RedTextWidget({Key? key, required this.text}) : super(key: key);` berperan sebagai konstruktor dengan beberapa requirement berupa teks dengan parameter text yang akan digunakan pada widget teks merah tersebut.
4. Kedua widget yang di tambahkan adalah container yang berisi teks dengan warna background/warna container yang berbeda, kontainer pertama berwarna kuning dengan lebar 50 dan memanggil widget `RedTextWidget` untuk membuat teks menjadi merah dan kontainer kedua berwarna hijau dengan lebar 100 dengan teks normal (berwarna hitam).
5. Parameter yang ada berdasarkan dokumentasi tersebut adalah sebagai berikut:

| Parameter | Deskripsi |
| --------- | --------- |
| textKey | Menetapkan key untuk widget Text yang dihasilkan. |
| minFontSize | Batasan ukuran teks minimum yang digunakan saat penyesuaian ukuran otomatis. |
| maxFontSize | Batasan ukuran teks maksimum yang digunakan saat penyesuaian ukuran otomatis. |
| stepGranularity | Ukuran langkah penyesuaian ukuran font terhadap batasan yang ada. |
| presetFontSizes | Mendefinisikan semua kemungkinan ukuran font di awal. |
| group | Sinkronisasi ukuran dari beberapa AutoSizeText. |
| wrapWords | Menentukan apakah kata-kata yang tidak muat dalam satu baris dipindahkan ke baris baru. Nilai default-nya true agar sama seperti Text. |
| overflowReplacement | Jika teks overflow dan tidak muat, widget ini ditampilkan sebagai gantinya. |