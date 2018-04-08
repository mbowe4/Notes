# Test Driven Development
1. You may not write production code until you have written corresponding unit test
2. You may not wirte more of a unit test than is needed to fail, and not compiling is failing
	* you don't have to test two cow objects in example below, just one cow
3. You may not write more production code than is sufficient to pass current failing test

#### Defensive Coding
* make sure software fails in a predictable way

#### Example Unit Test:

```java
Public class cowTest {

	@Test
	Public void speakTest() {
		
		//Given
		Cow cow = new Cow();
		
		//When
		String expected = "moo";
		String actual = cow.speak();
		
		//Evaluate
		Assert.assertEquals(expected, actual);
	}
}
```

### Writing Good Tests:
* Should follow **SOLID** principles, esp. _single responsibility_
* A clean test is a readable test
* A good test should only come to a binary conclusion, which should be quick and easy to understand 
* **_FIRST_**:
	1. **F**: Fast. i.e. not dependent upon a database
	2. **I**: Independent. Every test is an island. Should not have to fire off other methods to complete itself.
	3. **R**: Repeatable. Every test should be able to run in any environment.
	4. **S**: Self-Validating. Every test should have a binary boolean ouput (pass or fail).
	5. **T**: Timely. Tests should be written before production code.

	
	