# Classes & Objects

### Methods

You can define methods at the class level and the object level.

```text
class MyClass
    def self.doSomething()
        ...
    end

    def doSomething()
        ...
    end
end
```

In the example above, we have defined doSomething twice. However the two methods are subtly different.

In the first case we've defined a class method. So, if we call `MyClass.doSomething()` then the code inside the first method will be used.

If we instantiate a `MyClass` object and call the same method again:

```text
MyClass.new.doSomething()
```

where `MyClass.new` is an object instance of the `MyClass` class, then the second version of the method will be called.

The key is if the method has `self` in front of it, then it is a class method, otherwise it is an object method.

### Inheritance

Inheritance is denoted with the `<` symbol:

```text
class Subclass < Superclass
    ...
end
```

### Object constructors

Object constructors are defined in the `initialize` method of a class:

```text
class MyClass
    def initialize(parameter)
        @parameter = parameter
    end
end

instanceOfObject = MyClass.new("string argument")
```

### Instance variables

Instance variables are denoted using the `@` symbol before the variable. In the example above we see `@parameter` variable, which we set to the argument that is passed to the constructor. You can access instance variables. Taking the above example again, and assuming you have defined a getter somehow \(see below\), you would access parameter by calling

```text
instanceOfObject.parameter
```

There is a shorthand for assigning instance variables in a constructor:

```text
def initialize(@parameter : Type)
    ...
end
```

### Getters

Instance variables do not have getters by default. You can either define your own, or you can use the `property` or `getter` keywords in front of the instance variable name:

```text
class MyClass
  getter variable_one
  property variable_two
end
```

either of these keywords allows you to now call `my_class_instance.variable_name`

### Class variables

Like instance variables, you can also define class variables using `@@`. These are like static variables in languages such as Java, and are consistent across all instances of a class.

