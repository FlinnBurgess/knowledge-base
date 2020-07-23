# Macros

**Warning** - macros can become complicated very quickly, and should generally be avoided in production code. Instead, it is usually better to explicitly define different but similar classes if needs be, as well as using inheritance when appropriate.

Macros are code templates which can be populated/modified using the given arguments, a little like functions.

In Crystal, macros are processed before compilation of the code, so that any macros you use in your code are expanded before the code is compiled.

You can define macros as follows:

```text
macro my_macro(custom_class_name, **args)
    class {{ example_class_name }} < Example
        def {{ args[:function_name] }}
            {{ args[:function_return_val] }}
        end
    end
end
```

In this example, we can pass a class name and a list of arguments into the macro to generate a custom class based on the template. In this case, the generated class simply uses a method name passed in `args` to return a value also passed in `args`.

We can then use the macro like so:

```text
my_macro(CustomClass, function_name: "custom_function", function_return_val: 120)
```

