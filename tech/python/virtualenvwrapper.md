# virtualenvwrapper

`virtualenvwrapper` makes the use of python virtual environments easier. You need to have `virtualenv` installed before you can use `virtualenvwrapper`

### Creating a virtual env

`mkvirtualenv project_folder` creates a project\_folder folder inside `~/Envs` folder, or whatever you have set your environment variable `$WORKON_HOME` to be

### Work on a virtual env

`workon project_folder`

### Deactivate a virtual env

`deactivate`

### Delete an env

`rmvirtualenv venv`

### Other useful commands

`lsvirtualenv` List all of the environments.

`cdvirtualenv` Navigate into the directory of the currently activated virtual environment, so you can browse its site-packages, for example.

`cdsitepackages` Like the above, but directly into site-packages directory.

`lssitepackages` Shows contents of site-packages directory

### [Reference link](https://virtualenvwrapper.readthedocs.io/en/latest/command_ref.html)

