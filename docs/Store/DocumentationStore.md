Store utilisé par les composants d'interface pour interragir avec les [objects de documentation](../Interfaces/Documentation.md). Il permet de garder en mémoire les données, et fait suivre les appels au [service DocumentationSVC](../Services/DocumentationSVC.md).

## DocumentationTheme

### `listThemes(): Observable<DocumentationTheme[]>`

Liste les thèmes

### `create(theme: DocumentationTheme): Observable<DocumentationTheme>`

Crée un nouveau thème

### `update(id: DocumentationThemeID, theme: DocumentationTheme): Observable<DocumentationTheme>`

Met à jour un thème

### `delete(id: DocumentationThemeID): Observable<void>`

Supprime un thème

## Documentation

### `list(): Observable<Documentation[]>`

Liste les documentations

### `create(doc: Documentation): Observable<Documentation>`

Crée une nouvelle documentation

### `update(id: DocumentationID, doc: Documentation): Observable<Documentation>`

Met à jour une documentation

### `archive(id: DocumentationID): Observable<void>`

Archive une documentation

### `archiveAll(ids: DocumentationID[]): Observable<void>`

Archives plusieurs documentations