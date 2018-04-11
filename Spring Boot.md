# Spring Boot
* Spring boot provides a set of starter project templates to reduce time spent in set-up (configuration, setting dependencies, writing boiler-plate code)
* Helps devs focus only on the application business logic and leaves the heavy lifting to the Framework
* With Spring Boot you can easily create standalone applications that use an embedded server
	* ex: you don't have to find a servlet container to deploy the application
* Spring Boot is *"opinionated"* in that it will help you follow the best practices for created Spring applications
* Spring is RESTful and therefore stateless
* In the MVC pattern Spring is not the database

## Why Spring Boot??
* reduced time of developments & deployment
* easily create enterprise-production-ready Spring applications
* embedded containers such as Tomcat, Undertown, Jetty, etc.

#### Maven & Spring Boot
* Maven is a build/dependency managment tool that allows you to delcare all dependencies in a single file (pom.xml)
* Maven takes all the dependencies in the pom.xml and then communicates with a dependency Repository to download corresponding jars to the classpath

### How does Spring Boot know how to run?:
* Spring Boot inspects your code, and, based on the annotations `@RestController` and `@RequestMapping` tries to execute your code as a web app via an embedded **Tomcat server** and running it from within

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
* POJO that is managed by the container -> the lifecycle is managed by Spring


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

* **`@RequestParam`**: binds Servlet request parameters to handler/controller method parameters
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
* you can also add sortable and paging actions to your data 

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
* Spring Boot uses `@SpringBootApplication` and the auto-configuration based on the `@EnableAutoConfiguration` annotation to identify all the components
	1. Inspects classpath and configures app. accordingly (ex: web application)
	2. Identifies controllers (things marked with `@Controller` & contain `@RequestMapping` annotations)
	3. If the app has the Tomcat server as a dependency, it will use it when the app is run

## Tests

**Example Test:**

```java
class SimpleWebTest {
	
	@Test
	void greetingsTest() {
		assertEquals("Spring Boot Rocks," new WebApp().greetings())
	}
}
```

* To run test: `spring test app.groovy test.groovy`

* `@WebApplicationContext`: used to test a web app, loads the org.springframework.web.context.WebApplicationContext implementation, which ensures that all the files and beans related to the app are accessible

## Domain Driven Design

* Domain: the subject area on which the application is intendted to apply. The sphere of knowledge around which the application logic revolves
* Understand domain in which problem resides
* Not forcing a framework/language to solve a problem it isn't best suited for

## Spring and Pivotal
* spring boot
* spring cloud
* spring data
* spring security
* spring batch

## .jar & .war files
* **_.jar files_**: contain libraries, resources & accessories files
* **_.war files_**: contains the web application that can be deployed on any servlet/jsp container. The .war file contains jsp, html, javascript and other files necessary for the development of web applications

## REST controllers
* **What is a controller?**: a java class marked with annotations that has info about:
	1. What URL access triggers it
	2. What method to run when accessed
* Means you have methods that map to URL requests
* this method executes when the user makes a reques to that URL

```java
@RestController //designates class as a controller
public class HelloController {

	@RequestMapping("/hello")
	public String sayHi() {
		return "Hi";
	}
	
}
```

## Building a REST API
1. Identify the resources (usually nouns)
2. Identify how the user can access the resources (HTTP methods)
3. 
	


