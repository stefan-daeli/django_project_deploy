### ```local_settings.py``` configuration
```
cd /django_project/config/
```
```
sudo nano local_settings.py
```
```
from pathlib import Path

BASE_DIR = Path(__file__).resolve().parent.parent

#domain & shh server
HOST_CONFIG = ['domain.com', '00.00.00.000']
DEBUG_CONFIG = False
TEMPLATES_CONFIG = 'templates'
#database
DB_CONFIG = {
    'ENGINE': 'django.db.backends.mysql',
    'NAME': 'database_name',
    'HOST' : 'localhost',
    'USER' : 'root',
    'PASSWORD' : 'password',
    'PORT' : '3306'
}
#static
STATIC_URL_CONFIG = '/static/'
STATIC_ROOT_CONFIG = BASE_DIR / "staticfiles"
CORS_CONFIG = [
    "https://domain.com",
]
```
### ```settings.py``` configuration
```
sudo nano settings.py
```
- import libraries
```
from pathlib import Path
from .local_settings import *
import os
```
- debug configuration
```
DEBUG = DEBUG_CONFIG
```
- host configuration
```
ALLOWED_HOSTS = HOST_CONFIG
```
- apps register
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    #app
    'app',
]
```
- set directories
```
mkdir templates
```
```
mkdir static
```
```
mkdir media
```
- templates configuration
```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [BASE_DIR / TEMPLATES_CONFIG],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
                "apps.sources.utils.context_processors.developer_active",
            ],
        },
    },
]
```
- database configuration
```
DATABASES = {
    'default': DB_CONFIG
}
```
- static configuration
```
STATIC_URL = STATIC_URL_CONFIG
STATIC_ROOT = STATIC_ROOT_CONFIG
```
- media configuration
```
MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
```
### ```urls.py``` configuration
```
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('app.urls')),

]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```
### ```app/urls.py``` configuration
```
from django.urls import path

urlpatterns = [
    #create new url here
]
```

