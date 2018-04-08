## Interfaces  
- set of requirements
- only contains method delcarations
- all methods are implicity public
- a class **implements** an interface
- cannot instantiate an interface
- cannot declare instance variables
- does not enforce state **only** behavior
  
   

#### Comparable interface
- allows you to sort custom object/define a natural order



#### interfaces vs. abstract classes:
- a class can implement multiple interfaces, but only one class
- if a subclass extends an _abstract_ class it only has to contain the abstract methods it contains
- if a sublcass implements an _interface_ it *must* contain all methods of the interface
- variables declared in an interface are final by default, but may be declared otherwise

#### When to use an abstract class:
-  there are some related classes that need to share many common methods or fields
-  you need to declare fields that are not static and final


#### When to use an interface:
- you want to specify the behavior of a data type, but are not concerned about who implements is behavior.   


#### Using multiple interfaces:
- if two interfaces have conflicting default methods, you need to implicitly tell the compiler which method to call


#### 






