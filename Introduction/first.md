## First Spring Boot Application

- Prerequisites:
    - Maven/Gradle
- Adding classpath dependencies:

  **Maven:**
    - most spring boot applications use the `spring-boot-starter-parent` in the `parent` section of the POM.
    - it also provides `dependency-management` section so that you can omit `version` tags for "blessed" dependencies.
    - `spring-boot-starter-web` is used since we are developing a web application.
    - The `mvn dependency:tree` command prints a tree representation of your project dependencies.

- Writing the code:
  ```java
  package com.example;

  @RestController
  @SpringBootApplication
  public class MyApplication{
      @RequestMapping("/")
      String home() {
          return "Hello World";
      }
      public static void main(String[] args){
          SpringApplication.run(MyApplication.class, args);
      }
  }
  ```
  
  - `@RestControlelr` (stereotype annotation) provides hints that the class plays a specific role. In this case, our class is a web `@Controller`, so spring considers it when handling incoming web requests.
  - `@RequestMapping` provides "routing" information. It tells spring that any HTTP request with the `/` path should be mapped to the `home` method.
  - `@RestController` annotation tells spring to render the resulting string directly back to the caller.
  - `@SpringBootApplication` (meta-annotation), it combines `@SpringBootConfiguration`, `@EnableAutoConfiguration` and `@ComponentScan`.
  - `@EnableAutoConfiguration` tells spring boot to "guess" how you want to configure spring based on the dependencies you have added.
  - the `main()` method:
          entry point --> `run` --> `SpringApplication` starts spring --> starts auto-configured tomcat server.
  -  `MyApplication.class` is passed as an argument to `run` to tell `SpringApplication` which is the primary Spring component.  
