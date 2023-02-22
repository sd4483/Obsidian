#### How software is developed (steps involved):
1. **Requirements gathering**
	- Sometimes the requirements are clearly listed down which is not usually the case.
	- Sometimes there's only a business objective and requirements have to be deduced or gathered from the objectives.
2. **Specifications**
	- The requirements are converted into formal specifications so that requirements can be more precise and can be implemented and verified.
3. **Implementation**
	- This is where we actually implement the specification i.e. coding of the software or building the actual product
4. **Verification**
	- This is where we check whether the implementation meets the specification.
5. **Validation**
	- After verifying the specification, if the client requirements are satisfied, in this step we could say we satisfied the requirements.

**These 5 steps are typically performed in an iterative and incremental manner.**

##### Verification vs Validation
- **Formal definitions:**
	- ==**Verification**== 'Are we building the right thing?' (i.e., does the system meet its specification)
	- ==**Validation**== 'Are we building the right product?' (i.e., does the system meet the user's requirements?)
- Validation is usually done at the end of the developement of a certain part of the prototype or it could be after the entire software has been built.
- Verification occurs at every stage of development.

##### Software Development Processes
- If the product built is not what the client actually wants, that means the specification was wrong and the entire software might even have to rebuilt.
- In order to address the issue of products not meeting requirements or specifications  being wrong, people have come up with a number of software development process.
- There are ==**two central themes**== in the software development processes:
	- **Avoid the introduction of faults in advance** (eg. through proper design and documentation)
	- **Quickly produce working prototypes** of parts of the product for verification and validation
	- These two themes are somewhat conflicting cos to quickly build a product, sometimes people rush into it without a clear understanding of the requirements. On the other hand, to have a clear requirement with proper design and documentation could delay the whole process.
- Often times it'll be one or other themes that the project is mostly based on. But ==**what theme is chosen depends on the stakeholder requirements and our expectation of where the critical faults might arise**==. 
- If the requirements are clear from the clients, then there might not be many critical errors to deal with, but if they are not, then quickly working on some proptotypes and getting feedback from the client - asking them whether that is what they want, would be the way to go. 
- It's important to understand the risks involvded ("risk profile") in the project to select the appropriate path to take the project in. Or else risk analysis itself plays a prominent role.
- ==**Verification and validation are key steps**== - these are the steps where faults are identified typically and in early stages. If faults go undetected for a long time, they become more and more expensive to fix.
- Here is where ==**SOFTWARE TESTING**== comes in. It involves verification and vaildation of the system to assess whether it meets our requirements and precisely whether it works the way its intended.

#### Software Testing
- Software testing involves verification and vaildation of the system to assess whether it meets our requirements and precisely whether it works the way its intended. [repeated from above]
>"**Testing can be used to show the presence of bugs, but never to show their absence.**"
>\- Dijkstra, 1970

- What the above quote means is, ==**testing shouldn't be used as a way to show or convince ourselves that the system works the way it's supposed to without any errors**==. It should be used to check for the presence of bugs (or faults in the software).
>[!tip] Philosophy 
>- It shouldn't be used as evidence to support your theory that the program works correctly. It should be the other way around, testing to challenge your assumptions and find some evidence to test whether the system works appropriately.
>- Your attitude shouldn't be - let's try to test it to see if it works. It should be - let's try to break it and if cannot break it, there's some evidence that it works. 
- **Testing strategy**
	- A good testing strategy is designed to find as many faults as possible.
	- A good testing strategy would be - I tried my hardest to break the program and I couldn't break it.
- **Testing Lifecycle**
	- Error --> Fault --> Failure --> Incident
	- **Software development process:**
		- Requirements specification -> Design -> Coding -> Testing
		- In each of these steps errors could happen which would lead to some faults.
	- **Testing process:**
		- Testing -> Fault classification -> Fault isolation -> Fault resolution
		- In testing, we want to resolve the faults, first by understand what kind of fault it is, where it occured and then provide some resolution to that fault.
		- It's possible that in this process new errors might happen which would then need to be resolved.
- **Test case**: description of a single experiment
- **Test suite**: collection of test cases
- While designing a test suite, keep in mind the ==**Coverage vs Complexity trade-off**==.
	- **Coverage**: Extent to which a test suite covers the qualitativelty different behaviours of the system under test (SUT).
		- We want to cover as many different behavious of the system as possible. 
		- Coverage could also depend on our own definition of what we want to cover in the test suite (**==coverage criteria==**).
		- The idea is to have a high coverage -> high ability to detect faults in the system
	- **Complexity**: Measure of the costs of constructing, executing, and maintaining a test  suite.
		- Which costs are most relavent is highly context dependent.
	- Typically, it's a good idea to have high coverage and low complexity. Fix the coverage and minimise the complexity.

##### Testing vs Formal Verification
- ==**Formal verification is another way to verify the software using mathematical analysis of the code.**== 
	- A formal specification is used to check whether the program adheres to it.
		- Done using either by automated methods or manually with the help of a proof assistant.
	- Verfification is only as good as the formal specification.
- Formal verification can offer stronger guarantees but is costlier and requires greater expertise.
- Testing is considered as a poor mans way to verifying the software.
- There are things you can do with formal verification that can't be done with testing, but it's not that one is better than the other, these methods often complement each other.
- It's important to remember that no formal verification can truly capture all aspects of the system. Things like for example user experience which could play a huge role in the success of the product can't be tested using formal verification.
>"**Beware of bugs in the above code; I have only proved it correct, not tried it.**"
>\- Donald Knuth

##### Unit Testing
- Testing a `unit` in isolation
	- ==**Unit**== - A piece of software that delivers a single functionality (a single class/function/module).
- Unit testing should be done in isolation of the unit to verify it's functionality but typically `units` are dependent on other units.
	- 'Test stubs' are used to mock the behaviour of the dependent units when doing unit testing.
- '==**bottom up**==' approach - Test units that are not dependent on other units first and assume they are correct. Then move on to testing units that are dependent on other units.
- ==**Motivation**== behind unit testing is, '**fault isolation**' + '**complexity reduction**' (we reduce the complexity by testing smallest components of the software)
---
#### **A simple example:**

##### 1. Requirment
Compute the square root of a non-negative number.

##### 2. Specification
Given a double x>=0 compute a double y>=0 such that y^2 = x.

- That's the definition of a square root.

- We use double (64 bit floating point number) cos sometimes square root of a number is not an integer.

##### 3. Implementation

```Java
package square_root;

public class SquareRoot {
	public static double squareRoot(double x) {
		double guess = x;
		double previousGuess;
		
		do {
			previousGuess = guess;
			guess = 0.5 * (guess + x/guess);
		} while (previousGuess != guess);
		
		return guess;
	}
	
	public static boolean testSquareRoot(double x) {
		double squareRootx = squareRoot(x);
		return squareRootx >= 0 && squareRootx * squareRootx == x;
	}
}
```
- The above implementation kind of implements the specification given. The square root can be calculated for certain inputs like 4, 9, 16, etc. 

- But it fails for certain inputs like 0 for example and negative numbers. But that's okay to a certain extent cos the specification doesn't state what needs to be done for inputs like that. So it's more for a specification issue rather than a verification of specification issue.

- One way to solve the 0 input issue is to change the implementation like this:
	``` Java
		public static double squareRoot(double x) {
		
		if (x ==0) {
			return 0;
		}
		else {
			double guess = x;
			double previousGuess;
			
			do {
				previousGuess = guess;
				guess = 0.5 * (guess + x/guess);
			} while (previousGuess != guess);
			
			return guess;
		}
	}
	```

- But this still doesn't solve the issues with inputs like 2, 6, 12, etc.

- So the insight we got here is that, it's not always possible to compute the square root of a number. Specifically if the number is an irrational number like 2. 

- So the <u>specification we got is wrong</u>, we can't always compute the exact square root of a number but we can compute something close to that.

- Based on the above, the specification could be changed as follows:
	- If x < 0, throw an exception for negative input.
	- Given a double 'x' less than 50 million ==(50,000,000 >= x >= 0)==, compute a double ==($y \geq 0$)== such that the difference of square of y and x is less than $10^{-8}$ ie. ==($| y^2 - x | < 10^{-8}$ )==
<br>
- The `squareRoot` method could be changed like this:
	```Java
	public static double squareRoot(double x) {
		
		if(x < 0) {
			throw new IllegalArgumentException("Cannot compute square root of negative number" + x);
		}
		else if(x == 0) {
			return 0;
		}
		else {
			double guess = x;
			double previousGuess;
			
			do {
				previousGuess = guess;
				guess = 0.5 * (guess + x/guess);
			} while (previousGuess != guess);
			
			return guess;
		}
	}
	```

##### 4. Verification
- The `testSquareRoot` function could be changed like this:
	```Java
	public static boolean testSquareRoot(double x) {
		double squareRootx = squareRoot(x);
			return squareRootx >= 0 && Math.abs(squareRootx * squareRootx - x) < Math.pow(10.0, -8);
	}
	```

##### 5. Validation
- So the requirement given to us which is 'Compute the square root of a non-negative number', we come up with a specification for that and we verified the specification. `So we can say that we satisfied the requirement provided by the client.`

- But the <u>client might not agree with the specification we came up with</u> and might have some opinions regarding for example, instead of the difference of square of y and x being less than 10 to the power -8, they might want it to be something like `the difference between y and square root of x to be less than 10 to the power -n` (some number they provide). And also they might want the x to be in a different range rather than limited to 50 milliion and 0. 
	> [!note]
	> So it's important to have this validation step to ask ourselves ==Are we developing the right thing?==
- The problem in the example we chose is, the requirements are a bit ambiguous. It's not clear what to do when there is a negative input and not clear what to do with irrational inputs (2,6,12, etc.) So we came up with a specification ourselves that could address these issues but at the end, client had different opinions regarding that.

	>[!tip] My understanding
	>It's important to get as clear requirements from the client as possible so that the specification is close to what the systems needs to actually do or to be precise, to build the product the client actually wants.


