**Group Members**

Sudheer Paturi - 2232843
Dominik Wieczynski - 2237383
Pragun Joshi - 

---

### Problem 01

##### Question 01
![[Screenshot 2023-03-14 at 8.12.54 PM.png]]
##### Question 02

The program doesn't have any unreachable nodes or infeasible edges. There is atleast one input for which, each edge and node of the program is reachable. 

For example, 

If we give the inputs $[1,2,3,5,6,7,8,9,10]$ and $7$, the nodes $1,2,3,4,5,6,7,8,9,10,11$ are reachable. 

If we give the inputs $[2,3,5,6]$ and $1$, the nodes $1,2,3,4,5,6,8,9,14$ are reachable. 

And finally, if we give the inputs $[2]$ and 1, the nodes $1,2,3,4,14$ are reachable. 

The above three examples gives the insight that all the edges of the program are reachable as well.

**Observation:** The program has an infeasible path $\langle 1,2,3,4,5,6,8,10,11,4,14 \rangle$. When given an input that's higher than any number in the input list and that doesn't exist in the input list should take that path, but the program ends in an infinite loop. 

##### Question 03
Minimal test suite that provides $C_1$ coverage but doesn't provide $C_i(2)$ coverage.
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Array []xs</th>  
    <th style="text-align:center">Find x</th>  
    <th style="text-align:center">Expected Output</th>
    <th style="text-align:center">Observed Output</th>
  </tr>  
  <tr style="text-align:center; width:100%;">  
    <td>1</td>  
    <td>{1,2,3,5,6}</td>  
    <td>5</td> 
    <td>3</td>
    <td>3</td>  
  </tr>   
  <tr style="text-align:center; width:100%;">  
    <td>2</td>  
    <td>{2,3,5,6}</td>  
    <td>1</td> 
    <td>-1</td>
    <td>-1</td> 
  </tr>   
</table>

##### Question 04
Minimal test suite that provides $C_i(2)$ coverage. The while loop executes 0, 1, 2 times. However the nodes 8 and 9 of the program are never executed for any of the following test cases, thus it doesn't achieve $C_0$ coverage.
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Array []xs</th>  
    <th style="text-align:center">Find x</th>  
    <th style="text-align:center">Expected Output</th>
    <th style="text-align:center">Observed Output</th>
  </tr>  
  <tr style="text-align:center; width:100%;">  
    <td>1</td>  
    <td>{1}</td>  
    <td>1</td> 
    <td>0</td>
    <td>-1</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>2</td>  
    <td>{1,2,3}</td>  
    <td>2</td> 
    <td>1</td>
    <td>1</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>3</td>  
    <td>{1,2,3,5,6,7}</td>  
    <td>5</td> 
    <td>3</td>
    <td>3</td>  
  </tr>    
</table>

##### Question 05
Minimal test suite that provides $C_1$ coverage as well as $C_i(2)$ coverage. The test suite contains test cases that reach all edges of the program and also cases that provide $C_i(2)$ coverage by executing the while loop 0,1,2 times. 
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Array []xs</th>  
    <th style="text-align:center">Find x</th>  
    <th style="text-align:center">Expected Output</th>
    <th style="text-align:center">Observed Output</th>
  </tr>  
  <tr style="text-align:center; width:100%;">  
    <td>1</td>  
    <td>{2}</td>  
    <td>1</td> 
    <td>-1</td>
    <td>-1</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>2</td>  
    <td>{1,2,3}</td>  
    <td>2</td> 
    <td>1</td>
    <td>1</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>3</td>  
    <td>{2,3,4}</td>  
    <td>2</td> 
    <td>0</td>
    <td>0</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>4</td>  
    <td>{2,3,4,5,6}</td>  
    <td>5</td> 
    <td>3</td>
    <td>3</td>  
  </tr>    
</table>

##### Question 06

The loop executes infintely for test inputs of x that don't exist in the array inputs of xs. For example, take {1,2,3,5,6,7} as xs array input and for x take 4 as input. The expected behaviour og the program is that the loop should execute 2 times and return -1 as the output. But the program goes into a continous loop. This is something that should have been caught in the $C_i(2)$ test suite coverage but wasn't. 

##### Question 07

Considering the test suite written in Task 03 above, we can find an example.
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Array []xs</th>  
    <th style="text-align:center">Find x</th>  
    <th style="text-align:center">Expected Output</th>
    <th style="text-align:center">Observed Output</th>
  </tr>  
  <tr style="text-align:center; width:100%;">  
    <td>1</td>  
    <td>{1,2,3,5,6}</td>  
    <td>5</td> 
    <td>3</td>
    <td>3</td>  
  </tr>   
  <tr style="text-align:center; width:100%;">  
    <td>2</td>  
    <td>{2,3,5,6}</td>  
    <td>1</td> 
    <td>-1</td>
    <td>-1</td> 
  </tr>   
</table>
In the second test case, the input for $x$ is 1 which is not in the input array and is lower than the smallest number in the input array. For that input $x = 1$, the expected and observed outputs are the same. 

But considering the same test case, if we give an input that doesn't exist in the array and one that's higher than the smallest number, the expected output is $-1$ but that doesn't match with the observed output, which is an 'infinite loop'.

That is a fault in the program that is not detected by the test suite. 

##### Question 08

In the first test case, the input for $x$ doesn't exist in the array input, and therefore the expected output is -1 but the observed output is 'Infinite loop'.

In the second test case, the lenght of the array is even digits. For the inputs given, the expected output is 2 but the observed output is 'Infinite loop'.

In the third test case, the length of the array is odd digits. For the inputs given, the expected output is 2 but the observed output is 'Infinite loop'.
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Array []xs</th>  
    <th style="text-align:center">Find x</th>  
    <th style="text-align:center">Expected Output</th>
    <th style="text-align:center">Observed Output</th>
  </tr>  
  <tr style="text-align:center; width:100%;">  
    <td>1</td>  
    <td>{1,3,5}</td>  
    <td>4</td> 
    <td>-1</td>
    <td>Infinite loop</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>2</td>  
    <td>{1,2,3,4}</td>  
    <td>3</td> 
    <td>2</td>
    <td>Infinite loop</td>  
  </tr>
  <tr style="text-align:center; width:100%;">  
    <td>3</td>  
    <td>{1,2,5}</td>  
    <td>5</td> 
    <td>2</td>
    <td>Infinite loop</td>  
  </tr>    
</table>
