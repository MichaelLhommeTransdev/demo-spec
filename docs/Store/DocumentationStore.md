Store utilisé par les composants d'interface pour interragir avec les [objects de documentation](../Interfaces/Documentation.md). Il permet de garder en mémoire les données, et fait suivre les appels au [service DocumentationSVC](../Services/DocumentationSVC.md).

## DocumentationTheme

### `themes: Observable<DocumentationTheme[]>`

Liste des thèmes

### `createTheme(theme: DocumentationTheme): Observable<DocumentationTheme>`

Crée un nouveau thème

### `updateTheme(id: DocumentationThemeID, theme: DocumentationTheme): Observable<DocumentationTheme>`

Met à jour un thème

### `deleteTheme(id: DocumentationThemeID): Observable<void>`

Supprime un thème

## Documentation

### `documentations: Observable<Documentation[]>`

Liste des documentations

### `createDoc(doc: Documentation, file: File): Observable<Documentation>`

Crée une nouvelle documentation avec un fichier joint

### `updateDoc(id: DocumentationID, doc: Documentation, file?: File): Observable<Documentation>`

Met à jour une documentation, le champ fichier étant optionnel

### `archiveDoc(id: DocumentationID): Observable<void>`

Archive une documentation

### `archiveAllDoc(ids: DocumentationID[]): Observable<void>`

Archives plusieurs documentations