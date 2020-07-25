# virtualenv

`virtualenv` allows you to create isolated python environments. For example you can create an isolated environment in your project by navigating to the project folder and running `virtualenv venv` which will create a folder venv in your project containing a copy of python to be used in your virtual environment.

`venv` is a name used by convention, and is usually included in .gitignore files for example.

### Using the virtualenv

To use a virtual environment after creating it, you can run the command

```text
source venv/bin/activate
```

this will set your python interpreter to the one stored in your venv folder and any package installation you do \(for example with pip\) will be attributed to that environment.

### Leaving a virtualenv

To leave a virtualenv you simply run

```text
deactivate
```

### Deleting a virtualenv

To delete a virtualenv, just delete the corresponding folder.

### Running without global packages

The `--no-site-packages` flag stops the virtual environment from using globally installed packes. It is default behaviour for virtualenv 1.7+

