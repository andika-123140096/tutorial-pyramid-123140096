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

Berdasarkan pengamatan saya, di guide ini kita diberitahu kalo kita bisa menghemat baris kode dengan cara menulis default view nya di atas kelas. Ini bisa digunakan di dalam kasus beberapa fungsi menggunakan template yang sama.

## 10: Handling Web Requests and Responses

Berdasarkan pengamatan saya, di guide ini kita diberitahu bagaimana cara mendapatkan data dari web request. dalam kasus yg diberikan, kode mencoba mendapatkan data nama kemudian melakukan render html menggunakan data tersebut.

## 11: Dispatching URLs To Views With Routing

Berdasarkan pengamatan saya, di guide ini kita diberitahu bagaimana cara mendapatkan multi parameter dari request kemudian melakukan render html menggunakan data dari parameter tersebut.

## 12: Templating With jinja2

Berdasarkan pengamatan saya, di guide ini kita diberitahu bagaimana cara menggunakan engine template lain yaitu `jinja2`. Syntax nya hampir mirip dengan template yang default.

## 13: CSS/JS/Images Files With Static Assets

Berdasarkan pengamatan saya, di guide ini kita diberitahu bagaimana caranya menggunakan templating untuk melakukan embed file. Alasannya supaya lebih tidak repot ketika foldernya berubah, karena URL file nya akan digenerate oleh pyramid, berbeda dengan ketika menulis URL file nya manual.

## 14: AJAX Development With JSON Renderers

Di guide ini kita mengetahui bahwa kita bisa menggunakan custom renderer json untuk merender json. Kemudian kita bisa melakukan overriding default config.

## 15: More With View Classes

Di guide ini kita mengetahui bahwa kita bisa mengimplementasikan custom request method dan custom form parameter ke views yang kita buat. Contohnya seperti POST dan DELETE. jadi satu route yaitu /hello bisa menerima beberapa jenis request, tinggal digabung aja jadi satu class.

## 16: Collecting Application Info With Logging

Di guide ini kita mengetahui bahwa kita bisa menghidupkan sebuah logger dengan menggunakan konfigurasi pyramid. Dengan menggunakan logger kita bisa memantau aktivitas dari terminal.

## 17: Transient Data Using Sessions

Di guide ini kita mengetahui cara menambahkan session di dalam object request. guna nya itu untuk menyimpan state yang dilakukan pengguna di server web. misal di contoh itu menyimpan state counter, tapi di dunia nyata biasanya untuk menyimpan state apakah user udah login atau belum.

## 18: Forms and Validation with Deform

Di guide ini kita mengetahui cara menambahkan deform untuk melakukan validasi data yang dimasukkan ke dalam form.

Kita membuat schema dulu, terus inisiasi deform menggunakan schema tersebut. Dalam guide ini, schema nya adalah berikut:

```python
class WikiPage(colander.MappingSchema):
    title = colander.SchemaNode(colander.String())
    body = colander.SchemaNode(colander.String(), widget=deform.widget.RichTextWidget())

```

Nah enaknya itu the rest kita cuma panggil fungsi validate aja. Contohnya:

```python
@view_config(route_name="wikipage_add", renderer="wikipage_addedit.pt")
    def wikipage_add(self):
        form = self.wiki_form.render()

        if "submit" in self.request.params:
            controls = self.request.POST.items()
            try:
                appstruct = self.wiki_form.validate(controls)
            except deform.ValidationFailure as e:
                # Form is NOT valid
                return dict(form=e.render())

            # Form is valid, make a new identifier and add to list
            last_uid = int(sorted(pages.keys())[-1])
            new_uid = str(last_uid + 1)
            pages[new_uid] = dict(
                uid=new_uid, title=appstruct["title"], body=appstruct["body"]
            )

            # Now visit new page
            url = self.request.route_url("wikipage_view", uid=new_uid)
            return HTTPFound(url)

        return dict(form=form)
```

## 19: Databases Using SQLAlchemy

Di dalam guide ini kita menginstall package pyramid_tm dan zope.sqlalchemy. Untuk package zope.sqlalchemy itu untuk menghubungkan pyramid dengan database, i guess ini sqlite.

Kemudian kalo pyramid_tm itu untuk mempermudah kita melakukan transaction. Transaction di dalam database itu secara simpelnya untuk menyediakan checkpoint, misal kita menambahkan sesuatu ke table, kemudian terjadi error. nah itu bisa dirollback jika menggunakan transaction. Dalam kasus ini kita disuruh menambahkan aja ke pyramid, tidak secara explisit ada kode yg menggunakan, jadi saya asumsikan ini terjadi mekanisme otomatis.

Nah database kita itu disimpan di `databases/sqltutorial.sqlite`. Kita awalnya mendifinisikan sebuah model, kemudian kita bisa melakukan migrate supaya class yg kita buat berubah menjadi table di database.

```python
from pyramid.authorization import Allow, Everyone

from sqlalchemy import (
    Column,
    Integer,
    Text,
)

from sqlalchemy.ext.declarative import declarative_base

from sqlalchemy.orm import (
    scoped_session,
    sessionmaker,
)

from zope.sqlalchemy import register

DBSession = scoped_session(sessionmaker())
register(DBSession)
Base = declarative_base()


class Page(Base):
    __tablename__ = "wikipages"
    uid = Column(Integer, primary_key=True)
    title = Column(Text, unique=True)
    body = Column(Text)


class Root:
    __acl__ = [(Allow, Everyone, "view"), (Allow, "group:editors", "edit")]

    def __init__(self, request):
        pass
```

## 20: Logins with authentication

Di dalam guide ini kita mengetahui cara menginstall bcrypt yang gunanya untuk hashing password user. Nah berbeda dengan SHA-256 atau sejenisnya. Bcrypt ini memiliki secret key jika kita lihat di `development.ini`. Tapi itu sebenarnya sebuah salt, karena kalo secret_key berarti hashnya bisa didecrypt jika kita mengetahui dong. Tapi faktanya tidak bisa, salt itu menambahkan kekuatan cryptography nya.

Kemudian kita menggunakan AuthTktCookieHelper agar pyramid menyimpan data nya di cookies. Nah cookies ini dienkripsi dengan secret_Key, jadi kalo ada orang mengetahui secret_key maka dia bisa membuat session custom.

```
5ce0756e13e79f5453d9c9180e0160ef80c6ee2962e4e7fbc3a2f4a959cafbae0a270afc915228a9759f238a8639b237117a21efad6f2f75c31c0dbaf9375354690573e2ZWRpdG9y!userid_type:b64unicode
```

Enaknya dengan menggunakan helper itu kita cukup panggil beberapa method aja, dan langsung bekerja.

```python
import bcrypt
from pyramid.authentication import AuthTktCookieHelper


def hash_password(pw):
    pwhash = bcrypt.hashpw(pw.encode("utf8"), bcrypt.gensalt())
    return pwhash.decode("utf8")


def check_password(pw, hashed_pw):
    expected_hash = hashed_pw.encode("utf8")
    return bcrypt.checkpw(pw.encode("utf8"), expected_hash)


USERS = {"editor": hash_password("editor"), "viewer": hash_password("viewer")}


class SecurityPolicy:
    def __init__(self, secret):
        self.authtkt = AuthTktCookieHelper(secret=secret)

    def identity(self, request):
        identity = self.authtkt.identify(request)
        if identity is not None and identity["userid"] in USERS:
            return identity

    def authenticated_userid(self, request):
        identity = self.identity(request)
        if identity is not None:
            return identity["userid"]

    def remember(self, request, userid, **kw):
        return self.authtkt.remember(request, userid, **kw)

    def forget(self, request, **kw):
        return self.authtkt.forget(request, **kw)
```

## 21: Protecting Resources With Authorization
