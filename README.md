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
