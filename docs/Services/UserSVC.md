Service responsable des échanges avec le backend pour les [informations utilisateurs](../Interfaces/User.md)


## `getCurrentUser(): Observable<User>`

Récupère les informations de l'utilisateur connecté

Endpoint: `GET /users/me`

- Body : empty
- Response : `User`

## `updateNotificationSettings(webNotif: boolean, mailNotif: boolean): Observable<User>`

Met à jour les préférences utilisateurs

Endpoint: `PATCH /users/me`

- Body : 
```json
{
 notifMail: boolean,
 notifWeb: boolean
}
```
- Response : `User`


## `addFavorite(menu: MenuID): Observable<User>`

Ajoute un nouveau favoris

Endpoint: `POST /users/me/favorite`

- Body : simple integer as JSON
- Response : `User`

## `removeFavorite(menu: MenuID): Observable<User>`

Supprime un favoris

Endpoint: `DELETE /users/me/favorite/:id`

- Path param : `:id` as integer
- Body : empty
- Response : `User`

!!! warning
    L'ID passé au backend correspond à celui du menu, pas celui de la table de jointure

## `searchUsers(filter: string): Observable<string[]>`

Effectue une recherche d'utilisateur pour récupérer leurs noms.

Endpoint: `GET /users?filter=:filter`

- Path param : `:filter` as string
- Body : empty
- Response : `string[]`