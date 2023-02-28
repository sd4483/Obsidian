```mermaid
flowchart TD
	id_software((How software is developed)) --> id_req((Requirements Gathering))
	id_req --> id_spec((Specifications)) --> id_impl((Implementation))
	id_impl --> id_verif((Verification)) --> id_val(())
```