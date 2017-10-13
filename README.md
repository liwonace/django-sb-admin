# django-sb-admin

Introduction
------------

Django SB Admin is a resuable Django app which provides a Bootstrap 3 SB Admin dashboard theme:

http://startbootstrap.com/template-overviews/sb-admin/

SB Admin is a free to download Bootstrap admin template. This template uses the
default Bootstrap 3 styles along with a variety of powerful jQuery plugins to 
create a powerful framework for creating admin panels, web apps, or back-end dashboards.

This Installation checked with python3.6.1 on CentOS 6.7 64bit.

Installation
------------
1. Make django project::

    django-admin startproject (project name)
    cd (projectname)

2. Add "django_sb_admin" to your INSTALLED_APPS setting like this::

	vim (projectname)/settings.py

	ALLOWED_HOSTS = ['*']

	skip...
		
	INSTALLED_APPS = [
		'django.contrib.admin',
		'django.contrib.auth',
		'django.contrib.contenttypes',
		'django.contrib.sessions',
		'django.contrib.messages',
		'django.contrib.staticfiles',
		'django_sb_admin',
	]

	skip...

3. If you want to see an example app, add following to your urls file::

	vim sb/urls.py 

	from django.conf.urls import url, include
	from django.contrib import admin
	from . import views

	urlpatterns = [
		url(r'^admin/', admin.site.urls),
		url(r'^django-sb-admin/', include('django_sb_admin.urls')),
	]

4. download package and copy to your project::

	pip install django-sb-admin  

	cp -rf /root/anaconda3/lib/python3.6/site-packages/django_sb_admin .

5. copy file::

	cp django_sb_admin/views.py (projectname)/

6. migrate and run server::

	python manage.py migrate
	python manage.py runserver 0.0.0.0:8080

7. Check URL connection::

	http://192.168.7.52:8080/django-sb-admin/

