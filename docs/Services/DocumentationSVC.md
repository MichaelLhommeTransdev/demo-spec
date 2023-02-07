Service responsable des échanges avec le backend pour les entités [Documentation](../Interfaces/Documentation.md#documentation) et  [DocumentationTheme](../Interfaces/Documentation.md#documentationtheme).


## DocumentationTheme

### `listThemes(): Observable<DocumentationTheme[]>`

Liste des thèmes

Endpoint: `GET /documentationThemes`

- Body : empty
- Response : `DocumentationTheme[]`


### `createTheme(theme: DocumentationTheme): Observable<DocumentationTheme>`

Crée un nouveau thème

Endpoint: `POST /documentationThemes`

- Body : `DocumentationTheme`
- Response : `DocumentationTheme`

### `updateTheme(id: DocumentationThemeID, theme: DocumentationTheme): Observable<DocumentationTheme>`

Met à jour un thème

Endpoint: `PUT /documentationThemes/:id`

- Path param: `:id` as String
- Body : `DocumentationTheme`
* Response : `DocumentationTheme`

### `deleteTheme(id: DocumentationThemeID): Observable<void>`

Supprime un thème

Endpoint: `DELETE /documentationThemes/:id`

- Path param: `:id` as String
- Body : empty
- Response : empty

## Documentation

### `list(): Observable<Documentation[]>`

Liste les documentations **accessibles par l'utilisateur**

!!! warning
	Filtrage implicite en fonction du rôle utilisateur : les documents réservés aux admins ne seront retournés que pour un administrateur

Endpoint: `GET /documentations`

- Body : empty
- Response : `Documentation[]`

	
### `create(doc: Documentation, file: File): Observable<Documentation>`

Crée une nouvelle documentation avec un fichier joint

!!! INFO
	Ce point d'entrée utilise un format `multipart/form-data` avec deux champs : 
	
	- `file` pour le blob
	- `json` pour les données

Endpoint: `POST /documentations`

- Body : Multipart content
- Response : `Documentation`


### `update(id: DocumentationID: doc: Documentation, file?: File): Observable<Documentation>`

Met à jour une documentation, avec mise à jour optionnelle du fichier joint

!!! INFO
	Ce point d'entrée utilise un format `multipart/form-data` avec deux champs : 
	
	- `file` pour le blob
	- `json` pour les données
	
	[Configuration Spring](https://www.intelliware.com/submitting-a-multipart-request-multipartform-data-using-put-and-spring-boot/) pour `multipart/form-data` avec méthode `PUT`

Endpoint: `PUT /documentations/:id`

- Path param: `:id` as String
- Body : Multipart content
- Response : `Documentation`



### `download(id: DocumentationID): Observable<void>`

Démarre le téléchargement du fichier associé

!!! INFO
	Ce point d'entrée renvoi un fichier, le navigateur peut éventuellement l'afficher directement (cas des PDF) si le serveur utilise les headers suivants :
	
	```
	Content-Type: application/pdf
	Content-Disposition: inline; filename="filename.pdf"
	```

Endpoint: `GET /documentations/:id/attachment`

- Path param: `:id` as String
- Body : empty
- Response : binary data 


### `downloadAll(ids: DocumentationID[]): Observable<void>`

Démarre le téléchargement de plusieurs fichiers associés

!!! INFO
	Ce point d'entrée renvoi un fichier ZIP contenant plusieurs documents
	
	```
	Content-Type: application/octet-stream
	Content-Disposition: attachment
	```

Endpoint: `GET /documentations/attachments`

- Body: `DocumentationID[]` as JSON
- Response : binary data 

### `archive(ids: DocumentationID[]): Observable<void>`

Archive plusieurs documentations 

Endpoint: `POST /documentations/archive`

- Body : `DocumentationID[]` as JSON
- Response : `DocumentationID[]`


### `delete(ids: DocumentationID[]): Observable<void>`

Supprime plusieurs documentation d'un coup

Endpoint: `DELETE /documentations`

- Body : `DocumentationID[]` as JSON
- Response : `DocumentationID[]`