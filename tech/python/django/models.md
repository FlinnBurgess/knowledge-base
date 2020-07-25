# Models

Models essentially describe the layout of your database. You define your models inside the `models.py` file of an app.

### Defining models

A model is defined by creating a new class inside `models.py`. Each class should inherit from the Model class like so:

```text
MyModel(models.Model):
    field_name_one = models.SomeFieldClass({specs})
```

The class variables define the fields of your database, and the names you give it them will be used as field names, in this case `field_name_one`.

### Steps for making model changes

* Change your models
* Create the migrations
* Apply the migrations

### `migrate`

```text
python manage.py migrate
```

This command takes any migration scripts in your project and applies them to the database.

### `makemigrations`

```text
python manage.py makemigrations appName
`
```

This command takes any changes you've made to your models and generates the appropriate migrations required to reach that state.

### `sqlmigrate`

```text
python manage.py sqlmigrate appName migrationNumber
```

`sqlmigrate` can be used to see the SQL that a migration uses to achieve the desired state.

### String representations

Always remember to add a `__str__` method to your models, as it is used throughout Django and will help to make things more readable.

### Business logic

Since your models are just classes, you can define functionality in them. This means that any instances of the model in your database will have those functions, and you can use them in the logic of your project.

