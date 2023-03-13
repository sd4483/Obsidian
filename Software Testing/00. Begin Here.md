```mermaid
flowchart TB
	subgraph <strong>How software is developed<strong>
		direction LR
		req[Requirements \n Gathering] --> spec[Specifications] --> impl[Implementation] --> verif[Verification]
		subgraph <mark><strong>Software Testing</strong></mark>
		verif --> val[Validation]
		end
	end
	
```

```mermaid
flowchart LR
	SWT[Software Testing]:::swt --> WBT[White Box Testing \n <mark>Code</mark>] & BBT[Black Box Testing \n <mark>Specification</mark>]	
	
	WBT ---> TSW[Test Suite]
	TSW ---> TCW1[Test Case #1] & TCW2[Test Case #2] & TCW3[Test Case #3]
	
	BBT ---> TSB[Test Suite]
	TSB ---> TCB1[Test Case #1] & TCB2[Test Case #2] & TCB3[Test Case #3]
	classDef swt fill:#6495ED
```
