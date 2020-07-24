# Actors & Classes

### What's the difference?

In Pony, logic inside a class is run synchronously, whereas actors are run with asychronous communication.

Actors replace threads for concurrency.

### Constructors

Constructors are defined by the `new` keyword:

```text
new my_constructor([args]) =>
    ...
```

An actor or class can have multiple constructors with different names.

### Default constructor

The default constructor for an agent or class is `create`:

```text
actor Main
    new create([args]) =>
        ...
```

### Instantiating

You instantiate a class or actor like so:

```text
my_variable = ClassOrActor

another = ClassOrActor(with_argument)
```

### Fields

Fields are defined as such:

```text
var _field: Type

new create() =>
    ...
```

The underscore before the field's name denotes it as being private. In this case we don't assign a value to the field, and so the code won't compile unless we assign it a value in the constructor.

### Return Types

When defining behaviours or functions, specifying the return type is important. If no return type is specified, then the compiler will assume that the function returns a None type.

## Classes

### Functions

In classes, functions are defined like so:

```text
fun ref function_name(): ReturnType =>
    ...
```

### `apply` function

The apply function is meant to implement some common functionality of a class, and can be called directly. For example:

```text
class ExampleClass
    fun apply(var_one: String, var_two: String)
        ...

my_class = ExampleClass
result = my_class("String one", "String two")
```

As you can see you don't need to call `my_class.apply("String one", "String two")`, and you can just omit `.apply`.

## Actors

### Behaviours

In actors, rather than defining functions, you define behaviours using the `be` keyword:

```text
be behaviour_name(): ReturnType =>
    ...
```

