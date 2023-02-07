Cette page permet à un **administrateur** de gérer les notifications

!!! warning
		Contrainte de routage `HasRole('CRC_Admin')`


![Pasted image 20230125095559](../medias/Pasted%20image%2020230125095559.png)
![Pasted image 20230125095048](../medias/Pasted%20image%2020230125095048.png)

## Implémentation

Simple page statique qui regroupe 3 composants liés à la gestion des notifications :

- [un tableau pour la gestion des thèmes](../Composants/Notification/NotificationThemeTable.md)
- [formulaire pour gérer les paramètres liés aux notifications](../Composants/Notification/NotificationSettingsForm.md)
- [un tableau pour la gestion des notifications](../Composants/Notification/NotificationTable.md)