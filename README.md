# A quick attempt with Spring framework

## How to start

1. Checkout the source to a folder (ensure you have [gradle](https://docs.gradle.org/current/userguide/installation.html) installed)
2. Use `gradle wrapper` to prepare `gradlew` tools
3. Run `.\gradlew bootRun` and heading to http://localhost:8080/greeting to verify the result

## Highlights
* Static resources structure
* Auto reload
* devtools
* Gradle build
* Http compression

### Static resources

```bash
── src
    ├── main
    │   ├── java
    │   │   └── com
    │   └── resources
    │       ├── application.properties
    │       ├── *static*
    │       └── templates
    └── test
        └── java
            └── com
```

### Auto reload and devtools

In `gradle.build`, ensure following part

```ini
repository {
  addResources = true
}
```

and dependencies

```ini
dependencies {
...
compile("org.springframework.boot:spring-boot-devtools")
...
}
```

### Gradle build

* Take a look on available tasks by executing `gradle tasks`
* Basic live-reload session by `.\gradlew bootRun` (this gradlew is create by `gradle wrapper`)

### Http compression

* Add following settings to `src/main/resouces/application.properties`

```ini
server.compression.enabled=true
server.compression.mime-types=text/css,application/javascript
```

## References

* [Appdx A - Common application properties](http://docs.spring.io/spring-boot/docs/current/reference/html/common-application-properties.html)
* [Reference](http://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#how-to-enable-http-response-compression)
* [Guides](http://spring.io/guides)
* [Spring initializr](https://start.spring.io)
