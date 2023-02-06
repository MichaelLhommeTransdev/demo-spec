
```mermaid
sequenceDiagram
	Component ->>+ Store: Subscribe to data
    Store ->> BehaviorSubject: asObservable
    BehaviorSubject -->> Store: 
    Store -->>- Component: Observable data

    Note over Component,Store: Another time

    Component ->>+ Store: CRUD operation
	Store ->>+ Service: CRUD operation
	Service ->>+ Backend: CRUD API call
	Backend -->>- Service: json
	Service -->>- Store: json
    Store ->> BehaviorSubject: Update data
    BehaviorSubject -->> Store: 
    Store -->>- Component: 
    BehaviorSubject ->> Component: Dispatch updated data
```