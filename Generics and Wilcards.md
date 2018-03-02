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