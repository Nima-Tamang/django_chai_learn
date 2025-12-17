virtual set up
python  -m venv venv
venv\Scripts\activate

pip install Django
pip freeze > requirements.txt

To create Django-admin
django-admin startproject chaiheadq
cd chaiheadq
python manage.py runserver (port_number)

python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser
nimadorjetamang
IforgetPasswordEveryTime



#in setting, copy the change and urls too
import os for input 

#create app
python manage.py startapp tweet

create url in tweet/urls.py
from . import views
from django.urls import path
urlpatterns = [
    # path('', admin.site.urls),
    path('',views.index, name = 'index')
] 

in tweet/views.py
from django.shortcuts import render

# Create your views here.

def index(request):
    return render(request, 'index.html')

create folder templates/ in tweet

in chaihq 
urls.py set project
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('tweet/', include('tweet.urls'))
] + static(settings.MEDIA_URL,document_root = settings.
MEDIA_ROOT)


Go to chaiheadhq/settings..
install tweet
and configure media assets
 'DIRS': [os.path.join(BASE_DIR,'templates')],

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR,'media')

STATIC_URL = 'static/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')




