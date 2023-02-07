Cette page permet à un **administrateur** de contrôler le mode maintenance de l'application.

!!! warning
		Contrainte de routage `HasRole('CRC_Admin')`

![Pasted image 20230125094712](../medias/Pasted%20image%2020230125094712.png)

## Implémentation

Simple formulaire qui permet de contrôler plusieurs paramètres liés au mode maintenance. Les champs de configuration doivent être validés en un bloc.

L'activation / désactivation du mode maintenance fait appel à un contrôle séparé des autres.

### Services
- [UserSVC](../Services/UserSVC.md)
	- searchUsers(filter)
- [SettingsStore](../Store/SettingsStore.md.md)
	- setMaintenance(params)

### Material
- [Slide toggle](https://material.angular.io/components/slide-toggle)
- [Button](https://material.angular.io/components/button)
- [Checkbox](https://material.angular.io/components/checkbox)
- [Input](https://material.angular.io/components/input)
- [List](https://material.angular.io/components/list)