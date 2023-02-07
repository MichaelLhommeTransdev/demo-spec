Interface dédiée au paramétrage de l'application. Les traitements associés sont gérés par le [store Settings](../Store/SettingsStore.md) et le [service Setting](../Services/SettingsSVC.md).

## Typescript

```ts
type SettingID = string

enum SettingType {
	VARCHAR = "Varchar",
	INT = "INT",
	BOOLEAN = "Boolean"
}

interface Setting {
	code: SettingID
	name: string
	type: SettingType
	unit: string
	value: string | number | boolean | Date
}
```

## Contraintes
- code : strlen <= 50
- name : strlen <= 100
- type : strlen <= 100
- value : format à valider en fonction du type associé

## MCD d'origine

![Pasted image 20230125143312](../medias/Pasted%20image%2020230125143312.png)