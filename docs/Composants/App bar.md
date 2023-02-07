![Pasted image 20230125093144](../medias/Pasted%20image%2020230125093144.png)

## Implémentation

Utilisation du **store user** pour affichage du nom de l'utilisateur.

Utilisation du **store notification** pour affichage du nombre de notifications non lues avec un **badge** sur le bouton.

Ouverture de la liste des notifications a l'aide d'un **dialog**.

### Composants
- [Notifications popup](/Composants/Notification/NotificationsPopup)

### Stores
- [NotificationsStore](../Store/NotificationsStore.md)
	- unread count
- [UserStore](../Store/UserStore.md)
	- user name

### Material
- [Button](https://material.angular.io/components/button/overview)
- [Badge](https://material.angular.io/components/badge/overview)
- [Dialog](https://material.angular.io/components/dialog/overview)