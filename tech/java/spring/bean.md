# @Bean

The `@Bean` annotation goes on a method, typically inside a configuration class. Spring will then use that method to generate the corresponding object when an instance of it is autowired.

Note that Spring beans are different to general Java beans, which are classes which follow a particular standard. In terms of Spring, a bean is a method within a Spring context used to generate a particular object.

