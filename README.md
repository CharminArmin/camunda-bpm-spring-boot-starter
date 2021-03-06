# camunda-bpm-spring-boot-starter

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.camunda.bpm.extension/camunda-bpm-spring-boot-starter/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.camunda.bpm.extension/camunda-bpm-spring-boot-starter)  [![Project Stats](https://www.openhub.net/p/camunda-bpm-spring-boot-starter/widgets/project_thin_badge.gif)](https://www.openhub.net/p/camunda-bpm-spring-boot-starter) [![Travis Build](https://travis-ci.org/camunda/camunda-bpm-spring-boot-starter.svg?branch=master)](https://travis-ci.org/camunda/camunda-bpm-spring-boot-starter)

</tr>
</table>

## Get started

The extension is published on maven central, so if you are using maven, just add the dependency:

```xml
<dependency>
  <groupId>org.camunda.bpm.extension</groupId>
  <artifactId>camunda-bpm-spring-boot-starter([-rest|-webapp])</artifactId>
  <version>1.3.0</version>
</dependency>
```

and then create a simple process application like this one:

```java
@SpringBootApplication
@ProcessApplication
public class WebappExampleProcessApplication extends SpringBootProcessApplication {

  public static void main(String[] args) {
    SpringApplication.run(WebappExampleProcessApplication.class, args);
  }

}
```

Check out the [Documentation](https://camunda.github.io/camunda-bpm-spring-boot-starter) and the [Examples](https://github.com/camunda/camunda-bpm-spring-boot-starter/tree/master/examples)


## Resources

* [Issue Tracker](https://github.com/camunda/camunda-bpm-spring-boot-starter/issues)
* [Contributing](https://github.com/camunda/camunda-bpm-spring-boot-starter/blob/master/CONTRIBUTE.md)



## Releases

* [Release Notes 1.2.1](https://github.com/camunda/camunda-bpm-spring-boot-starter/milestone/5?closed=1)
* [Blog Article for release 1.2.0](https://blog.camunda.org/post/2016/06/camunda-spring-boot-1.2.0-released/)
 
### Migration hints

#### From < 1.3.0 to >= 1.3.0

##### Configuration

We have decided to refactor the configuration mechanism. Especially we removed the  `org.camunda.bpm.spring.boot.starter.configuration.CamundaConfiguration` interface. For now all configurations are `org.camunda.bpm.engine.impl.cfg.ProcessEnginePlugin`s. With this it is possible to hook into `preInit`, `postInit` and `postProcessEngineBuild` which provides more complex possibilities.

If you have implemented an `CamundaConfiguration` you have to switch to `ProcessEnginePlugin` (and its `preInit` method). You can also extend your configuration from `org.camunda.bpm.spring.boot.starter.configuration.impl.AbstractCamundaConfiguration` to avoid a cast to `SpringProcessEngineConfiguration`.

### Roadmap

* [Milestone 1.3.0](https://github.com/camunda/camunda-bpm-spring-boot-starter/milestone/4?closed=1)
* [Milestone 2.0.0](https://github.com/camunda/camunda-bpm-spring-boot-starter/milestone/3) - Java8 + Spring Boot 1.4

## Maintainer

*  _[Oliver Steinhauer](https://github.com/osteinhauer)_
*  _[Jan Galinski](https://github.com/jangalinski)_
*  _[Christian Lipphardt](https://github.com/hawky-4s-)_

## License

* [Apache License, Version 2.0](./LICENSE)

