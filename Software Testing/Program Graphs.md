## What
Graphs have vertices(V) and edges(E).

Vertices are connected using directional arrows which represent edges.

Vertices (V) and Edges (E) can be thought of as individual sets and the graph as a pair set of (V,E).

All the graphs considered in this module are finite (meaning they all end). Not sure if there are inifinite graphs.

Program graphs are just graphs that represent the control flow of a program.

Each simple program statement is considered a vertex/node (numbers) and the connection or flow from one statement to another is represented using edges(arrows).

## Why

Any program flow can be represented using a graph. It will help us visualise the program and its flow. It can also help us find any infeasible paths in the program that no input can reach.

## How

Consider a simple program:

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
		return 
	}
}
```
