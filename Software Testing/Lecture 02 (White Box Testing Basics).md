We derive test cases from the code. But for good test cases, both code and specification should be considered

Specification testing: Test cases align with specifcation
	Might fail to cover undesirable behaviours of the programs. Ex: Memory leak

White box testing: Testing code for bugs, testing behaviour
	Disadvantages: Never covers all specified behaviours, refactor -> reqrite test cases, cannot do test-driven development

Applications:
- Usually applied once the code is stable
- Imp for safety critical applications (like airplanes)
- In safety critical contexts, certification like this might be required

Coverage criteria
- Makes the idea of test coverage precise and measurable
- Usually qualitative, but quantitative does exist
- Usually code-based
- In white box testing, select suitable code based coverage criterion and find a test suite with minimal complexity that satisfies criterion
- Designing a good specification based test suite depends on the understanding of the code-based coverage criteria

Program graphs:
- Simple statements are followed immediately by another simple statements
	- They are usually just like 1 -> 2
- If then else is like in a triangle format or like a polygon for multiple branches
- For switch cases, it's like a tree branch
- While loop is like a loop 1 -> 2 -> 1

Path: A path in a graph is a finite or infinite sequence of vertices of graph
- There can be infinite paths with loops like {2,4,2,4,2,4,2,4...}

A node path is feasible if the node is reachable

What sort of inputs are acceptable is dependent on what we want the program to do. Like if we want the program to handle exceptions.

We generally don't consider brackets in the graphs unless there is no return for that program and it's void, then the last bracket will be considered as a node.

Feasible path: Part of a program that's feasible

