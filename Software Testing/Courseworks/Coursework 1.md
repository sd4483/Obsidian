**Group Members**

Sudheer Paturi - 2232843
Dominik
Pragun Joshi

---

### Problem 01

##### Task 01
```mermaid
flowchart LR
	id1((1)) --> id2((2)) --> id3((3)) --> id4((4)) --> id14((14))
	id4 --> id5((5)) -->id6((6)) --> id7((7))
	id6 --> id8((8)) --> id9((9)) --> id4
	id8 --> id10((10)) --> id11(11) --> id4
	
```

##### Task 02

The program doesn't have any unreachable nodes or infeasible edges. There is atleast one input for which each edge and node of the program is reachable.

##### Task 03
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
    <td>{1,2,3,5,6}</td>  
    <td>2</td> 
    <td>1</td>
    <td>1</td> 
  </tr>   
</table>

##### Task 04
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

##### Task 05
{1,2,3}

{1} 1 -1

