### Nama: Andika Dinata

### NIM: 123140096

### Kelas: RA

## 01: Single-File Web Applications

Menurut analisa saya, pada guide ini saya diajarkan tentang cara melakukan setup awal framework pyramid.

Kemudian ada beberapa line kode yang bisa saya jelaskan.

Line 13 itu kita membuat sebuah route, route disini fungsinya supaya framework menangkap request dari path tersebut. path yg ingin ditangkap di kode tersebut adalah /

Line 14 itu kita membuat sebuah view, view disini fungsinya meneruskan request dari sebuah route ke sebuah fungsi yang kita buat untuk menampilkan sebuah response, responnya bisa berupa html seperti di contoh kode.

Ketika saya buka halaman http://localhost:6543/ muncul teks Hello, world!

Saya udah setup venv, tapi folder .venv nya tidak saya commit juga hehe.

## 02: Python Packages for Pyramid Applications

Oke, disini kita disuruh menambahkan file setup.py yang isinya itu menurut sepemahaman saya sebuah kode yg mengecek dependency python yg dibutuhkan apakah sudah terinstall apa belum.

Ketika saya menjalankan command di bawah ini.

```
cd package
pip install -e .
```

tebakan saya benar bahwa fungsinya untuk mengecek dependency yang dibutuhkan apakah sudah terinstall atau belum.

Kemudian saya coba menjalankan file app.py di `package/tutorial`. Hasilnya sama seperti guide yang pertama, ini menampilkan Hello, world!

## 03: Application Configuration with .ini Files

Disini kita melakukan copy folder sebelumnya kemudian menambahkan sebuah line code di setup.py yang menurut analisa saya ini untuk menentukan entry point dari app nya.

Kemudian kita merefactor `__init__.py` dan menghapus app.py

Menurut pemahaman saya kenapa harus dipindah, karena di konfigurasi yg ada di setup itu kita menulis tutorial:main. kalo kodenya tetap di app.py berarti harus nulis tutorial.app:main.

Hmm. Inti dari guide ini menurut saya untuk kita mengetahui kalau kita bisa melakukan konfigurasi menggunakan file .ini

## 04: Easier Development with debugtoolbar

Berdasarkan pengamatan saya, di guide ini kita diberitahu cara menginstall debugtoolbar supaya memudahkan kita melakukan pengembangan web karena errornya lebih mudah ditracking menggunakan alat ini.

Kemudian alasan kenapa menggunakan extra require karena kita perlu menambahkan flag dev di confignya, tujuannya supaya alat ini diinstall saat pengembangan aja.

## 05: Unit Tests and pytest

Berdasarkan pengamtan saya, di guide ini kita diberitahu cara menginstall pytest agar kita bisa melakukan pengetesan secara otomatis. Maksudnya otomatis itu kita cukup menjalankan scripy python lain untuk menguji kita error atau ga, lebih akurat dibandingkan manual seharusnya.

## 06: Functional Testing with WebTest

Berdasarkan pengamatan saya, di guide ini kita diberitahu cara menginstall webtest agar kita bisa melakukan pengujian otomatis ke suatu halaman web. misal halaman / harus menampilkan Hello, world! maka dengan menggunakan tools ini kita bisa mengujinya menggunakan script python.

## 07: Basic Web Handling With Views

Berdasarkan pengamatan saya, di guide ini kita diberitahu kalau cara yang bagus itu memisah views sebagai file terpisah. Contoh kode menunjukkan dengan cara menulis route di views.py kemudian menambahkan kode untuk scan .views di app.py

## 08: HTML Generation With Templating

Berdasarkan pengamatan saya, di guide ini kita diberitahu kalau kita bisa melakukan cara yang lebih efisien untuk menampilkan html. yaitu dengan cara membuat 1 template html kemudian menggunakannya berulang, jadi kita cukup memasukkan data saja ke dalamnya.

di dalam kode nya kita menggunakan decorator @view_config untuk melakukan hal tersebut.

## 09: Organizing Views With View Classes
