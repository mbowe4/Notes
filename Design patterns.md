# Design patterns
* Means by which a set of objects communicate
* Established way of solving a problem by object oriented patterns
* _Rule of Three_:
	1. code can be copied once
	2. once it's reused 3 times it should be abstracted into a separate method

### Singleton
* Ensures a class only has one instance and provide a global access point to it

### Creational Patterns:
* **Builder**: Best used when you have a constructor that takes in over _4_ arguments
	* Allows you to construct an object without concern for the order in which the arguments are entered


```java
Person person = new PersonBuilder().setAddress("Address")
										.setCity("Wilmington")
										.setName("Madeline")
										.build();
											
// In the PersonBuilder class use setter that return an instance of the PersonBuilder:

Public PersonBuilder setName(String name) {
	this.name = name;
	return this;
	
// PersonBuilder constructor sets the defaults 	
}
```

**Issues with the factory Pattern**: too many arguments can be error prone

### Structural Patterns
* **Decorator Pattern**: attach additional responsibilities to an object dynamically
	* provides a flexible alternative to sublasssing for extending functionality
* **Adaptors Pattern**: 

### Behavioral Patterns
* **Command Pattern**: decouples what is done from when it is done
	* concrete commands objects are tasks `UNDO_TASK`
* 
