Store utilisé par les composants d'interface pour interragir avec [les données utilisateurs](../Interfaces/User.md)

## `user: Observable<User>`

Référence à l'utilisateur connecté

## `updateNotificationSettings(webNotif: boolean, mailNotif: boolean): Observable<User>`

Mise à jour des préférences de notifications

## `addFavorite(menuId: MenuID): Observable<void>`

Ajout d'un nouveau favoris

## `removeFavorite(menuId: MenuID): Observable<void>`

Suppression d'un favoris