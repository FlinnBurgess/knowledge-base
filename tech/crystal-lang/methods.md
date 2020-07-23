# Methods

### Signatures

Method signatures can be defined with a selection of different argument styles.

#### Optional arguments

Here we can assign default values that will be used if none is passed.

```text
def method(optional = "optional")
    ...
end
```

#### Type Matching/Overloading

You can define the same method multiple times with different argument types, and have them behave differently.

```text
def method(item : Int32)
    ...
end

def method(item : String)
    ...
end
```

#### Splat argument

This argument takes a list of items rather than a single one. The items eventually are resolved to tuples.

```text
def method(*items)
    ...
end
```

#### Named arguments

```text
def method(nameOne argumentOne, nameTwo argumentTwo)
    ...
end

method nameOne: "some string", nameTwo: 12345
```

#### Double splats

Double splat arguments allow you to pass a list of arguments in the format of `key: value`

```text
def method(**arguments)
    ...
end

method argumentOne: valueOne, argumentTwo: valueTwo
```

### Scope

Methods and classes are public by default. For both, you can limit the scope by adding the `private` or `protected` keyword in front of the `def` or `class` keyword.

### Return types

Method return types are always inferred, but you can specify the return type of a method by doing the following:

```text
def method(argumentOne, argumentTwo) : Number
    ...
end
```

The method defined above will return a `Number`. A type restriction can either be a type or `self`, which refers to the current class.

If you specify that a method has a return type of `Nil`, then Crystal will always return nil for that method.

