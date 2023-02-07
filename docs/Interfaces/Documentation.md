Détails des interfaces pour les fonctionnalités liées à la documentation. Les traitements associés sont gérés par le [store documentation](../Store/DocumentationStore.md) et le [service documentation](../Services/DocumentationSVC.md).

- DocumentationTheme : permet de regrouper plusieurs documentation
- Documentation : une documentation

## Types de base

```ts
type DocumentationID = number
type DocumentationThemeID = string
```

## Interface **DocumentationTheme**

### Typescript

```ts
interface DocumentationTheme {
	id: DocumentationThemeID
	name: string
	shortName: string
	itemsCount: number
}
```

!!! info
		`itemsCount` n'apparait pas explicitement dans la spécification fonctionnelle d'origine mais est nécessaire pour empêcher la suppression d'un thème lorsque celui-ci est utilisé par des documentations.

### Contraintes

- id : strlen <= 3
- name: strlen <= 100
- shortName: strlen <= 30

## Interface **Documentation**

### Typescript

```ts
interface Documentation {
	id: DocumentationID
	theme: string
	name: string
	shortName: string
	version: string
	archived: boolean
	adminRequired: boolean
	creationDate: Date
}
```

### Contraintes

- name: strlen <= 100
- shortName: strlen <= 30
- version: strlen <= 10

## MCD d'origine

![Pasted image 20230203150720](../medias/Pasted%20image%2020230203150720.png)

