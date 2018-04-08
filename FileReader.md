# Reading Files
#### Using Scanner:   


```java
public class App {
	public static void main(String[] args) throws FileNotFoundException {
		String fileName = "example.txt";
		
		File textFile = new File(fileName);
		
		Scanner in = new Scanner(textFile);
		
		while(in.hasNextLine()) {
			String line = in.nextLine();
			
			System.out.println(line);
		}
		
		in.close(); 			//closes the file 
	}
}
```

#### Using FileReader:


```java
public class App {
	public static void main(String[] args) {
		
		File file = new File("test.txt");
		BufferedReader br = null;
		
		try {
			FileReader fr = new FileReader(file);
			
			//read line by line
			//process chars line by line
			br = new BufferedReader(fr);
			
			String line;
			
			while( (line = br.readLine()) != null) {
				System.out.println(line);
			}
			
		} cath (FileNotFoundException e) {
			System.out.println("File not found: " + file.toString());
		} catch(IOException e) {
			System.out.println("Unable to read file: " + file.toString());
		}
		finally {   //will always run even w/excpetions
			try {
				br.close();
			} catch(IOExcpetion e) {
				System.out.println("Unable to close file: " + file.toString());
			}
		  	catch(NullPointerException ex) {
		  		// file was probably never opened
		  }
		}
	}
}
```

