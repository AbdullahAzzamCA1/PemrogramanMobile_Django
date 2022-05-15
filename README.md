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
## -- Static files 🗃️
Static files digunakan untuk menyimpan file css, js, dan gambar.
## -- Database 🗄️
## -- Models 📟
## -- CRUD 📝
## -- Authentication : Login & Logout 🧔‍♂️
## -- Akses Username Pada Template 🔲
## -- Signup / Tambah User 📲
## -- Upload File 📑
## -- Export File 📑
## -- Virtual Environment 📦
## -- Persiapan Deployment 🧿
## -- Deployment 🧿
