![Pasted image 20230125095813](../medias/Pasted%20image%2020230125095813.png)

![Pasted image 20230125095819](../medias/Pasted%20image%2020230125095819.png)

## Implémentation

Récupérer les informations de l'utilisateur au chargement de la page (**onNgInit**)
Affichage des roles sous forme de tableau (ou de [Chips](https://material.angular.io/components/chips) #Question ?)
Affichage des toggles
Bouton sauvegarder ou sauvegarde instantanée #Question

### Stores
- [UserStore](../Store/UserStore.md)
	- userRoles
	- notificationPrefs

### Services
- [UserSVC](../Services/UserSVC.md)
	- setNotificationPrefs

### Material
- [Button](https://material.angular.io/components/button/overview)
- [Slide toggle](https://material.angular.io/components/slide-toggle/overview)
- [List](https://material.angular.io/components/list/overview)