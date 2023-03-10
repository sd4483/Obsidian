### Exercise 01

**Formula**: $(not A and B) and (C or D)$
The given test suite doesn't satisfy the MC/DC cos it doesn't satisy the Condition/Decision coverage to begin with.

**Test Cases** 
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr>  
  <tr>  
    <td>1</td>  
    <td>T</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td> 
    <td>F</td> 
  </tr>
  <tr>  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>
  <tr>  
    <td>3</td>  
    <td>T</td>  
    <td>F</td> 
    <td>T</td>
    <td>T</td>
    <td>F</td>  
  </tr>
  <tr>  
    <td>4</td>  
    <td>F</td>  
    <td>F</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>
  <tr style="color: red;">  
    <td>5</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>       
</table>

**Unique cause approach**
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - A</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr>  
  <tr style="color: red;">  
    <td>1</td>  
    <td>T</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>F</td>  
  </tr> 
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>
  </table>  
  <table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - B</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>F</td> 
    <td>T</td>
    <td>F</td>
    <td>F</td>  
  </tr>     
</table>
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - C</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>     
</table>
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - D</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>T</td>
    <td>T</td>  
  </tr>     
</table>

**Masking approach**

<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - A</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr>  
  <tr style="color: red;">  
    <td>1</td>  
    <td>T</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>F</td>  
  </tr> 
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>T</td>
    <td>T</td>  
  </tr>      
</table>
  <table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - B</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>F</td> 
    <td>F</td>
    <td>T</td>
    <td>F</td>  
  </tr>     
</table>
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - C</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>F</td>
    <td>T</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>F</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>     
</table>
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case - D</th>  
    <th style="text-align:center">A</th>  
    <th style="text-align:center">B</th>
    <th style="text-align:center">C</th> 
    <th style="text-align:center">D</th>  
    <th style="text-align:center">Expected Output</th>
  </tr> 
  <tr style="color: red;">  
    <td>1</td>  
    <td>F</td>  
    <td>T</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>
  <tr style="color: red;">  
    <td>2</td>  
    <td>F</td>  
    <td>T</td> 
    <td>T</td>
    <td>T</td>
    <td>T</td>  
  </tr>     
</table>


### Exercise 2

##### Task 01

```Java
boolean swapped

int i

int[] items

int swap
```

##### Task 02

![[Screenshot 2023-03-10 at 3.13.52 PM.png]]
<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Variable</th>  
    <th style="text-align:center">Defined At</th>  
    <th style="text-align:center">Used At</th>
  </tr>  
  <tr>  
    <td>swapped</td>  
    <td>2, 4, 12</td>  
    <td>3</td> 
  </tr> 
  <tr>  
    <td>i</td>  
    <td>5</td>  
    <td>6, 7, 8, 9, 10, 11</td> 
  </tr> 
  <tr> 
	  <td>items</td>
	  <td>10, 11</td>
	  <td>6, 8, 9</td>
  </tr>
  <tr>
	<td>swap</td>
	<td>9</td>
	<td>11</td>
  </tr>
 
</table>

##### Task 03

<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Test Case</th>  
    <th style="text-align:center">Input</th>  
    <th style="text-align:center">Output</th>  
    <th style="text-align:center">Execution Path</th>
  </tr>  
  <tr>  
    <td>1</td>  
    <td>[4,3,2]</td>  
    <td>[2,3,4]</td> 
    <td>1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 6, 7, 8, 9, 10, 11, 12, 13, 6, 7, 8, 9, 10, 11, 12, 13</td> 
  </tr>   
</table>
