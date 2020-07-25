# Basics

### Creating a new project

`django-admin startproject projectName` will create a `projectName` directory in your current directory

### Running the development server

Inside a new project there will be a `management.py` file. This can be used to run your development server by using the command `python manage.py runserver {port}`

`{port}` is optional, and allows you to specify a port to listen to.

### Hot reload

Django has a hot-reload function which will reload the site when changes are made to the python code. When new files are added however, they will not be reflected in the site, and a restart is required.

### Apps

An app is a web application that can do something, for example a database, or a simple polling app.

### Projects

A project is a collection of configuration and **apps** for a particular website, and can contain multiple **apps**

### Creating new apps

To create a new app you run `python manage.py startapp appName`

