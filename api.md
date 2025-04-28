## Spring Boot - REST API
Initialize Spring Boot project and add web dependency.
```java
package com.example.demo.controllers;

import org.springframework.web.bind.annotation.*;

@RestController
public class RestEndpoints{
    @GetMapping("/course")
    public Course getEndpoint(@ResquestParam(defaultValue = "Spring Boot", required = false)String name,
                              @ResquestParam(defaultValue = "2", required = false)Integer chapterCount){
                  return new Course(name, chapterCount);
    }

    @PostMapping("/register/course")
    public String saveCourse(@RequestBody Course course){
            return String.format("Your course named %s with %s chapters is saved", course.getName(), course.getChapterCount());
    }
}
```
