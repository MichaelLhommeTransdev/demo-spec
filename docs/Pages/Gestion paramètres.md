Cette page permet à un **administrateur** de gérer les paramètres

!!! warning
		Contrainte de routage `HasRole('CRC_Admin')`

![Pasted image 20230125095726](../medias/Pasted%20image%2020230125095726.png)

![Pasted image 20230125095735](../medias/Pasted%20image%2020230125095735.png)

## Implémentation

Simple page qui affiche un tableau avec les valeurs des différents paramètres. Pas d'ajout ni de suppression à prévoir. Un bouton par ligne permet d'ouvrir un [formulaire dialogue](/Composants/SettingFormDialog) pour éditer l'unité et la valeur uniquement.

### Services
- [SettingsStore](/Store/SettingsStore)

### Angular
- [Button](https://material.angular.io/components/button)
- [Table](https://material.angular.io/components/table/overview)