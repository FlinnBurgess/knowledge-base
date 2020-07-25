# Unification

Unification aims to make the two sides of an expression match. For example, if we input

```text
[1, 2, 3] = List.
```

we get the output

```text
List = [1, 2, 3].
```

This is because Prolog has tried to match the right hand side to the left. The solution in this case implies that `List` must be the same value as the value on the left, i.e. `[1, 2, 3]`.

Prolog can unify in both directions. For example, if we input

```text
[A, B, 3] = [1, 2, C].
```

we get

```text
A = 1,
B = 2,
C = 3.
```

### Falsehood

If there is no logically correct assignment of variables in an expression, Prolog will simply return false, as the expression cannot make sense. e.g.

```text
[A, 2, 4] = [1, B, 3]
```

3 cannot equal 4, and so this is a logically impossible expression.

