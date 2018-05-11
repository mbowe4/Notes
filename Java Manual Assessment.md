# Java Manual Assessment

## What are the 3 parts that make up an object?
* _**Identity**_: how the object is distinguished from others of the same class with the same state & behavior
* **_State_**: how the object reacts when you invoke method on it
* **_Behavior_**: what you can do with the object or what methods can be applied to it

## What is a class in Java?
* A class is the blueprint for an object
* All code in Java must be inside of a class

## What is a multidimensional Array? Show an example:
* A multidimensional Array is an Array that uses two indexes to reference an element. It is typically used when there is a need for a matrix, for example in a chess game could be layed out using a multi-dimensional array

```java
int[][] matrix = 
{
	{1, 2, 3, 4, 5, 6},
	{7, 8, 9, 10, 11, 12},
	{13, 14, 15, 16, 17, 18}
};

// to access the number 6: int[0][5]
```

## What are examples of mutator and accessor methods?
* **_Mutator methods_**: mutator methods change the state of the object it is invoked upon. An example is a setter:

```java
public void setName(String name) {
	this.name = name;
}
```

* **_Accessor methods_**: access objects without modification. An example is a getter:

```java
public String getName() {
	return this.name;
} 
```

## What does API stand for?
* API stand for Application Programming Interface. An API in the context of Java is a collection of pre-written packages, classes, and interfaces with their respective methods, fields and constructors. An API serves to facilitate interaction with a software program. Can help in minimizing the amount of code being written in a class.


## What is the difference between an empty string value and a null string value?
* An empty string value is a String object with length 0 that references those empty contents. 
* A String with a null value does not yet have reference to any specific object.


## What is the difference between StringBuilder and StringBuffer?
* StringBuilder and StringBuffer in that they are both mutable, however, StringBuffer is thread-safe and more suitable for multi-threaded environments. StringBuilder is faster, and is preferred in single-thread environments.


## Show some examples of operators and expressions:
* operators: 
	* _multiplication_: `*`
	* _addition_: `+`
	* _division_: `/`
	* _modulus_: `%`, ex: `10 % 2 = 0`
	* ex: `a += 2`
	* ex: `a *= a`
	* _comparisons_: 
		* **less than**: `a < b`
		* **greater than**: `a > b`
		* **equal in value**: `a == b`
		* **or**: `a || b`
		* **and**:  `a && b`
	

## What does MVC stand for? What is an example of the model?
* MVC stands for **M**odel, **V**iew, **C**ontroller
* Model stores the data, ex: a database
* View is what the user interacts with
* Controller is 

## What is a modifier?

## Name some types of modifiers:

## Name some types of non-access modifiers:

## What is an immutable type and give an example:

## When would you use the keyword static and waht does static imply?

## What are some primitive data types and what is a primitive?
* **_Primitive_**: a primitive is the most basic data type in Java. They are the building blocks for data manipulation, and hold fixed values.

![primitive Types](https://github.com/mbowe4/Notes/blob/master/primitiveTypes.png)

## What are packages and what are they good for?
* Packages organize code

## What is an interface?
* An interface is a contract. It specifies a set of requirements/behaviors that implementing classes should have, without regard to *how* it is implemented.
* Contain only method declarations
* Methods are implicity public
* Does not enforce state, only behavior


## Can you instantiate an interface?
* Interfaces cannot be instantiated, they can only be *implemented*

## What is an abstract class?
* An abstract class contains one or more abstract methods. It cannot be instantiated, but is used by instantiating an a class that extends it.
* Subclasses must provide implementations for the abstract methods
* Can contain methods and fields, and declare different levels of access

## Can you instantiate an abstract class?
* NO
* The only way to use an abstract class is to instantiate an inheriting subclass

## What is an anonymous inner class?

## What is a relational database?


















