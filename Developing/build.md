<details>
  <summary>Build Systems</summary>
  
  - choose a build system that supports dependency management like maven or gradle

  **Dependency Management:**
  - each release of spring boot provides a curated list of dependencies that it supports.
  - no need to specify a version of any dependecy. Spring boot manages that.
  - the curated list contains all spring modules that you can use with spring boot as well as a refined list of third party libraries. ``spring-boot-dependecies``
</details>

<details>
  <summary>Starters</summary>

  - a set of convenient dependency descriptors that you can include in your application. Eg: ``spring-boot-starter-data-jpa``
  - starters contain a lot of the dependencies that you need to get a project up and running quickly.
  - all official starters follow a naming patter:
    - ``spring-boot-starter-*``, where ``*`` is a particular type of application.
</details>
