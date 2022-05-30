# Readings: Authentication & Production Server

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

[JSON Web Tokens](https://jwt.io/introduction/)

What is a JSON Web Token (JWT)?  
It's an open standard that defines a compact self-contained way for securely trasnmitting info between parties as a JSON object.


Some Scenarios where A JWT is useful:
* **Authorization** Most common scenario for JWT. Once the user is logged in, each subsequent request will include the JWT. Allowing the user to access routees, services and resources.
* **Information Exchange** JWTs are a good way of securely transmitting info between parties, especially since they can be signed, so you know who's sending the information.

JWT Structure?
* **Header** Considering of two parts: type of token *JWT* and signing algorithm being used *HMAC, SHA256, or RSA*
* **Payload** Contains the claim, where claims are statement about the user and any additional data. Three types of claims *registered, public, and private*
* **Signature** To create a signature you have to take the encoded header, the encoded payload, and the algorithm specified in the header

How does it work?
When the user successfully logs in the JWT will be returned. 
![image](https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)

Why do we use them? 
Security! 


[DRF JWT Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)
Using them in Django Rest framework

Step 1 Install:
```
pip install djangorestframework_simplejwt
```

Step 2 Add it to Django Project Settings.py:

```
REST_FRAMEWORK = {
	'DEFAULT_AUTHENTICATION_CLASSES': [
		'rest_framework_simplejwt.authentication.JWTAuthentication',
		],
}

```

Step 3 Add to urls.py

```python
from django.urls import path 
from rest_framework_simplejwt import views as jwt_views 

urlpatterns = [ 
	# Your URLs... 
		path('api/token/', jwt_views.TokenObtainPairView.as_view(),
		name='token_obtain_pair'), 
		path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'), 
	]
```


Other Code in views.py and urls.py:

```python
#views
from rest_framework.views import APIView 
from rest_framework.response import Response 
from rest_framework.permissions import IsAuthenticated 

class HelloView(APIView): 
	permission_classes = (IsAuthenticated,) 
	
	def get(self, request): 
		content = {'message': 'Hello, World!'} 
		return Response(content)

#urls
from django.urls import path 
from myapi.core import views 

urlpatterns = [ 
	path('hello/', views.HelloView.as_view(), name='hello'), 
]

```

To use it you need to:
* Obtain the token with a POST request
* Access token(time limit 5 min)
* Refresh token


[Django Runserver Is Not Your Production Server](https://build.vsupalov.com/django-runserver-in-production/)

## Videos

Optional: [JWT with DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)

## Bookmark and Review

[Gunicorn](https://gunicorn.org/)

[Django Migrations Primer](https://realpython.com/django-migrations-a-primer/)