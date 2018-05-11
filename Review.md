## Final
### Final Variables
* always contain the same value
* if a final variable holds a reference to an object, the state may be changed by operations, but the variable will always refer to the same object
* primitives can be made immutable with the `final` modifier
* the variable's pointer to the value cannot change

### Final Classes
* cannot be subclassed

### Final Methods
* cannot be overridden by subclasses
* cannot be hidden by subclasses


## Static
### Static variables
* allows a variable to be used without first creating an instance of the class
* a static class member is associated with the class itself, rather than an object. **All class instances share the same copy of the variable**
* **When to use:**
	
	
### Static methods
* Can only access static data
* _Cannot access_ instance variables
* Can be accessed via the class directly
	* **When to use:**
		* If you have a method that takes arguments and outputs data, but never deals with instance data of the class
		* 


```java
public class myClass {
	static int days_in_week = 7;
}

public class myOtherClass {
	static void main(String[] args) {
		System.out.println(myClass.days_in_week);
	}
}
```


## Access Modifiers


**Modifer**         | Class     | Package   | Subclass  | World     |       
--------------------|-----------|-----------|-----------|-----------|
Public              | 		Y	  |     Y     |     Y     |     Y     |
Protected           | 		Y	  |     Y     |     Y     |     N     |
Private             | 		Y	  |     N     |     N     |     N     |
Default             | 		Y	  |     Y     |     N     |     N     |



## Inheritance





