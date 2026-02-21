## Developer Tools

- `spring-boot-devtools` modules is used
- they might cause classloading issues
- they are automatically disabled when running a fully packaged application.
- to enable devtools, set `-Dspring.devtools.restart.enabled=true` system property, to disable devtools, exclude the dependency or set `-Dspring.devtools.restart.enable=false`.

Diagnosing Classloading Issues
----
#### Restart VS Reload
The restart tech works by using two classloaders. Classes that do not change are loaded into a base classloader. Classes that are actively developing are loaded into a restart classloader.
When the application is restarted, the _restart_ classloader is thrown away and a new one is created (meaning application restarts are much faster than "cold starts") 
If restarting is not quick enough or causes classloading issues, you can use reloading tech such as `JRebel` (works by rewriting classes as they are loaded to make them more amenable to reloading.)

Logging Changes in Condition Evaluation
-----
- each time app restarts, a report showing the condition evaluation delta is logged.
- shows changed to app's auto-config as you make changes such as adding or removing beans.
- to disable it:
  ```shell
    spring.devtools.restart.log-condition-evaluation-delta=false
  ```
