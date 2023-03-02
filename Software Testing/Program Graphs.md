## What

Graphs have vertices(V) and edges(E).

Vertices are connected using directional arrows which represent edges.

Vertices (V) and Edges (E) are considered as individual sets and the graph as a pair set of (V,E).

All the graphs considered in this module are finite (meaning they all end). Not sure if there are inifinite graphs.

Program graphs are just graphs that represent the control flow of a program.

Each ==simple program statement is considered a vertex/node== (numbers) and the connection or ==flow from one statement to another is represented using edges==(arrows).

## Why

==Any program flow can be represented using a graph==. 

It will help us ==visualise the program== and its flow. 

It can also help us ==find any infeasible paths== in the program that no input can reach.

## How

**Consider a simple program:**

```Java
public int foo(int x, int y)
{
	for (int i=0; i<y; i++)
	{
		x = bar(x);
	}
	if (x == y)
	{
		y = x + y;
		return baz(x, y, y);
	}
	else if (x > y)
	{
		x = x - y;
		return baz(y, x, x);
	}
	else
	{
		return 23;
	}
}
```

**The program graph for the above program:**

```mermaid
flowchart LR
	id1((1)) --> id3((3)) --> id5((5)) --> id4((4))
	id3 --> id7((7)) --> id9((9)) --> id10((10))
	id4 --> id3
	id7 --> id12((12)) --> id14((14)) --> id15((15))
	id12 --> id17((17)) --> id19((19))
```
The ==parantheses== / opening and closing brackets are ==not considered== as part of the graph. 

The r==eturn statement is usually the end== of the graph unless the graph has a recursive statement.

Loops are represented by adding an arrow back to the statement where the loop started from.

In a `for loop`, the arrow is added back from the loop exit condition, in the example above, loop exit condition would be `i < y`, so an arrow is added back from there to the beginning of the loop. In the example, the exit condition is considered as statement 4.

For a `while loop`, this is how it would be like:

```Java
while(guardCondition)
{
	doSomething();
}
```

Program graph for the above `while loop`:

```mermaid
flowchart LR
	id1((1)) --> id3((3)) --> id1
```
---

Branch points like `if-else`, `switch case` statements can lead to multiple edges from a single vertex.

#### Outdegree of a graph

**Formal definition**: The outdegree of a node v is number of nodes w such that there exists an edge (v,w) in the graph.

Meaning, if there are three nodes that can be reached from a node, then outdegree of that node is 3. 

Example, if nodes 5, 7, 9 can be reached from 4, then outdegree for vertex 4 is 3.

#### Indegree of a graph

**Formal definition**: The indegree of a node v is the number of nodes w such that there exists an edge (w,v) in the graph.

It's the same as outdegree but for incoming edges from multiple nodes to a certain node. 

Example, if nodes 5, 7, 9 all point to same node, 11, then the indegree of vertex 11 is 3.

---

#### Chains (Graphs without multiple branches)

Chains are graphs without multiple branches.

The starting node has an indegree of 1 or less than and outdegree of exactly 1.
The ending node has an indegree of exactly 1 and outdegree of 1 or less than 1.

**Example of chains:**
```mermaid
flowchart LR
	id1((1))
```
```mermaid
flowchart LR
	id1((1)) --> id2((2))
```
```mermaid
flowchart LR
	id1((1)) --> id1
```
```mermaid
flowchart LR
	id1((1)) --> id2((2)) --> id3((3)) --> id4((4))
```
```mermaid
flowchart LR
	id1((1)) --> id2((2)) --> id3((3)) --> id4((4)) --> id1
```

---

#### D-D Graphs

Chains, branch points and nodes with indegree greater than 1 induce partitions of vertices in the graph, meaning, some vertices could be straigt forward pointing from one to another, some could have loops, multiple branches, etc.

The D-D (Decision to Decision) graph is obtained by collapsing each maximal chain to a single node. 

**For example a chain like this:**

```mermaid
flowchart LR
	id1((1)) --> id2((2)) --> id3((3)) --> id4((4))
```
can be collapsed to 
```mermaid
flowchart LR
	id1((1,2,3,4))
```
