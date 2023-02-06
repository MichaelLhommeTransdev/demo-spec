## MCD

![Pasted image 20230125145622](../medias/Pasted%20image%2020230125145622.png)

## TS

!!! WARNING
	#warning 
	Certains champs nécessaire à PBI ne sont pas encore listés dans l'interface Menu

```ts
enum MenuType {

}

type RootMenuId = string

interface RootMenu {
	name: RootMenuId
	shortName: string
	maxLevel: number
}

type MenuId = number

interface Menu {
	id: MenuId
	root: RootMenuId
	level: number
	parent: MenuId
	previousSibling: MenuId
}
```

## Contraintes

### RootMenu
- name : strlen <= 50
- shortName : strlen <= 50

### Menu
- name : strlen <= 100
- shortName : strlen <= 30
- type : strlen <= 3
- version : strlen <= 10

## Endpoints

### RootMenu

!!! QUESTION
	#Question 
	Nécessité de créer & supprimer les root menu ?

#### GET /rootMenus

- Body : empty
- Response : `RootMenu[]`

#### POST /rootMenus

- Body : `RootMenu`
- Response : `RootMenu`

#### PUT /rootMenus

- Body : `RootMenu`
- Response : `RootMenu`

#### DELETE /rootMenus/:name

- Path param : `:name` as String
- Body : empty
- Response : `RootMenu`

### Menu
