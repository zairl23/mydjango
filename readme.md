Learning Django
===============

### create a new project

    django-admin startproject mysite

### super user account record.

python manage.py createsuperuser

admin

admin@admin.com

root123456


### Start server

    python manage.py runserver [9000]

### Create a app

    python manage.py startapp polls

### Database

    python manage.py migrate

### Models

polls/models.py
    
    from django.db import models


    class Question(models.Model):
        question_text = models.CharField(max_length=200)
        pub_date = models.DateTimeField('date published')


    class Choice(models.Model):
        question = models.ForeignKey(Question, on_delete=models.CASCADE)
        choice_text = models.CharField(max_length=200)
        votes = models.IntegerField(default=0)


### Include tha app

mysite/settings.py

    INSTALLED_APPS = [
        'polls.apps.PollsConfig',
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
    ]

### Migrate

    python manage.py makemigrations polls

show the sql 

    python manage.py sqlmigrate polls 0001

take the migrate

    python manage.py migrate

### Playing with the API

    python manage.py shell

### Generatic view

https://docs.djangoproject.com/en/1.11/ref/class-based-views/generic-display/#django.views.generic.detail.DetailView

### Contenttype

https://docs.djangoproject.com/en/1.11/ref/class-based-views/generic-display/#django.views.generic.detail.DetailView