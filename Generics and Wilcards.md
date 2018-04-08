# Generics and Wilcards
- This loop can be used to pass any arrayList of objects that is a subclass of Machine
- This is becuase the wildcard "?" *extends* Machine
- However, only Machine methods can be used in this example, Camera methods are not available

```java
public class App {	
	public static void showList(ArrayList< ? extends Machine > list) {
		for (Machine value: list) {
			System.out.println(value);
		}
	}
	
	public static void main(String[] args) {
		ArrayList<Machine> machineList = new ArrayList<Machine>();
		
		machineList.add(new Machine());
		machineList.add(new Machine());
		
		ArrayList<Camera> cameraList = new ArrayList<Camera>();
		
		cameraList.add(new Camera());
		cameraList.add(new Camera());
		
		showList(machineList); // can pass in either list and it would work
	}
}
```

### Defining Generic Class
- T: compiler assumes *Object* is upper bound unless you specify T extends anther class
- **Bounds:** when extending T must always be a subtype of its bounding type

### Defining Generic methods
- ex: `public static <T> T getmiddle(T... a) {...etc....};`

### Type Erasure
- at compile time type parameters are erased and replaced with Objects

### Bridge Methods
- created by the compiler to cast

### Limitations of Generics
- no primitive types
- no runtime type inquiry on inner types
- no arrays of paramaterized type (compiler will make them into Objects)
- cannot be instantiated directly
- no generic arrays
- cannot be used as statics or genric classes


































