Un tableau permettant l'affichage et la suppression des notifications.

![](/medias/notification_admin_table.png)

## Implémentation

L'édition est accessible via un bouton présent sur chaque ligne, et la création de nouvelles notifications via un bouton général. Ces deux actions ouvrent un [dialogue formulaire](./NotificationFormDialog.md).

Le tableau doit supporter la sélection multiple pour permettre d'appliquer les actions **archiver** et **supprimer** en masse.

!!! warning
    La suppression ne doit être possible que si la notification est archivée

## Utilisation des services

- [NotificationStore](/Store/NotificationsStore)