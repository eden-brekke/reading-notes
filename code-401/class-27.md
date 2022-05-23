## Reading

[Using Models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)

* models are what define the structure and data within Django. 
* You can choose many DB types to fit a given model that you want to work with 
* Using groups of related info is the most common way of organization, called an 'Object'
* You can define relationships within Django in three ways
	* one to one 
	* one to many
	* or many to many 

example 

```python
from django.db import models
from django.urls import reverse

class MyModelName(models.Model):
    """A typical class defining a model, derived from the Model class."""

    # Fields
    my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
    ...

    # Metadata
    class Meta:
        ordering = ['-my_field_name']

    # Methods
    def get_absolute_url(self):
        """Returns the URL to access a particular instance of MyModelName."""
        return reverse('model-detail-view', args=[str(self.id)])

    def __str__(self):
        """String for representing the MyModelName object (in Admin site etc.)."""
        return self.my_field_name

```

#### Common field arguments for declaring many or most of the different field types:
 * **help_text** provides text label for HTMl forms 
 * **verbose_name** human readable name for field used in field labels (default verbose name from field name if not specified)
 * **default** default value for field. can be a value or an object
 * **null** if True Django will store blank values as NULL in the DB for fields where appropriate. 
 * **blank** if True, the field is allowed to be blank in your forms, but the default is false. 
 * **choices** group of choices for the field. if provided the default corresponding form widget will be a select box with these choices instead of the standard text field
 * **primary_key** if True: sets the current field as the primary key for the model *where primary key is a special database column designated to uniquely identify all the different table records* If no field is specified as the primary key fields can be specified for each app, or globally. 

#### Common field types:
* **CharField** is used to define short-to-mid sized fixed length strings (must specify max_length)
* **TextField** used for large arbitrary-length strings. may specify max_length but its only used when field is displayed in forms. (not enforced at db level)
* **IntegerField** field for storing ints, and for validating entered values as ints
* **DateField** or **DateTimeField** used for storing/representing dates and date/time info. Field can additionally declare the mutually exclusive parameters. 
* **EmailField** used to store and validate email addresses
* **FileField** and **ImageField** used to upload fiels and images respectively 
* **AutoField** special type of *IntegerField* that automatically incremenets, *primary key* of this type is automatically added to your model if you don't specify one
* **ForeignKey** used to specify a one-to-many relationship to another DB model
* **ManyToManyField** specifies many-to-many relationships
* 
[Django Admin](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)

-   `Advanced configuration` section is optional
    
-   The tutorial is really good but some of the tools are dated so when reading try to understand the concepts more than the code.

* Can use Django Admin site to add your data
* Register your model with the Admin Site then Login and Create some the data 
* Then the Django admi app can use the models you've registered to allow part of your site to create, view, update, and delete (CRUD :D) your data 
* create a superuser (which can be used to create instances of models to test the sites capabilities)
* Run the server!
* login with the superuser 
* Use the site! 

**Things I want to Know more about**
I don't really understand the superuser stuff, interested to look more into this. 

(Optional): [Beginner’s Guide to Django - Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)

## Bookmark and Review

[Beginner’s Guide to Django - Part 2](https://simpleisbetterthancomplex.com/series/2017/09/11/a-complete-beginners-guide-to-django-part-2.html)