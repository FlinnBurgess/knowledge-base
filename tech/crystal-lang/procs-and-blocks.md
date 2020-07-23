# Procs & Blocks

Procs & blocks allow you to utilise higher-order functions, e.g. passing them as arguments to other functions.

### Blocks

Blocks allow you to take anonymous functions as arguments to your methods. This makes them the primary way of manipulating arrays, such as filtering, partitioning and transforming. The short form syntax is like so:

```text
[1, 2, 3].map{|x| "#{x} Mississippi"}
```

The block is the code wrapped in braces `{ ... }`. To define a method that uses a block, we define a `&block` argument like so:

```text
def myFunction(&block: T -> U)
    ...
end
```

This tells us that we will accept a block that transforms values from type T to an unknown type U.

To call the function passed to your method, you make a call to `yield`.

### Procs

Procs allow us to assign functions to variables. We write these like so:

```text
a_variable = -> (argument: Type) do
    argument.doSomething()
end
```

This `do ... end` definition is the long form and is optional. You could optionally use the short form instead, as seen above, like so:

```text
a_variable = -> (argument: Type) { |arg| arg.doSomething() }
```

