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
The above implementation kind of implements the specification given. The square root can be calculated for certain inputs like 4, 9, 16, etc. 
But it fails for certain 
##### **==4. Verification==**

