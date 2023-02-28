```mermaid
flowchart TD
	software[How software is developed]-->req[Requirements Gathering]
	req --> spec[Specifications] --> impl[Implementation]
	impl --> verif[Verification]
	verif ---> val[Validation]
```
