# Collection of Collections
- Lists: ordered, indexed
- Set: unique elements, can be sorted
	- SortedSet
- Queue: FIFO
- Deque: FIFO & LIFO, double ended
	- acts as a stack
- Maps: key value pairs
- _Collection extends Iterable class_

### Segregation of Interfaces & Implementation

#### Interfaces:
* Multiple Data Structures
* Functional
* prefer as vaiable type: code to the interface
* defines behavore

#### Implementation:
* Specific data structure
* can be instantiated
* muliple implemenataions of each interface

## Choosing a collection to use:
1. see flow chart

## Collection Behaviors
1. **Iteration**
2. **Sizing**
3. **Mutation**

# Using Iterators
* if you want to modify a collection while looping through it use an iterator

```java
final Iterator<Product> productIterator = products.iterator();
while (productIterator.hasNext()) {
	Product product = productIterator.next();
	if (product.getWeight() > 20) {
		System.out.println(product);
	} else {
		productIterator.remove();   // Allows you to iterate through a collection and remove at the same time
	}
}
```

* if you don't use an Iterator you will get a `ConcurrentModificationException`
* the for each loop uses an Iterator behind the scenes

### Implementing Iterable Interface

```java
public class UrlLibrary implements Iterable<String> {
	private LinkedList<String> urls = new LinkeList<String>();
	
	public UrlLibrary() {
		urls.add("http://.....,");
		urls.add("http://......");
		urls.add("http://......");
	}
	
	@Override
	public Iterator<String> iterator() {
		return urls.iterator();  // using built in iterator of the LinkedList
	}
}
```




## List Interface
#### Key Features
* **Order:** have clearly defined iteration order aka an index
* **Modification:** can modify Lists using indices
* **Lookup:** find values by index
* **View:** sublists





















