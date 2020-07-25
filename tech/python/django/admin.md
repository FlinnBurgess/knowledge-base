# Admin

Creating admin accounts in Django is a very simple process. To create a superuser for the website, you run

```text
python manage.py createsuperuser
```

and then enter the desired username, email and password.

These credentials will now be usable to log into the `/admin/` page of your website to access the admin panel.

### Adding models to the admin panel

You can add access to the models of your project to the admin panel, which allows you to make changes to them through the UI.

To add a model to your admin screen you must add it to the `admin.py` file of an app. First import the model class, then add the line.

```text
admin.site.register(ModelClassName)
```

