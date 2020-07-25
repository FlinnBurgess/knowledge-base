# Tail Recursion Optimisation

Recursion can be an inefficient way to formulate a function. However, if the last part of a recursive function is the recursive call, then the compiler can use tail recursion optimisation to turn the recursive call into a loop.

Sometimes we must transform a recursive function so that the recursive call comes last, allowing for the optimisation.

For example, an inefficient implementation of the sum of the values of a list is:

```text
total([], 0).
total([Number|Rest], Sum) :-
    total(Rest, PartialSum),
    Sum is PartialSum + Number.
```

As you can see, this implementation doesn't finish in a recursive call. We can manipulate the implementation so that it does, by using an accumulator:

```text
total([], Final, Final).
total([First|Rest], PartialSum, Final) :-
    total(Rest, PartialSum + Number, Final).
```

Here, the `PartialSum` is the accumulator and holds the current total for each level of recursion.

Since the function now finishes in a recursive call, Prolog can do tail recursion optimisation.

