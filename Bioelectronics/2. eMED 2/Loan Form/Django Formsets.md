# Django Formsets

## 2021-12-15

#documentation #instruction

---

## Django Formsets

- Formsets in Django are an advanced way of handling multiple forms on a single webpage.
- A formset is a layer of abstraction to work with multiple forms on the same page.
- To create a Django formset you need to use the ==Django Form Class==
- Creating a form is much easier than handling the data entered into those fields at the back end.



## Loans App 
### First set up a normal model and form
1. Create loan model:

```python
#loans/models.py

class Loan(models.Model):
	loan_number = models.IntegerField()
	supplier = models.CharField(max_length=256, null=True)
	contact_person = models.CharField(max_length=256, null=True)
	...
	
	def __srt__(self):
		return self.supplier
```

2. Create views and forms as required

```python
#loans/views.py

class CreateLoanView(CreateView):
	model = Loan
	fields = '__all__'
```

```python
#loans/form.py

class LoanForm(ModelForm):
	class Meta:
		model = Loan
		fields = '__all__'
```

3. Write template and add the urls.py

```html
<form action="." method="post">
	{% csrf_token %}
	{{ form }}
	<button type="submit">Submit</button>
</form>
```

### Adding a formset
The use of formsets grant us the ability to assign multiple equipment to a single loan (loan number).

1. Create LoanEquipment model

```python
#loans/models.py

class LoanEquipment(models.Model):
	equipment_description = models.CharField(max_length=256)
	model = models.CharField(max_length=256, null=True)
	model_number = models.CharField(max_length=50, null=True, blank=True)
	
	loan = models.ForeignKey(Loan, one_delete=models.CASCADE)
	
	...
	
	def __str__(self):
		return self.equipment_description.strip()
```

The `ForiegnKey` defines a One-To-Many relationship between the `Loan` and `LoanEquipment` models - meaning a loan entry can have many associated equipment.

2. Register the LoanEquipment model in the Admin panel

```python
#loans/admin.py

from .models import Loans, LoanEquipment

class LoanEquipmentInline(admin.TabularInline):
	model = LoanEquipment
	extra = 1

@admin.register(Loan)
class LoanAdmin(admin.ModelAdmin):
	inlines = [LoanEquipmentInline]

```

There are a couple of things happening here

First we create an inline model by subclassing `admin.TabularInline` and specifying which model to use for the inline - `LoanEquipment` in our case.

Next, we need to create a `LoanAdmin` class responsible for how the `Loan` model in rendered in the admin panel. To render the `LoanEquipmentInline` on the same page as the `Loan` model, we add the `LoanEquipmentInline` to the LoanAdmin's `inlines` list.

Lastly, we register the `Loan` model and its inline models with the admin panel using the `@admin.register`decorator and passing our `Recipe` model as an argument.

3. Create the LoanEquipment formset

```python
#loans/forms.py

from django.forms import ModelForm, inlineformset_factory
from .model import Loan, LoanEquipment

class LoanEquipmentForm(forms.ModelForm):
	class Meta:
		model = LoanEquipment
		exclude = ('Loan')

LoanEquipmentFormSet = forms.inlineformset_factory(Recipe, Ingredient, form=IngredientForm)
```

Once we create the `LoanEquipmentForm` we can make the formset by using the `inlineformset_factory` function with three arguments:
- model - the parent model
- related model - the related model with the ForeignKey
- form - an optional base form to use for each form in the formset

`inlineformset_factory` automatically associates the parent model with its child model.

4. Modifying the Loan view