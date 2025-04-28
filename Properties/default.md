# Default Properties file
- application.properties file is autodetected, its placed in "src/main/resources".
- Spring Boot specified various common default properties inside to support logging, AOP, Identify, Hibernate, JPA etc.
- no need to specify all the default properties in all cases, specify them only on-demand.
- this is how spring reduces XML based configurations and changing them to simple properties.
- Declare the properties:
    ```java
    server.port = 8080
    default.course.name=SAP HANA
    default.course.chapterCount=66
    ```
- Use the properties:
    ```java
    @Value("${default.course.name}")
    private String nameDefault;

    @Value("${default.course.chapterCount}")
    private Integer chapterCountDefault;
    ```
