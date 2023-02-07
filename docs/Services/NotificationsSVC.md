Service responsable des échanges avec le backend pour les entités de [Notifications](../Interfaces/Notification.md).


## NotificationTheme

### `listThemes(): Observable<NotificationTheme[]>`

Liste des thèmes

Endpoint: `GET /notificationThemes`

- Body : empty
- Response : `NotificationTheme[]`


### `createTheme(theme: NotificationTheme): Observable<NotificationTheme>`

Crée un nouveau thème

Endpoint: `POST /notificationThemes`

- Body : `NotificationTheme`
- Response : `NotificationTheme`

### `updateTheme(id: NotificationThemeID, theme: NotificationTheme): Observable<NotificationTheme>`

Met à jour un thème

Endpoint: `PUT /notificationThemes/:id`

- Path param: `:id` as String
- Body : `NotificationTheme`
* Response : `NotificationTheme`

### `deleteTheme(id: NotificationThemeID): Observable<void>`

Supprime un thème

Endpoint: `DELETE /notificationThemes/:id`

- Path param: `:id` as String
- Body : empty
- Response : empty


## Notification

### `list(): Observable<Notification[]>`

Liste les notifications relatives à l'utilisateur connecté

!!! warning
    Filtrage implicite en fonction de l'utilisateur connecté
    
Endpoint: `GET /notifications`

- Body : empty
- Response : `Notification[]`

### `update(partialJson): Observable<Notification>`

Permet de mettre à jour les informations de la notification

Endpoint: `PATCH /notifications/:id`

- Path param: `:id` as Integer
- Body: JSON
```
{
  read?: boolean
  liked?: boolean
  disliked?: boolean
  deleted?: boolean
}
```
- Response: `Notification`

### `download(id: NotificationID): Observable<void>`

Démarre le téléchargement des fichiers joints

!!! INFO
	Ce point d'entrée renvoi un fichier ZIP contenant plusieurs documents
	
	```
	Content-Type: application/octet-stream
	Content-Disposition: attachment
	```


Endpoint: `GET /notifications/:id/attachment`

- Path param: `:id` as String
- Body : empty
- Response : binary data 


## NotificationTemplate

### `listTemplates(): Observable<NotificationTemplate[]>`

Liste les templates de notifications

Endpoint: `GET /notificationTemplates`

- Body: empty
- Response : `NotificationTemplate[]`


### `createTemplate(template: NotificationTemplate): Observable<NotificationTemplate>`

Crée un template de notification

Endpoint: `POST /notificationTemplates`

- Body: `NotificationTemplate`
- Response: `NotificationTemplate`


### `updateTemplate(id: NotificationTemplateID, template: NotificationTemplate): Observable<NotificationTemplate>`

Met à jour un template de notification

Endpoint: `PUT /notificationTemplates/:id`

- Path param: `:id` as Integer
- Body: `NotificationTemplate`
- Response: `NotificationTemplate`


### `archiveTemplates(ids: NotificationTemplateID[]): Observable<number[]>`

Archiver plusieurs templates de notification

Endpoint: `POST /notificationTemplates/archive`

- Body: `NotificationTemplateID[]` as JSON
- Response: `NotificationTemplateID[]`


### `deleteTemplates(ids: NotificationTemplateID[]): Observable<number[]>`

Supprime plusieurs templates de notification

Endpoint: `DELETE /notificationTemplates`

- Body: `NotificationTemplateID[]` as JSON
- Response: `NotificationTemplateID[]`
