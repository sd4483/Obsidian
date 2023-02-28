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
	SWT[Software Testing] --> WBT[White Box Testing \n (Code)]

		SWT[Software Testing] --> S[Specification]
	end
	
	
	TS --> TC1[Test Case #1] & TC2[Test Case #2] & TC3[Test Case #3]
```
