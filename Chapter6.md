# Chapter 6: Interfaces, Lambda Expressions, and Inner Classes  

### Interfaces
- a way of describing *what* classes should do, without specifying *how*
- all methods of an interface are automatically public
- never have instance fields
- can just define constants and no methods - though this is not ideal

### Object cloning
- when you make a copy of a variable holding an object reference, changing the copy also changes the *original*   

```java
Employee original = new Employee("John Public", 5000);
Empoyee copy = original;
copy.raiseSalary(10);   // this also changes the original
```

- to make a new object that can diverge from the original: use the clone method
		- clone method is a protected method of *Object*
		- So in this example, only the Emplyee class can clone Employee objects
		- deep copy vs. shallow copy

### Lamba Expressions
- a block of code that can be passed around to be executed later
- a block of code together with the specification of any variables that must be passed to the code 
- object whose responsibility is to evaluate a function
- **used to defer method calls**

```java
(String first, String second) 
	-> first.length() - second.length()
```
- lambda: mathematical function is effectively computable
- **3 components to a lambda expression:**
		1. parameters
		2. arrow (->)
		3. expression
- if there are no parameters, supply empty parenthese:

```java
() -> {for (int i = 100; i >= 0; i--) System.out.println(i); }
```

### Functional Interfaces
- you can supply a _lamba expression_ whenever an objet of an interface with a single abstract method is expected - aka a *functional interface*

### Inner Classes
- a class defined within another class
- Uses:
		- can access private data
		- can be hidden from other classes in the same package

### Comparators
- comparing method takes a "key extractor" function that maps a type *T* to a comparable type (ex: *String*) 
		- for example: to sort an array of Person objects by name

```java
Arrays.sort(people, Comparator.comparing(Person::getName)); // alone this would sort by name
```

- to break ties if the person has the same first name:

```java
Arrays.sort(People, Comparator.comparing(Person::getLastName)
									.thenComparing(Person.getFirstName));
```

- could also be used to sort by length of their names
	

	























