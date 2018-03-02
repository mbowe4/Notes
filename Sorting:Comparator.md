# Sorting Lists  


## Comparator Interface:
* if you want to sort in some way other than the "natural order" you have _create_ a class to implement the **comparator interface**
		* aka: sort your String variables in order of length:
		
```java
class StringLengthComparator implements Comparator<String> {

	@Override
	public int compare (String s1, String s2) {
		int len1 = s1.length();
		int len2 = s2.length();
		
		if(len1 > len2) {
			return 1;
		} else if (len 1 < len2) {
			return -1;
		}
		
		return 0;
	}
}
```

* Once you implement the Comparator class, to use it, just create a new instance of it and pass it to Collections.sort()
* this example sorts by string length:


```java
public class App {
	
	public static void main (String[] args) { 
		List<String> animals = new ArrayList(String()
		
		animals.add("Tiger");
		animals.add("lion");
		
		Collections.sort(animals, new StringLengthComparator());
	}
}
```

##compareTo Method:
* can be used to sort arbitrary objects

```java
List<Person> people = new ArrayList<Person>();

people.add(new Person(1, "Joe"));
people.add(new Person(3, "Bob"));
people.add(new Person(2, "Claire"));

Collections.sort(people);  // This would *not* work by itself
						// the Person object does not have natural order
```

####Sort in order of name:

```java
Collections.sort(people, new Comparator<Person>() {
	public int compare(Person p1, Person p2) {
		return p1.getName().compareTo(p2.getName());
	}
});

```


## Natural Ordering
* to define the natural order: `class Person implements Comparable<Person> {}`










