# Iterators

Iterators allow you to loop over objects such as arrays and strings.

### `each`

`each` allows you to pass each item inside an iterable to a function body. You do that as follows:

```text
my_iterable.each do |item_variable|
    ...
end
```

where `item_variable` is the item of the iterable that the iterator is currently on.

You can also pass the corresponding index of the item as well using `with_index`:

```text
my_iterable.each.with_index do |item_variable, index|
    ...
end
```

