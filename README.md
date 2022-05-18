# Rangkuman Playlist Django 2.2 | Src : Zul Hilmi

## -- Pengenalan ✍️
Django merupakan web framework(kerangka kerja) bersifat open source ditulis menggunakan bahasa python

Django mengikuti pola arsitektur MVT(Model, View, Template)
- Model (Representasi dari database) 
- View (Fungsi – fungsi untuk mengatur proses)
- Template (User interface)

Skill dasar untuk belajar django
- Python
- OOP
- Query sql
- HTML

## -- Workflow 🧬
![image](https://user-images.githubusercontent.com/92994688/168478347-19796773-b7f4-4767-8b63-ee043c9aa496.png)
- Client dapat melakukan request ke Urlconf
- Urlconf memilih view
- View melakukan query set ke Model jika membutuhkan database kemudian memilih template
- Template memberikan response interface ke client.

## -- Kebutuhan 📦
- Cmd/terminal
- Text editor
- Web browser
- Python 
- Django (command installasi :  pip install django/pip install django==“version”).

## -- Membuat Project ⚒️
Membuat project :
- Buka terminal
- Atur path folder
- Jalankan Command : 
```cmd
django-admin startproject ‘nama project’
```
Meaktifkan server :
- Buka terminal
- Atur path folder
- Jalankan command : 
```cmd
python manage.py runserver
```
## -- Basic Routing 🔀
Untuk membuat routing  dapat dilakukan pada file ‘urls.py’ pada project django.

![image](https://user-images.githubusercontent.com/92994688/168478503-ddeff0c4-0ee7-4fbf-9abd-df172f96b17b.png)

Contoh routing sederhana :
```py
from django.contrib import admin
from django.urls import path
from perpustakaan.views import buku, penerbit

urlpatterns = [
    path('admin/', admin.site.urls),
    path('buku/', buku),
    path('penerbit/', penerbit),
]
```

## -- Membuat Apps 💻
Apps menghandle model, view, urlconf, dan template pada django. 

Untuk membuat app dapat dilakukan pada terminal sesuai dengan path folder
Command untuk membuat app :
```cmd
Django-admin startapp perpustakaan
```
atau
```cmd
Python manage.py startapp pepustakaan
```
Configurasi apps :
- Pergi ke file settings.py
- Tambahkan nama app pada bagian INSTALLED_APPS.
```py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'nama apps',
]
```

## -- Membuat Views ⚙️
Untuk membuat views bisa dilakukan pada file views.py pada apps yang dibuat.

![image](https://user-images.githubusercontent.com/92994688/168479236-75b53b41-24a5-423a-909a-301664449e7f.png)

Contoh view sederhana yang mengembalikan file template
```py
def penerbit(request):
    return render(request, 'penerbit.html')
```
kemudian mengatur urls.py untuk mengakses view.
```py
path('penerbit/', penerbit),
```

## -- Templates 🔲
Template merupakan file hmtl atau tampilan interface dari web yang dibuat.

Config templates :
- Settings.py bagian templates
- Isi value dari ‘DIRS’ ke nama folder templates yang kita buat.
```py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': ['templates'],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
### Django Template Language
- Substitute Variabel
- Filter
- Tags/Control Flow
### Templates Extending
kita dapat membuat folder templates base html, sederetan folder project dan apps.
dan untuk folder templates content dapat dibuat didalam folder apps.

berguna untuk membuat struktur folder yang lebih baik dan tak terjadi pengulangan penulisan code yang sama.

## -- Static files 🗃️
Static files digunakan untuk menyimpan file css, js, dan gambar.

## -- Database 🗄️
Setelah pertama kali melakukan runserver pada project django, by default django telah membuat database dengan menggunakan dbms Sqlite3.

Config default database django pada settings.py :
```py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

### Setup database jika ingin menggunakan Mysql :
- Install mysql (mysql, python connector)
- Create database pada cmd dari Mysql
- Lakukan Config pada file settings.py bagian database : 
```py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'nama database',
        'USER': 'root',
        'PASSWORD': 'password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### Command untuk melakukan migrasi (menyebarkan / menginisialisasi tabel – tabel kedalam database.) :
```cmd
Python manage.py makemigrations
```
Lalu,
```cmd
Python manage.py migrate
```

## -- Models 📟
Models merupakan definitive dari database atau representasi tabel pada database. Dengan menggunakan models, kita tidak perlu lagi menggunakan Query SQL untuk membuat tabel di database. Kita dapat melakukan Migrasi pada model, maka Django akan melakukan Create Tabel Sesuai dengan field – field yang ada pada models.

### Foreign Keys
Foreign keys digunakan untuk untuk membuat relasi antar tabel dalam database relational.

bentuk umum :
```
nama_field = models.ForeignKey(class_model, on_delete=models.CASCADE)
```

### Django Admin
Untuk membuat django admin kita dapat menjalankan command berikut pada terminal project kita :
```cmd
Python manage.py createsuperuser
```
Untuk melakukan register model dapat dilakukan pada file admin.py pada apps. Contoh :
```py
from django.contrib import admin
from perpustakaan.models import Buku, Kelompok

admin.site.register(Buku)
admin.site.register(Kelompok)
```

lalu kemudian isi data sesuai ketentuan yang diminta.

### ORM (Object Relation Mapping)
### Forms

## -- CRUD 📝

### Menambah Data
### Mengubah Data
### Hapus Data

## -- Authentication : Login & Logout 🧔‍♂️
## -- Akses Username Pada Template 🔲
## -- Signup / Tambah User 📲
## -- Upload File 📑
## -- Export File 📑
## -- Virtual Environment 📦
## -- Deployment 🧿
### Persiapan
### Deployment
