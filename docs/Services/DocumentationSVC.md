Service responsable des échanges avec le backend pour les entités [Documentation](../Interfaces/Documentation.md#documentation) et  [DocumentationTheme](../Interfaces/Documentation.md#documentationtheme).


## Méthodes

### `list(): Documentation[]`

Liste les documentations **accessibles par l'utilisateur**

### `download(id: DocumentationID): void`

Démarre le téléchargement du fichier associé

### `downloadAll(ids: DocumentationID[]): void`

Démarre le téléchargement des fichiers associés

## Endpoints associés


### Documentation Themes

#### GET /documentationThemes

- Body : empty
- Response : `DocumentationTheme[]`

#### POST /documentationThemes

- Body : `DocumentationTheme`
- Response : `DocumentationTheme`

#### GET /documentationThemes/:id

- Path param: `:id` as String
- Response : `DocumentationTheme`

#### PUT /documentationThemes/:id

- Path param: `:id` as String
- Body : `DocumentationTheme`
* Response : `DocumentationTheme`

#### DELETE /documentationThemes/:id

- Path param: `:id` as String
- Response : empty


### Documentations

#### GET /documentations

!!! warning
	Filtrage implicite en fonction du rôle utilisateur : les documents réservés aux admins ne seront retournés que pour un administrateur

- Body : empty
- Response : `Documentation[]`

#### POST /documentations

!!! INFO
	Ce point d'entrée utilise un format `multipart/form-data` avec deux champs : 
	
	- `file` pour le blob
	- `json` pour les données

- Body : Multipart content
- Response : `Documentation`

#### GET /documentations/:id/attachment

!!! INFO
	Ce point d'entrée renvoi un fichier
	
	Pour télécharger :
	```
	Content-Type: application/octet-stream
	Content-Disposition: attachment
	```
	
	Pour ouverture dans le navigateur (PDF) :
	```
	Content-Type: application/pdf
	Content-Disposition: inline; filename="filename.pdf"
	```

!!! WARNING
	Besoin de stocker le nom de fichier ainsi que le content type pour display inline


- Path param: `:id` as String
- Response : binary data 

#### GET /documentations/attachment

!!! INFO
	Ce point d'entrée renvoi un fichier ZIP contenant plusieurs documents
	
	```
	Content-Type: application/octet-stream
	Content-Disposition: attachment
	```

!!! WARNING
	Besoin de stocker le nom de fichier (au moins l'extension) pour générer le zip


- Path param: `:id` as String
- Response : binary data 


#### PUT /documentations/:id

!!! INFO
	Ce point d'entrée utilise un format `multipart/form-data` avec deux champs : 
	
	- `file` pour le blob
	- `json` pour les données

- Path param: `:id` as String
- Body : Multipart content
- Response : `Documentation`

!!! WARNING
	https://www.intelliware.com/submitting-a-multipart-request-multipartform-data-using-put-and-spring-boot/


#### POST /documentations/archive

!!! INFO
	  Permet l'achivage en masse

- Body : `number[]` as json
- Response : `number[]`

#### DELETE /documentations

!!! INFO
    Permet la suppression en masse. Remplace le endpoint de suppression classique

- Body : `number[]` as json
- Response : `number[]`

## CRUD admin
- add
- update
- delete
- addTheme
- updateTheme
- deleteTheme


## Actions utilisateurs

- listDocs()
- downloadDoc(id)
- downloadDocs(ids[])
