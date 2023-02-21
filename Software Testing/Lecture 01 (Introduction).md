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
5. Validation

#### **A simple example:**

##### **==1. Requirment==** 
Compute the square root of a non-negative number.

##### **==2. Specification==** 
Given a double x>=0 compute a double y>=0 such that y^2 = x.

- That's the definition of a square root.

- We use double (64 bit floating point number) cos sometimes square root of a number is not an integer.

##### **==3. Implementation==**

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
- The `testSquareRoot` function could be changed like this:
	```Java
	public static boolean testSquareRoot(double x) {
		double squareRootx = squareRoot(x);
			return squareRootx >= 0 && Math.abs(squareRootx * squareRootx - x) < Math.pow(10.0, -8);
	}
	```
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

- So the requirement given to us which is 'Compute the square root of a non-negative number', we come up with a specification for that and we verified the specification. So we can say that we satisfied the requirement provided by the client.
- 
##### **==4. Verification==**
