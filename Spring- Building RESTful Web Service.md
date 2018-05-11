# Spring: Building RESTful Web Service

* Difference between get methods in Spring and regular Java

#### Spring:

```java
@RequestMapping("/greeting")
public Greeting greeting(@RequestParam(value="name", defaultValue="World") String name) {
	return new Greeting(counter.incrementAndGet(), String.format(template, name));
}
```


#### Java:

```java
public Greeting greeting(String name) {
	return new Greeting(counter.incrementAndGet(), Stirng.format(template, name));
}
```