# Views

Views are defined in the `views.py` file of an app. In the file you define a function which takes a request as an argument and returns the view, for example

```text
def index(request):
    return HttpResponse("Hello, world")
```

