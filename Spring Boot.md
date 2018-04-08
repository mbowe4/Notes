# Spring Boot
* Spring boot provides a set of starter project templates to reduce time spent in set-up (configuration, setting dependencies, writing boiler-plate code)
* helps devs focus only on the application business logic and leaves the heavy lifting to the Framework
* With Spring Boot you can easily create standalone applications that use an embedded server
* Spring Boot is "opinionated" in that it will help you follow the best practices for created Spring applications

## Why Spring Boot??
* reduced time of developments & deployment
* easily create enterprise-production-ready Spring applications
* embedded containers such as Tomcat, Undertown, Jetty, etc.

### How does Spring Boot know how to run?:
* Spring Boot inspects your code, and, based on the annotations `@RestController` and `@RequestMapping` tries to execute your code as a web app via an embedded **Tomcat server** and running it from within.

##### Example of simple Spring Boot Application:

![Screenschot](/Users/madelinebowe/Desktop/Screen Shot 2018-04-08 at 10.49.16 AM.png)
 
1. The `@SpringBootApplication` annotation and the `SpringApplication` singleton class in the `main` method execute
2. the `run` method call accepts 2 parameters (the class that contains the `@SpringBootApplication` annotation and the applications arguments.)

### Spring IoC Container
* Creates the objects, wires them together, configures them, and manages their complete life cycle
* Uses DI to manage the components aka **Beans** that make up an application
* The container get its instructions on what objects to instantiate, configure & assemble by reading the configuration metadata.
	* The configuration metadata is represented by:
		1. XML
		2. Java annotations
		3. Java code
* POJO classes + configuration metadata => IoC => fully executable application

### Life Cycle of a Bean
1. _Bean is instantiated_
2. _Bean is cleanedup/torndown_

* to define setup/teardown for a bean, declare `<bean>` with **init-method** and/or **destroy-method** parameters


### Annotations:
* **`@Controller`**: designates class an an MVC controller
* **`@RequestMapping`**: maps web requests to handler classes and methods

ex:

```java
/** when a request for home.html is made, the showHomePage method executes.
	It returns the view name "home".
	No model in this example.
**/  

@Controller
public class HomeController {
	@RequestMapping("/home.html")
	public String showHomePage() {
		return "home";
	}
}
```

* **`@RequestParam`**: binds Servelt request parameters to handler/controller method parameters
* **`@SpringBootApplication`**: same as declaring the following 3 annotations:
	* **`@Configuration`**: marks class as containng 1 or more Spring bean declarations
	* **`@ComponentScan`**: tells Spring to scan and look for classes annotated with `@Configuration`, `@Service`, `@Repository`, etc.
	* **`@EnableAutoConfiguration`**: enables Spring's auto-configuration behavior which creates bean configurations based dependencies & configurations in the classpath.  
	
* **`@RestController`**: indicates the application has possible REST endpoints.
	* Same as adding: **`@Controller`** & **`@ResponseBody`**
* **`@OneToMany`**: the `Poll` instance can contain 0 or more Option instances
* **`@OnteTOMany(cascade=CascadeType.ALL)`**: any database operation (persist, remove, merge) on a `Poll` instance needs to be extended to any relation `Option`. Ex: when a `Poll` instance gets deleted, all relation `Option` instances will be deleted also from database
* **`ResponseEntity`**: gives full controll over the HTTP response, including the response body and headers. Used in this example as the return type
* **`@AutoWired`**: instantiates and object (ex: JournalRepository variable repo so it can be used in a method)
* **`@ResponseBody`**: directs Spring MVC to automatically use the correct HTTP message converters to transform the response into JSON data

#### JPA
* Standards-based API for accessing, storing, & managing data between Java objects and relational databases. It is a specification, and there are many implementations (Hibernate, TopLink, etc.)
* Annotationst that indicate data should be persisted to database:
	*  **`@Entity`**: 
	*  **`@Id`**: allows instances of the class to be easily persisted and retrieved using JPA technology
	*  **`@GeneratedValue`**
*  **`@Transient`**: indicates JPA engine not to persist that property
*  JPA needs a constructor with no parameters

#### Spring Data Repository
* **_JpaRepository_**: a marker interaface that allows the Spring Data Repository engine to recognize it and apply the necessary proxy classes to implement the base CRUD actions, but also custom methods.
* you can also add sortabel and paging actions to your data 

#### Repository Implementation / DAOs
* Provide abstraction for interacting with datastores
* provide a pair of repository interfaces and classes for each domain object
* **However**: Spring Data aims at addressing the issue and eliminates the need to write repository implementations
* with JPA use the CrudRepository marker interface
* **CrudRepository Interface**: takes the type of domain object that it manipulates and the type of 

## How Spring Boot Works
##### Things to keep in mind:
* Spring boot never generates code and never outputs any source code
* Simply follows best practices to create a robust application with minimum effort

#### Process of running application:
* Spring Boot uses `@SpringBootApplication` and the auto-configuration based on the corresponding annotation to identify all the components
	1. Inspects classpath and configures app. accordingly (ex: web application)
	2. Identifies controllers (things marked with `@Controller` & contain `@RequestMapping` annotations)
	3. If the app has the Tomcat server as a dependency, it will use it when the app is run

