## Reading

[Django Custom User Model](https://learndjango.com/tutorials/django-custom-user-model)
Instead of using the build in user model, it's suggested that you use the custom user model instead! 
The custom user model provides flexibility. 

Setup:
* create and navigate into a dedicated directory called accounts 
* install django
* make new django project
* make new app (accounts)
* start the local web server

Run these commands: 
```
# Windows
> cd onedrive\desktop\code
> mkdir pages
> cd pages
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
(.venv) > django-admin startproject django_project .
(.venv) > python manage.py startapp accounts
(.venv) > python manage.py runserver
```
They don't run migrate because it's important to wait until after they've created the custom user model before migrating

Next Create the initial custom user model:
* update project settings (add accounts to installed apps)
* create new CustomUser model
* create new UserCreation and UserChangeForm
* update the admin

```python
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

create accounts/forms.py
and add this to forms.py: 
```python
# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

Then to admin.py:
```python
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

Now it's time to migrate! 
makemigrations accounts and then run the migrate
create the superuser
then its TUV Tough looove
And that's all! 

[DjangoX](https://github.com/wsvincent/djangox)
This is a repo that you use  as a starter Django project. 
install:
```
$ git clone https://github.com/wsvincent/djangox.git
$ cd djangox
```

Pip:
```
$ python -m venv .venv

# Windows
$ Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
$ .venv\Scripts\Activate.ps1

# macOS
$ source djangox/bin/activate

(.venv) $ pip install -r requirements.txt
(.venv) $ python manage.py migrate
(.venv) $ python manage.py createsuperuser
(.venv) $ python manage.py runserver
# Load the site at http://127.0.0.1:8000
```

Then add your environmental variables, add gunicorn as the production web server, update the email_backend and connect with a mail provider, secure the admin, that's all! 
## Videos

Choose one:

[Creating a Custom User Moel](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)

[Abstract User, User Profile and Signals in Django](https://www.youtube.com/watch?v=EudKs1HPUfE)
User Model:
* email 
* username
* password
* storage quota pictures 

this video adds extra fields to the model
easiest point to do this at the new project level
less easy to a production app (no real users)
tricky with a live app (real users exist)

start a new project with a template that already has the usermodel
and import/extend AbstractUser in your UserModel

three steps to make a user profile
1. make a one to one relation of user to user profile
2. then create post_save signal 
3. load signal into the app

 


## Bookmark and Review

[Substituting a custom User model](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)