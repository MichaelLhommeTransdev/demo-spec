Détails des interfaces pour les fonctionnalités liées aux notifications. Les traitements associés sont gérés par le [store menu](/Store/MenuStore) et le [service menu](/Services/MenuSVC).

## Types de base

```ts
type RootMenuId = string
type MenuId = number
```

## Interface **RootMenu**

### TypeScript

```ts
interface RootMenu {
	name: RootMenuId
	shortName: string
	maxLevel: number
	treeStructure: string // JSON content
}
```

### Contraintes

- name : strlen <= 50
- shortName : strlen <= 50


## Interface **Menu**

### Typescript

```ts
interface Menu {
	id: MenuId
	root: RootMenuId
	name: string
	shortName: string
	version: string
	adminsRestricted: boolean
	keyUsersRestricted: boolean
	pbiID: string
	pbiURL: string
	pbiWorkspace: string
}
```

### Contraintes

- name : strlen <= 100
- shortName : strlen <= 30
- type : strlen <= 3
- version : strlen <= 10

## MCD d'origine

![Pasted image 20230125145622](../medias/Pasted%20image%2020230125145622.png)
