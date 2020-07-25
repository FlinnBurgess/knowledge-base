# Domains

It is important in a language like Prolog to define the expected domain of a given variable. One example of defining a domain would be to check a variable against a list of expected values, like so:

```text
colour(Colour) :-
    member(Colour, [red, green, blue]).
```

