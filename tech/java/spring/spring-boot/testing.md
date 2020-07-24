# Testing

### MockMvc

We can `Autowire` a `MockMvc` object to be used in simulating HTTP requests.

### Annotations

#### @Test

Denotes a test case inside a test class

#### @SpringBootTest

Placing this annotation on your test class causes Spring to start an entire instance of your Spring Boot app for running the tests. This approach to testing can result in long test execution times since you have to instantiate the whole app for each relevant class.

You can pass a parameter into the annotation to specify certain behaviour, for example

```java
@SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
```

will tell the services to listen to requests on a randomly generated port. Then when we use the @LocalServerPort annotation to inject a variable, it will use the randomly generated value. This allows us to make calls to the service in our tests by querying `localhost:{port number}`.

You should use `@SpringBootTest` if you are going to be testing the application from start to finish, or for parts of the codebase which are difficult to set up manually.

#### @MockBean

This annotation allows you to create a mock instance of a class. You can then use Mockito syntax to mock return values for particular method calls.

This is useful for when you only want to test a certain part of the application, and don't care about specific functionality of the parts you are mocking.

#### @WebMvcTest

This annotation causes Spring to fire up an application context containing only the Beans that are required to test a web controller.

You can pass a `controllers` parameter to the annotation to specify a set of Controller classes which should be used in the application context. Excluding this parameter means that all Controller classes are included.

