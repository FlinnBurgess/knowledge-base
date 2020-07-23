# Aliases

Aliases allow us to group different types into a single type. They are a way of giving a name to a union type.

```text
alias MyAlias = (FirstType.class | SecondType.class)
```

Now if we specify in a method that we are expecting an argument of type `MyAlias`, the compiler will enforce that the argument is either of the class `FirstType` or `SecondType`.

