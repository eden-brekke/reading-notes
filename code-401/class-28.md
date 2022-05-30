## Reading

[Django Forms](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)

### Objective: 
* to understand how to write forms to get information from users and update the database. 
* to understand how generic class-based editing views can simplify form creation

An HTML form is a group of fields/widgets on a webpage.  
Forms are a flexible way for collecting user input. 
Forms are also relatively secure for sharing data with the server, allowing us to send data in a POST request, with cross-site forgery protection.

Django forms take a lot of work out of the creation of forms.  
They provide a framework that lets you define forms and their fields programmatically. 
It then uses the objects to generate the form, handle the validation and user interactions.  

#### Example of an html form:
```html
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```

After hittin submit, the data is uploaded to the server. 
The form attributes define the HTTP method used to send the data and the destination of the data on the server(action)
* **action:** The resource/URL where data is to be sent for processing when the form is submitted (If this is not set then the form will be submitted back to current page URL)
* **method:** the HTTP method used to send the data: post or get
	* the **POST** method should always be used if the data is going to result in a change to the server's database. (More resistant to cross-site forgery request attacks)
	* the **GET** method should only be used for forms that don't change the user data (such as a *search* form)

The role of a server is to render the initial form state. 
After the user presses submit the server receives the data. 
Once a server gets a request with all valid form data, then it'll perform the appropriate reaction.

### The main things Django's form handling does are:
1. Display the default form for the first time,
2. Receive data from submit request and bind it to the form
3. Clean and Validate the data
4. If any data is invalid: redisplay the data
5. If all data is valid, perform required actions
6. Once all actions are complete redirect user to another page


#### Declare Form:
```python
from django import forms

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")
```

### Most common Form Arguments
* **require:** boolean, if a field is required or not
* **label:** used to render the field in html, if not specified Django will create one by capitalizing first letter and replacing spaces with underscores
* **label_suffix:** default is colon after label, but you can change it
* **initial:** initial value for the field when the form is displayed
* **widget:** display widget to use
* **help_text:** additional text that can be displayed in forms to explain how to use the field
* **error_message:** list of error messages for field
* **validators:** list of functions that will be called on field when it's validated
* **localize:** enables localization of form data input
* **disable:** field is displayed but its value cannot be edited if this is true (default is false)

#### Form Validation
update forms.py:
```python
import datetime

from django import forms

from django.core.exceptions import ValidationError
from django.utils.translation import gettext_lazy as _

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")

    def clean_renewal_date(self):
        data = self.cleaned_data['renewal_date']

        # Check if a date is not in the past.
        if data < datetime.date.today():
            raise ValidationError(_('Invalid date - renewal in past'))

        # Check if a date is in the allowed range (+4 weeks from today).
        if data > datetime.date.today() + datetime.timedelta(weeks=4):
            raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))

        # Remember to always return the cleaned data.
        return data
```

url config:
```python
urlpatterns += [
    path('book/<uuid:pk>/renew/', views.renew_book_librarian, name='renew-book-librarian'),
]
```

views:

```python
import datetime

from django.contrib.auth.decorators import login_required, permission_required
from django.shortcuts import get_object_or_404
from django.http import HttpResponseRedirect
from django.urls import reverse

from catalog.forms import RenewBookForm

@login_required
@permission_required('catalog.can_mark_returned', raise_exception=True)
def renew_book_librarian(request, pk):
    """View function for renewing a specific BookInstance by librarian."""
    book_instance = get_object_or_404(BookInstance, pk=pk)

    # If this is a POST request then process the Form data
    if request.method == 'POST':

        # Create a form instance and populate it with data from the request (binding):
        form = RenewBookForm(request.POST)

        # Check if the form is valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required (here we just write it to the model due_back field)
            book_instance.due_back = form.cleaned_data['renewal_date']
            book_instance.save()

            # redirect to a new URL:
            return HttpResponseRedirect(reverse('all-borrowed') )

    # If this is a GET (or any other method) create the default form.
    else:
        proposed_renewal_date = datetime.date.today() + datetime.timedelta(weeks=3)
        form = RenewBookForm(initial={'renewal_date': proposed_renewal_date})

    context = {
        'form': form,
        'book_instance': book_instance,
    }

    return render(request, 'catalog/book_renew_librarian.html', context)
```




HoooooBoy this is a long one, I think I get the jist but I think this is definitely one that I'll have to come back and reference. 


## Bookmark and Review

[Django Templates](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Home_page)

[Django Views](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Generic_views)