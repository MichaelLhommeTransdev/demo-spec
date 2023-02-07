Store utilisé par les composants d'interface pour interragir avec les [objects de notifications](../Interfaces/Notification.md). Il permet de garder en mémoire les données, et fait suivre les appels au [service NotificationsSVC](../Services/NotificationsSVC.md).

!!! warning
    Les NotificationTemplate ne nécessitant pas de persistance dans l'interface utilisateur, elles ne sont pas gérées par ce store.

## NotificationTheme

### `themes: Observable<NotificationTheme[]>`

Liste des thèmes

### `createTheme(theme: NotificationTheme): Observable<NotificationTheme>`

Crée un nouveau thème

### `updateTheme(id: NotificationThemeID, theme: NotificationTheme): Observable<NotificationTheme>`

Met à jour un thème

### `deleteTheme(id: NotificationThemeID): Observable<void>`

Supprime un thème

## Notification

### `notifications: Observable<Notification[]>`

Liste des notifications destinée à l'utilisateur connecté

### `markRead(id: NotificationID): Observable<void>`

Marquer une notification comme lue

### `markLiked(id: NotificationID): Observable<void>`

Marquer une notification comme *liked*

### `markDisliked(id: NotificationID): Observable<void>`

Marquer une notification comme *disliked*

### `markDeleted(id: NotificationID): Observable<void>`

Marquer une notification comme supprimée