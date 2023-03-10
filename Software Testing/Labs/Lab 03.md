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

<table style="text-align:center; width:100%;">  
  <tr style="background-color: #dddddd;">  
    <th style="text-align:center">Variable</th>  
    <th style="text-align:center">Defined At</th>  
    <th style="text-align:center">Used At</th>
  </tr>  
  <tr>  
    <td>swapped</td>  
    <td></td>  
    <td>items</td> 
  </tr>   
  <tr>  
    <td>i</td>  
    <td>1</td>  
    <td>1</td> 
  </tr> 
  <tr> 
	  <td>items</td>
  </tr>
  <tr>
	<td>swap</td>
  </tr>
 
</table>
