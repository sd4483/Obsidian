```mermaid
mermaid.flowchartConfig = { width: 100% }
flowchart TB
	software[How software is developed]-->req[Requirements Gathering]
	req --> spec[Specifications] --> impl[Implementation]
	impl --> verif[Verification]
	subgraph Software Testing
	verif --> val[Validation]
	end
	
```
