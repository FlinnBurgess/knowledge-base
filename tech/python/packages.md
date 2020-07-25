# Packages

Packages allow you to organise your modules in an intuitive way.

### `__init__.py`

To initialise a package, a folder has to contain the file `__init__.py`. This tells python that the folder is a package. `__init__.py` can be an empty file, or it can contain additional information to do with initalisation, or for example `__all__`, below.

### `__all__` and `import *` behaviour

Defining an `__all__` variable insite of `__init__.py` defines the submodules and subpackages that should be imported if the wildcard is used. For example, if in `package` you have

```text
__all__ = ["subpackage_one", "subpackage_two"]
```

then when you run

```text
import package
```

you will have access to `subpackage_one` and `subpackage_two`.

If you don't include an `__all__` variable, then importing `package` will mean that you have to call `package.subpackage_one` to access the modules of `subpackage_one`

### Sub-packages

A package folder can contain sub-folders which can themselves contain the `__init__.py` file which makes them into packages. This allows you to next packages and then import them like this: `package_one.package_two`

