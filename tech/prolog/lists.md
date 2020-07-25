# Lists

### Deconstructing lists

We can take the first element of a list and the remaining elements like so

```text
?- [First|Rest] = [1, 2, 3]
First = 1,
Rest = [2, 3].
```

