# Pemrograman Mobile - Codelab #06
Codelab #6 - Layout dan Navigasi
NIM: 2341720083
Nama: Afrizal Qurratul Faizin

## Praktikum 1
### Langkah 1
Buatlah sebuah project flutter baru dengan nama layout_flutter. Atau sesuaikan style laporan praktikum yang Anda buat.

### Langkah 2: Buka file lib/main.dart

![1-1](img/Praktikum1/Langkah1.png)

### Langkah 3 & 4
Selanjutnya, buat diagram setiap baris. Baris pertama, disebut bagian Judul, memiliki 3 anak: kolom teks, ikon bintang, dan angka. Anak pertamanya, kolom, berisi 2 baris teks. Kolom pertama itu memakan banyak ruang, sehingga harus dibungkus dengan widget yang Diperluas.

Baris kedua, disebut bagian Tombol, juga memiliki 3 anak: setiap anak merupakan kolom yang berisi ikon dan teks.

Setelah tata letak telah dibuat diagramnya, cara termudah adalah dengan menerapkan pendekatan bottom-up. Untuk meminimalkan kebingungan visual dari kode tata letak yang banyak bertumpuk, tempatkan beberapa implementasi dalam variabel dan fungsi.

Pertama, Anda akan membuat kolom bagian kiri pada judul. Tambahkan kode berikut di bagian atas metode build() di dalam kelas MyApp

![1-4](img/Praktikum1/Langkah3-4.png)

## Praktikum 2
### Langkah 1
Bagian tombol berisi 3 kolom yang menggunakan tata letak yang sama—sebuah ikon di atas baris teks. Kolom pada baris ini diberi jarak yang sama, dan teks serta ikon diberi warna primer.

Karena kode untuk membangun setiap kolom hampir sama, buatlah metode pembantu pribadi bernama buildButtonColumn(), yang mempunyai parameter warna, Icon dan Text, sehingga dapat mengembalikan kolom dengan widgetnya sesuai dengan warna tertentu.

`lib/main.dart (_buildButtonColumn)`

![2-1](img/Praktikum2/Langkah1Code.png)

Tidak ada perubahan pada aplikasi secara visual.

### Langkah 2
Buat Fungsi untuk menambahkan ikon langsung ke kolom. Teks berada di dalam Container dengan margin hanya di bagian atas, yang memisahkan teks dari ikon.

Bangun baris yang berisi kolom-kolom ini dengan memanggil fungsi dan set warna, Icon, dan teks khusus melalui parameter ke kolom tersebut. Sejajarkan kolom di sepanjang sumbu utama menggunakan MainAxisAlignment.spaceEvenly untuk mengatur ruang kosong secara merata sebelum, di antara, dan setelah setiap kolom. Tambahkan kode berikut tepat di bawah deklarasi titleSection di dalam metode build():

![2-2](img/Praktikum2/Langkah2Code.png)

Tidak ada perubahan pada aplikasi secara visual.

### Langkah 3
Tambahkan variabel buttonSection ke dalam body seperti berikut:

![2-3](img/Praktikum2/Langkah3.png)

## Praktikum 3
Tentukan bagian teks sebagai variabel. Masukkan teks ke dalam Container dan tambahkan padding di sepanjang setiap tepinya. Tambahkan kode berikut tepat di bawah deklarasi buttonSection, lalu masukkan ke body:

![3-1](img/Praktikum3.png)

## Praktikum 4
### Langkah 1
Anda dapat mencari gambar di internet yang ingin ditampilkan. Buatlah folder images di root project layout_flutter. Masukkan file gambar tersebut ke folder images, lalu set nama file tersebut ke file pubspec.yaml seperti berikut:

![4-1](img/Praktikum4/Langkah1.png)

### Langkah 2
Tambahkan aset gambar ke dalam body seperti berikut

`BoxFit.cover` memberi tahu kerangka kerja bahwa gambar harus sekecil mungkin tetapi menutupi seluruh kotak rendernya.

![4-2](img/Praktikum4/Langkah2.png)

### Langkah 3

Pada langkah terakhir ini, atur semua elemen dalam ListView, bukan Column, karena ListView mendukung scroll yang dinamis saat aplikasi dijalankan pada perangkat yang resolusinya lebih kecil.

![4-3](img/Praktikum4/Langkah3.png)

## Tugas Praktikum 1
1. Selesaikan Praktikum 1 sampai 4, lalu dokumentasikan dan push ke repository Anda berupa screenshot setiap hasil pekerjaan beserta penjelasannya di file README.md!
2. Silakan implementasikan di project baru "basic_layout_flutter" dengan mengakses sumber ini: https://docs.flutter.dev/codelabs/layout-basics

### Jawaban
1. Tertera Diatas

### Basic Layout Flutter

#### Bagian Lay Out a Widget:

![Basic 1](img/TugasPraktikum1/BasicLayouting.png)

#### Lay Out Multiple Widget Vertically and Horizontally

![Layout 1](img/TugasPraktikum1/RowColumn.png)

#### Sizing Widgets

Original:

![Sizing 1](img/TugasPraktikum1/RowColumn.png)

Sized:

![Sizing 2](img/TugasPraktikum1/Rizing.png)

#### Packing

![Packing](img/TugasPraktikum1/Packing.png)

#### Nesting Row & Column

![Nesting](img/TugasPraktikum1/Nesting.png)

#### Common Layouts
##### Containers
![Common Container](img/TugasPraktikum1/CommonContainer.png)

##### Grid View
![Common Grid View](img/TugasPraktikum1/CommonGrid.png)

##### List View
![Common List View](img/TugasPraktikum1/CommonList.png)

##### Stack
![Common Stack](img/TugasPraktikum1/CommonStack.png)

##### Card
![Common Card](img/TugasPraktikum1/CommonCard.png)

## Praktikum 5

Pada praktikum 5 ini anda akan belajar mengenai pembangunan aplikasi bergerak multi halaman. Aplikasi yang dikembangkan berupa kasus daftar barang belanja. Pada aplikasi ini anda akan belajar untuk berpindah halaman dan mengirimkan data ke halaman lainnya. Gambaran mockup hasil akhir aplikasi dapat anda lihat pada gambar di atas (mockup dibuat sederhana, sehingga Anda mempunyai banyak ruang untuk berkreasi). Desain aplikasi menampilkan sebuah ListView widget yang datanya bersumber dari List. Ketika item ditekan, data akan dikirimkan ke halaman berikutnya.

### Langkah-langkah
Sebelum melanjutkan praktikum, buatlah sebuah project baru Flutter dengan nama belanja dan susunan folder seperti pada gambar berikut. Penyusunan ini dimaksudkan untuk mengorganisasi kode dan widget yang lebih mudah.

Buatlah dua buah file dart dengan nama home_page.dart dan item_page.dart pada folder pages. Untuk masing-masing file, deklarasikan class HomePage pada file home_page.dart dan ItemPage pada item_page.dart. Turunkan class dari StatelessWidget.

Setelah kedua halaman telah dibuat dan didefinisikan, bukalah file main.dart. Pada langkah ini anda akan mendefinisikan Route untuk kedua halaman tersebut. Definisi penamaan route harus bersifat unique. Halaman HomePage didefinisikan sebagai /. Dan halaman ItemPage didefinisikan sebagai /item. Untuk mendefinisikan halaman awal, anda dapat menggunakan named argument initialRoute.

Sebelum melakukan perpindahan halaman dari HomePage ke ItemPage, dibutuhkan proses pemodelan data. Pada desain mockup, dibutuhkan dua informasi yaitu nama dan harga. Untuk menangani hal ini, buatlah sebuah file dengan nama item.dart dan letakkan pada folder models. Pada file ini didefinisikan pemodelan data yang dibutuhkan.

Pada halaman HomePage terdapat ListView widget. Sumber data ListView diambil dari model List dari object Item. Untuk menampilkan ListView pada praktikum ini digunakan itemBuilder. Data diambil dari definisi model yang telah dibuat sebelumnya. Untuk menunjukkan batas data satu dan berikutnya digunakan widget Card. Kode yang telah umum pada bagian ini tidak ditampilkan.

Item pada ListView saat ini ketika ditekan masih belum memberikan aksi tertentu. Untuk menambahkan aksi pada ListView dapat digunakan widget InkWell atau GestureDetector. Perbedaan utamanya InkWell merupakan material widget yang memberikan efek ketika ditekan. Sedangkan GestureDetector bersifat umum dan bisa juga digunakan untuk gesture lain selain sentuhan. Pada praktikum ini akan digunakan widget InkWell.

Untuk menambahkan sentuhan, letakkan cursor pada widget pembuka Card. Kemudian gunakan shortcut quick fix dari VSCode (Ctrl + . pada Windows atau Cmd + . pada MacOS). Sorot menu wrap with widget... Ubah nilai widget menjadi InkWell serta tambahkan named argument onTap yang berisi fungsi untuk berpindah ke halaman ItemPage.

![Hasil Praktikum 5](img/Praktikum5.png)

![Hasil Praktikum 5 - Terpilih](img/Praktikum5Selected.png)

## Tugas Praktikum 2
### Nomor 1
Untuk melakukan pengiriman data ke halaman berikutnya, cukup menambahkan informasi arguments pada penggunaan Navigator. Perbarui kode pada bagian Navigator menjadi seperti berikut.

```
onTap: () {
    Navigator.pushNamed(
        context,
        '/item',
        arguments: item,
    );
},
```

### Nomor 2
Pembacaan nilai yang dikirimkan pada halaman sebelumnya dapat dilakukan menggunakan ModalRoute. Tambahkan kode berikut pada blok fungsi build dalam halaman ItemPage. Setelah nilai didapatkan, anda dapat menggunakannya seperti penggunaan variabel pada umumnya.

### Nomor 3
Pada hasil akhir dari aplikasi belanja yang telah anda selesaikan, tambahkan atribut foto produk, stok, dan rating. Ubahlah tampilan menjadi GridView seperti di aplikasi marketplace pada umumnya.

![Hasil Nomor 3](img/TugasPraktikum2/MarketplaceLayout.png)

### Nomor 4

Silakan implementasikan Hero widget pada aplikasi belanja Anda dengan mempelajari dari sumber ini: https://docs.flutter.dev/cookbook/navigation/hero-animations

![Hasil Nomor 4](img/TugasPraktikum2/HeroAnimation.gif)

### Nomor 5
Sesuaikan dan modifikasi tampilan sehingga menjadi aplikasi yang menarik. Selain itu, pecah widget menjadi kode yang lebih kecil. Tambahkan Nama dan NIM di footer aplikasi belanja Anda.

![Hasil Layout](img/TugasPraktikum2/Layout1.png)

![Hasil Layout Page](img/TugasPraktikum2/LayoutOpen.png)

### Nomor 6
Selesaikan Praktikum 5: Navigasi dan Rute tersebut. Cobalah modifikasi menggunakan plugin go_router, lalu dokumentasikan dan push ke repository Anda berupa screenshot setiap hasil pekerjaan beserta penjelasannya di file README.md. Kumpulkan link commit repository GitHub Anda kepada dosen yang telah disepakati!

![Hasil Layout](img/TugasPraktikum2/LayoutWithGp.png)

![Hasil Layout](img/TugasPraktikum2/LayoutWithGoOpen.png)

Penjelasan:

Secara tampilan, tidak ada perubahan pada aplikasi, namun, secara kode, ada perubahan secara signifikan.

```
// main.dart
final _router = GoRouter(
  initialLocation: '/',
  routes: [
    GoRoute(
      path: '/',
      builder: (context, state) => HomePage(),
    ),
    GoRoute(
      path: '/item',
      builder: (context, state) {
        final item = state.extra as Items;
        return ItemPage(item: item,);
      },
    )
  ]
);
```

Pada kode ini, router akan dibuat menggunakan `GoRouter()`, dengan masing-masing path di-route menggunakan `GoRoute()`, menggunakan builder sebagai extra parameter, data dapat di passing/oper jika ingin masuk ke rute `/item`.

```
// Home Page
onTap: () {
    context.push('/item', extra: items[index]);
},
```

Kode ini akan dieksekusi ketika bagian layar di-klik, yang akan melakukan `push` data melalui `context.push()` yang akan mengirim extra parameter berupa data item yang di-klik.

```
// Item Page
final Items item;
const ItemPage({super.key, required this.item});
static const String routeName = '/item';
```

Pada kode ini, konstruktor dirancang ulang dengan objek Items dengan nama item yang akan menjadi parameter setelah key, yang dimana parameter item ini harus ada. Nantinya, data item dapat langsung dipanggil setelahnya menggunakan `item.name`, `item.stock`, dan sebagainya.