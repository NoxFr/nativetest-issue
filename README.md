# Sample project for Multi Module Native Test Issues

    ./mvnw clean install

This successfully builds the project and runs the tests.

    ./mvnw clean install -Pnative,nativeTest

This command fails with the following error:

```
[ERROR] Failed to execute goal org.springframework.boot:spring-boot-maven-plugin:3.4.3:process-aot (process-aot) on project shared: Unable to find a suitable main class, please add a 'mainClass' property -> [Help 1]
```

This is because the `nativeTest` profile add the `spring-boot-maven-plugin` to use the `process-aot` goal on test classes. 
However, in a multi-module project, the spring boot main class is commonly defined only in the application module.