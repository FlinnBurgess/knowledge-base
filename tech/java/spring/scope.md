# @Scope

The `@Scope` annotation is used alongside `@Bean` on a method, and defines the behaviour with which a bean is instantiated.

```text
@Bean
@Scope(String scopeType)
public Person person() {
    return new Person();
}
```

### Prototype

```text
@Scope("prototype")
```

A bean with the `prototype` scope will return a different instance every time it is instantiated.

