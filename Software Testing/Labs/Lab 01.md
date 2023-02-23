### Exercise 01

###### Task 01

```mermaid
flowchart LR
	id1((1)) --> id2((3)) --> id3((4)) ---> id10((17)) & id4((6))
	
	id4 ---> id5((8)) & id7((11))
	
	id5 --> id6((9))
	
	id6 --> id3
	
	id7 --> id8((13)) --> id9((14))
	
	id9 --> id3
```

##### Task 02

```mermaid
flowchart LR
	id1((1, 3)) --> id2((4)) ----> id3((6)) ---> id4((8, 9)) & id5((11, 13, 14))
	id2 --> id6((17))
	id5 --> id2
	id4 --> id2
```

##### Task 03

Execution paths of the program:
$\langle 1,3,4,17 \rangle$
$\langle 1,3,4,6,8,9,17 \rangle$
$\langle 1,3,4,6,11,13,14,4,17 \rangle$

##### Task 04

```Java
public static int addNew(int x, int y) 
{	
	int sum = y;   
	do {
	    sum = sum - 1;
	    x = x + 1;
	} while(x <= 0);       
	do {
	    sum = sum + 1;
	    x = x - 1;
	} while(x > 0);
	return sum;     
}
```

**Program graph for the refactored program:**
```mermaid
flowchart LR
	id1((1)) --> id2((3)) --> id3((4)) --> id4((5)) --> id6((6)) --> id7((7)) --> id8((8)) --> id9((9)) --> id10((10)) --> id11((11)) --> id12((12))
	id7 --> id3
	id11 --> id8
```

##### Task 05

Test Case | x | y | Expected Output
:--: | :-: | : - : | :--:
1 | -1 | -1 | -2
2 | 0 | 0 | 0
3 | 1 | 1 | 2


### Exercise 02

##### Task 01

```mermaid
flowchart LR
	id1((1)) --> id3((3)) ---> id7((7)) --> id13((13))
	id3 --> id5((5))
	id7 ---> id9((9)) ---> id10((10)) --> id11((11))
	id13 --> id15((15)) ---> id16((16)) --> id17((17))
	id10 --> id1
	id16 --> id1
```
