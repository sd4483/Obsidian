```mermaid
flowchart TB
	subgraph How software is developed
		direction TB
	req[Requirements \n Gathering] --> spec[Specifications] --> impl[Implementation] --> verif[Verification]
	subgraph Software Testing
	verif --> val[Validation]
	end
	end
	
```
