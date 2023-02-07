![Pasted image 20230125095850](../medias/Pasted%20image%2020230125095850.png)

![Pasted image 20230125095855](../medias/Pasted%20image%2020230125095855.png)

## Implémentation

Récupération des données au chargement de la page (**onNgInit**)
Affichage sous forme de tableau avec possibilité de sélectionner les lignes
Selection et suppression multiple

#Question 
Formulaire avec inputs inline ou modal pour ajout de nouveau menus racines

### Validation
- Code : maxLen = 50
- Short name: maxLen = 50

### Stores
- [MenuStore](../Store/MenuStore.md)
	- listRoots

### Services
- [MenuSVC](../Services/MenuSVC.md)
	- addRoot(code, name, maxLevel)
	- deleteRoot(ids[])

### Material
- [Table](https://material.angular.io/components/table/overview)