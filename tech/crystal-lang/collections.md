# Collections

### Arrays

Arrays are defined like so:

```text
[123, 444, 901]
```

Every element of an array must have the same type, but this type can be a _union type_, i.e. a combination of multiple types \(e.g. a number or a string\). Despite this, you should try and ensure an array contains values of the same type.

### Tuples

Defined like so:

```text
{"A String", 123, :symbol}
```

A tuple is a fixed length list of items that can have different types.

We can pass the individual members of a tuple as arguments by placing the `*` symbol in front of it:

```text
coordinates = {6, 4}
plot(*coordinates)
```

### Named Tuples

Defined like so:

```text
{string: "A String", number: 123, symbol: :symbol}
```

Named tuples allow us to associate a symbol with each tuple element.

### Indexing

Crystal allows random access of tuples and arrays, as opposed to linked-list style behaviour. Crystal will throw an out-of-bounds exception if the index doesn't exist, but you can default the value to nil instead by including `?` like so:

```text
list[4]?
```

### Hashes

Defined like so:

```text
{"Key" => :value, "String" => :symbol}
```

The keys must be of the same type, as do the values. However, like with arrays, these types can be union types, but this should be avoided for simplicity's sake.

### `includes?`

Classes which inherit from `Enumerable` have the `include(...)` method, which allows you to search for an object inside them.

