---
date: 2024-11-05 02:34
sources: "[[SyncWise]]"
tags:
  - zettel
  - software-dev
status: literature
publish: true
---
# django-rest-framework

## Steps 
**Step-1:** create python env 
```
python -m venv .venv
```

**Step-2:** activate environment
```
# Mac OS
source .venv/bin/activate  
```

**Step-3:** install libraries
```
pip install django djangorestframework environs
```

**Step-4:** freeze it to requirements.txt
```
pip freeze > requirements.txt
```

**Step-5:** create a django project 
```
django-admin startproject <myproject>
```

**Step-6:** change dir into the project 
```
cd <myproject>
```

**Step-7:** create an app for the api 
```
python manage.py startapp api
```

**Step-8:** update settings.py
```python
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "api",
    "rest_framework",
]
```

**Step-9:** add models to models.py 
```python 
from django.db import models

# Create your models here.
class BlogPost(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField()
    published_date = models.DateTimeField(auto_now_add=True)
    
    def __str__(self):
        return self.title
```

**Step-10:** create serializers.py inside the api dir and add the below code
```python
from rest_framework import serializers
from .models import BlogPost

class BlogPostSerializer(serializers.ModelSerializer):
    class Meta:
        model = BlogPost
        fields = "__all__"
```

> [!note]-
> **We create a serializer because we need to convert the model to json objects to be returned or passed to API endpoints that we create.**

**Step-11:** create views you can use the generic views for create, read, update and delete.

**Step-12:** add urls.py file inside the app
```python
from django.urls import path
from . import views

urlpatterns = [
    path("blogposts/", views.BlogPostListCreate.as_view(), name="blog-post-list-create"),
]
```

**Step-13:** update the urls.py in our project to forward to app's url.
```python
from django.urls import path, include

urlpatterns = [
    path("", include("api.urls")),
]
```

**Step-14:** make migrations 
```
# make sure you are inside your project
python manage.py makemigrations
```

**Step-15:** migrate 
```
python manage.py migrate 
```


---
## Related Notes

## References(links)
