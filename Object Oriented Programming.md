# Object Oriented Programming

* breaks the problem down into small logical objects, with a single responsibility
* Scalability of solutions over time
* Greater testability

### Object
- In OOP, **Everything is an object**
- Characteristics of an Object:
	* **Identity** - how is it distinguished. What is it’s name
	* **State** - the value of internal objects this object contains **variables store the state**. What does it store?
	* **Behavior** - what services or actions this object can perform. How it acts

### Classes
* Classes are a template
* You construct objects from a specific class
* The object you construct is an instance of that class or an object instance

##### Writing a class
* You write/debug classes
* When you run the program is creates Objects
* Methods describe behavior

### Methods
* Private Method -  no other outside objects can call it
* Static Method- you do not need to create an object to call it
	* example: the Math object
	* Behaves dependent of an object’s state

### Encapsulation: 
* combining data and behavior in one package and hiding the implementation details from the users of the objects
* Object methods should only interact with instance variables

### Naming
* _objects_ = nouns
* _Methods_ = action verbs (should be concise)

### Relationship between classes
* **Dependence**: “*Uses-a*”
	* Ex: timecard object
* **Aggregation**: “*Has-a*”
	* The objects contained inside the class
* **Inheritance**: “*Is-a*” 
* **All objects in java are extended from Object.class except for primitives**


#### Objects and instance variables
* The new keyword tells the JVM to add a new object to the heap

#### Constructors
* Do not have a **TYPE**, they have have a name which is the same as the class name
* No return value
* Always called with the `new` keyword
* A class can have more than one constructor

```java
public class Person {
	public Person() {
	/* set up some defaults*/
	}
}
```

### Mutators & Accessor
* **_Mutator_**: an action or method that changes the *STATE* of an object
* **_Accessor_**: privileges we assign to field objects
	1. Public
	2. Private
	3. Protected
	4. Default
* Allow us to open up or hide different things inside an object



* **Final**: defines a values as constant or consistent.
	* Cannot be mutated by any objects
	* **Ex**: `private final Float pi = 3.14159;`: you wouldn’t wan the value of pi to change


##### Keep in mind:

* Objects are services
* Read java source code
* Assume users are stupid. Use your code to stop them from doing something they shouldn’t

