# Readings: Permissions & Postgresql

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

[DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)


Together authentication ad throttling will determine whether a request should be granted or denied access for a website. 


How Permissions are determined:
* the request was successfully authenticated but permission was denied will produce a HTTP 403 error
* the request was not successfully authenticated and the highest priority authentication call does not use WWW-Authenticate headers will also produce a 403 error
* The request was not successfuly authenticated and the highest priority authentication class does use WWW-Authenticate headers will produce a 401 error

REST framework permissions support object level permissioning which is used to determine if a user should be allowed to act on a particular object. 

API reference:
* **AllowAny** is a permission calss that will allow unrestricted access regardless of it the request was authenticated or not
* **IsAuthenticated** will deny permission to any unauthenticated user and allow permission otherwise
* **IsAdminUser** permission class will deny permission to any user unless they're admin
* **IsAuthenticatedOrReadOnly** will allow authenticated users to perform requests but will allowed anonymous users to still read
* **DjangoModelPermissions** ties into Djangos standard model permissions
* **DjangoModelPermissionsOrAnonReadOnly** similar to above but will allow anonymous users to read
* **DjangoObjectPermissions** Ties into djangos standard object permissions framework that allows per-object permissions on models. 

Third Part Packages:
* **DRF- Access Policy** provides a way to define complex access rules in declarative policy classes
* **Compose Permissions** provide simple way to define complex and multi=depth permission objects
* **REST Condition** another extension for building complex permissions
* **DRY Rest Permissions** provide the ability to define different permissions for individual default and custom actions
* **Django Rest Framework Roles** Make its easier to parameterize your API over multiple types of users
* **Django REST Framework API key** provides permissions classes, models, and helpers to add API key authorization to your API
* **Django Rest Framework Role Filters** filtering over multiple types of roles
* **Django Rest Framework PSQ** is an extenstion that gives support for having action-based permission_classes, serializer_class and queryset dependent on permission based rules

## Bookmark and Review

[Classy Django REST](http://www.cdrf.co/)

[DRF Generic Views](https://www.django-rest-framework.org/api-guide/generic-views/)