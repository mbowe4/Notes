# Threading
## Implementation
* implementing the `Runnable` interface
	* functiontioal interface with `void run();`
	* `Thread t = new Thread(r);` where r is Runnable
	* Thread is started by calling `t.start();`
* Extending the Thread class

``` java
class MultithreadingDemo extends Thread {
	public void run() {
		try {
			// Displaying the thread that is running
			System.out.println ("Thread " + Thread.currentThread().getId() + " is running");
		}
		catch (Exception e) {
			//Throwing an exception
			System.out.println("Exception is caught");
		}
	}
}

// Main Class
public class Multithread {
	public static void main (String[] args) {
		int n = 8; // Number of threads
		for (int i = 0; i < 8; i++) {
			MultithreadingDemo object = new MultithreadingDemo();
			object.start();
		}
	}
}


```

#### Thread States
* New -> Runnable -> Running -> Terminated(Dead state)

#### Thread Synchronization
- **Race conditions:**multiple threads have access to the same object and try to modify that object
	- *Locks* used to allow synchronized access to a thread
	- *DeadLocks:* when two or more threads are waiting for the other to release a lock


#### Monitor
- Monitor (intrinsic lock on object)

```java
public void addName(String name) {
	synchronized(this) {
		lastName = name;
		nameCount++
	}
	nameList.add(name);
}
```