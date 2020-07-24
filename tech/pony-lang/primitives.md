# Primitives

Primitives only contain functions, and no fields. You can define primitives of your own, which serve as convenient ways of grouping bits of code. For example:

```text
primitive Math
    fun add(x: U64, y: U64): U64 =>
        x + y

    fun subtract(x: U64, y: U64): U64 =>
        x - y
```

