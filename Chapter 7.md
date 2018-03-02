# Chapter 7
## Exceptions, Assertions, and Logging

### Classification of Exceptions
-  an exception object is an instance of a class derived from *Throwable*
- _**Exception Hierarchy:**_

![Rendering preferences pane](/Users/madelinebowe/ThrowableHierarchy.png)

- **Errors:** unchecked exceptions
- describe internal errors and resource exhaustion inside java runtime system
	- should not throw an object of this type
	- if error occurs: notify user & terminate program gracefully

- **Exceptions:** checked exceptions
	1. *Runtime Exceptions* are due to a programming error
			- A bad cast
			- out-of-bounds array access
			- null pointer access
	2. **IO Exceptions* code is good, something bad happened to it


### Checked Exceptions
- declared in the method header

```java
class MyAnimation
{
	...
	public Image loadImage(String s) throws FileNotFoundException, EOFException
	{
	...
	}
}
```
- don't declare *unchecked exceptions* or exceptions inheriting from *RuntimeException* because these are not under your control

### How to Throw an Exception:
1. Find appropriate excpetion class  
2. Make an object of that class   
3. Throw it. 

- Once a method throws an exception it does not return to its caller

### Creating Exception Classes
- Derived from *Exception* or child class
- You should provide both a default constructor and a constructor that contains a details message
- **Example for a custom Exception class:**

```java
class FileFormatException extends IOException
{
	public FileFormatException() {}   // default constructor
	public FileFormatException(String gripe)   // message constructor
	{
		super(gripe);
	}
}
```

### Catching an Exception
- if an exception occurs that is not caught, the program will terminate
- a *try/catch* block is the simplest way prevent this:

```java
try
{
	code
	more code
	more code
}
catch (ExceptionType e)
{
	handler for this type
}
```
- if any code in the *try* block throws an exception of the class specified: 
	1. The program skips the remainder of the code in the try block
	2. The program executes the code inside the catch clause

- if another type of exception occurs the method exits immediately
- you can catch multiple exceptions with separate try/catch clauses **or** catch multiple exception types in the same catch clause

```java
try
{
	code that might throw exceptions
}
catch (FileNotFoundException | UnknownHostException e)
{
	emergency action for missing files and unkown hosts
}
```

### Finally Block
- if no exceptions are thorwn
- if exception outside try block is thrown
- if an exception is thrown in a catch clause
- Programe skips the finally clause if the catch clause does not throw an exception

### Assertions
- *Assert* evaluates a condition and throws an AssertionError if it is false
- **Toggling:** java can be enables by running the program with the -ea option

```java
java -ea MyProject
```

### Logging
- supressed logs are inexpensive; penalty for leaving them in code is minimal
- records can be directed to different handlers: 
		- Console
		- wiriteing to file
		- database
		- plain text or XML

#### Logging levels:
1. default: INFO
2. SEVERE
3. INFO
4. CONFIG
5. FINE 
6. FINER
7. FINEST


```java
Logger logger = new Logger.getLogger(nameOfClass);

...

logger.info("hello world");
logger.sever("logs to severe");
logger.setLevel(Level.SEVERE);  // only print out severe

```


































