<details>
  <summary>Using the "default" package</summary>

  - when a class does not include a ```package``` declaration, it is considered to be in the "default package".
  - it's use is discouraged, can cause problems for Spring Boot Applications that use ```@ComponentScan```, ```@ConfigurationPropertiesScan```, ```@EntityScan```, or ```@SpringBootApplication``` annotations, since every class from every jar is read.

    Tip: ``` follow java's recommended package naming conventions and use a reversed domain name (for eg: com.example.project)```
</details>

<details>
  <summary>Locating the Main Application Class</summary>

  - locate your main application class in a root package above other classes.
  - ```@SpringBootApplication``` annotation is often placed on your main class, defines a base "search package" for certain items.
```java
@SpringBootApplication
public class MyApplication{
    public static void main(String[] args){
        SpringApplication.run(MyApplication.class,args);
    }
}
```
</details>
