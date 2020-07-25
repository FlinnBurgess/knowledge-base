# URLs

### URLconfs

A project will have a top-level `urls.py` \(referred to as a URLconf in the docs\), and apps can also have their own URLconf files as well.

Each URLconf will contain an array of paths named `urlpatterns`, which are used to navigate the website.

```text
urlpatterns = [
    path('path-one/', include('pathOne.urls')),
    path('admin/', admin.site.urls),
]
```

### `ROOT_URLCONF`

This setting tells Django which URLconf to use as the base level resolver of URLs

### `include()`

In the example above you see the use of `include('appOne.urls')`. Include allows you to have nested URLs which are defined in a given package's URLconf. In the example above, navigating to /path-one/something-else in your URL will use the URLconf of appOne to map something-else to a specific view

### `path()`

The path function defines a single mapping of a URL to a behaviour/view. Paths are found in lists in a URLconf, as shown above.

The `path()` function takes four arguments:

#### `route` \(required\)

`route` is a string representation of a URL pattern. `GET` request params are not included when searching routes for a match, only the base URL.

#### `view` \(required\)

The `view` passed is used when Django finds a matching URL pattern. Django passes an HttpRequest as the first argument to the view, and a list of kwargs as the second argument.

#### `kwargs` \(optional\)

A dictionary of keyword arguments to be passed to the target view

#### `name` \(optional\)

You can name your URL so that it can be referenced unambiguously from elsewhere in Django, especially from within templates.

### Extracting variables from a URL

You can extract values from a URL to use in your code by doing something like the following:

```text
path('<int:question_id>', views.detail, name='detail')
```

The `int` part denotes what sort of value Django should match when looking at the URL, and `question_id` assigns the matched value with to a keyword argument which gets passed to `views.detail`

