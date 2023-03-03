### Exercise 01

**Formula**: $(not A and B) and (C or D)$

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
    <td>T</td> 
    <td>F</td>
    <td>F</td>
    <td>F</td>  
  </tr>     
</table>

The given test suite doesn't satisfy the MC/DC cos it doesn't satisy the Condition/Decision coverage to begin with.