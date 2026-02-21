## Auto-Configuration

- attempts to configure spring application based on jar dependencies added automatically.
- use `@EnableAutoConfiguration` or `@SpringBootApplication` annotations to `@Configuration` classes.
-  `--debug` adding this to your application enables debug logs for a selection of core loggers and logs a conditions report to the console

Disabling Specific Auto-configuration classes
----
- use `exclude` attribute to disable them:
    ```java
      @SpringBootApplication(exclude = { DataSourceAutoConfiguration.class})
        public class MyApplication{
    }
    ```
- if class is not on the classpath, use `excludeName` attribute of the annotation and specify the fully qualified name instead.
- can also use `spring.autoconfigure.exclude` property to control list of auto-configuration classes.
- Additional packages can be configured using the `@AutoConfigurationPackage` annotation.
