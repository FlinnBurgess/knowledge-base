# Basics

### Facts

A fact is a piece of information about the world. Facts are made up of predicates and atoms.

#### Examples of predicates/facts

```text
red(car) - the car (atom) is red
fast(car) - the car (atom) is fast
owns(car, jim) - jim (atom) owns car (atom)
```

Each of the above are predicates, which contain atoms.

Facts are generally specific, e.g. John likes Emma. This is very specific about the relationship between John and Emma.

### Atoms

Atoms are meaningful only to the programmer reading them. If you define an atom called `car`, Prolog has no knowledge of the significance of what a car is, it only has inferences about the `car` atom based on the rules and facts you give it.

### Variables

Variables start with a capital letter, e.g. `Thing`

#### Blank Variables

If we want a variable that we want to ignore the value of, we can simply use the `_` character as a placeholder

### Rules

Rules define an if-then relationship between predicates. For example:

```text
fast(Thing) :- fun(Thing)
```

This rule tells us that if the variable Thing is fast, it is also fun.

Unlike facts, rules tend to be generic. e.g. people who like the same things also like each other.

