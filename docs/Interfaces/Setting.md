
Prévoir conversion d'un champ unique typé Union vers de multiple champs typés scalaires (côté back ou côté front ?)

## MCD

![Pasted image 20230125143312](../medias/Pasted%20image%2020230125143312.png)

## TS

```ts
enum SettingType {
	VARCHAR,
	INT,
	BOOLEAN
}

interface Setting {
	code: string
	name: string
	type: string
	unit: string
	value: Date | DateTime | string | number | boolean
}
```

!!! QUESTION
	#question
	La table prévoit des champs date, mais non utilisé ?

## Contraintes
- code : strlen <= 50
- name : strlen <= 100
- type : strlen <= 100
- value : validate format depending on type

## Endpoints

### GET /parameters

- Body : empty
- Response : `Setting[]`

### GET /parameters/:code

- Path param : `:code` as String
- Body : empty
- Response : `Setting`

### PATCH /parameters/:code

- Body : 
```json
{
	type: string,
	unit: string,
	value: Date | DateTime | string | number | boolean
}
```
- Response : `Setting`