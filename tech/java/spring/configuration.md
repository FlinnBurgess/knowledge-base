# @Configuration

A class annotated with the `@Configuration` annotation can contain bean definition methods annotated with [the `@Bean` annotation](bean.md). This marks it to be processed by Spring to generate bean definitions and service requests for those beans at runtime.

```text
@Configuration
public class AppConfig {

    @Bean
    public MyBean myBean() {
        // instantiate, configure and return bean ...
    }
}
```

