Store utilisé par les composants d'interface pour interragir avec les [objects de menus](../../Interfaces/Menu). Il permet de garder en mémoire les données, et fait suivre les appels au [service MenuSVC](../../Services/MenuSVC).

## MenuRoot

### `roots: Observable<MenuRoot[]>`

Liste des menus racines

### `createRoot(root: RootMenu): Observable<RootMenu>`

Crée un nouveau menu racine

### `updateRoot(id: RootMenuID, root: RootMenu): Observable<RootMenu>`

Met à jour un menu racine

### `deleteRoot(id: RootMenuID): Observable<void>`

Supprime un menu racine


## Menu

### `menus: Observable<Menu[]>`

Liste des menus

### `create(menu: Menu): Observable<Menu>`

Crée un nouveau menu

### `update(id: MenuID, root: Menu): Observable<Menu>`

Met à jour un menu

### `delete(id: MenuID): Observable<void>`

Supprime un menu