![Pasted image 20230125093431](../medias/Pasted%20image%2020230125093431.png)

## Estimation

Durée : 1j
Risque : 0

## Implémentation

Création d'un arbre à partir des données du store, affichage du bouton favoris depuis le store utilisateur

#Question 
Besoin d'un arbre (intérêt -> collapsable) ou simple liste avec padding (intérêt -> visualisation seulement)

### Stores
- [MenuStore](../Store/MenuStore.md)
	- listMenus
 - [UserStore](../Store/UserStore.md)
	 - favorites

### Services
- [UserSVC](../Services/UserSVC.md)
	- addFavorite

### Material
- [Tree](https://material.angular.io/components/tree/overview)
- [Button](https://material.angular.io/components/button/overview)