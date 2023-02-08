Service responsable des échanges avec le backend pour les entités [Menu](../../Interfaces/Menu).


## RootMenu

### `listRoots(): Observable<RootMenu[]>`

Liste des menus racines

Endpoint: `GET /rootMenus`

- Body : empty
- Response : `RootMenu[]`


### `createRoot(theme: RootMenu): Observable<RootMenu>`

Crée un nouveau menu racine

Endpoint: `POST /rootMenus`

- Body : `RootMenu`
- Response : `RootMenu`

### `updateRoot(id: RootMenuID, theme: RootMenu): Observable<RootMenu>`

Met à jour un menu racine

Endpoint: `PUT /rootMenus/:id`

- Path param: `:id` as String
- Body : `RootMenu`
* Response : `RootMenu`

### `deleteRoot(id: RootMenuID): Observable<void>`

Supprime un menu racine

Endpoint: `DELETE /rootMenus/:id`

- Path param: `:id` as String
- Body : empty
- Response : empty


## Menu

### `list(): Observable<Menu[]>`

Liste des menus

Endpoint: `GET /menus`

- Body : empty
- Response : `Menu[]`


### `create(theme: Menu): Observable<Menu>`

Crée un nouveau menu

Endpoint: `POST /menus`

- Body : `Menu`
- Response : `Menu`

### `update(id: MenuID, theme: Menu): Observable<Menu>`

Met à jour un menu

Endpoint: `PUT /menus/:id`

- Path param: `:id` as String
- Body : `Menu`
* Response : `Menu`

### `delete(id: MenuID): Observable<void>`

Supprime un menu

Endpoint: `DELETE /menus/:id`

- Path param: `:id` as String
- Body : empty
- Response : empty
