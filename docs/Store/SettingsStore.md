Store utilisé par les composants d'interface pour interragir avec les [objets de paramétrage](../Interfaces/Setting.md). Il permet de garder en mémoire les données, et fait suivre les appels au [service SettingsSVC](../Services/SettingsSVC.md).

## `settings: Observable<Setting[]>`

Liste des paramètres

## `select(code: SettingID): Observable<Setting>`

Sélectionne un paramètre à partir de son ID

## `update(code: SettingID, setting: Setting): Observable<Setting>`

Mise à jour d'un paramètre

## `updateAll(settings: Settings[]): Observable<Setting[]>`

Met à jour plusieurs paramètres d'un coup