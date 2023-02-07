Service responsable des échanges avec le backend pour les entités [Setting](../Interfaces/Setting.md)

### `list(): Observable<Setting[]>`

Liste les paramètres

Endpoint: `GET /parameters`

- Body : empty
- Response : `Setting[]`

### `get(code: SettingID): Observable<Setting>`

Récupère un paramètre

Endpoint: `GET /parameters/:code`

- Path param : `:code` as String
- Body : empty
- Response : `Setting[]`

### `update(code: SettingID, setting: Setting): Observable<Setting>`

Met à jour un paramètre

Endpoint: `PATCH /parameters/:code`

- Body : JSON
```json
{
	type: string,
	unit: string,
	value: string | number | boolean | Date
}
```
- Response : `Setting`

### `updateAll(settings: Setting[]): Observable<Setting[]>`

Met à jour plusieurs paramètres d'un coup

Endpoint: `PATCH /parameters`

- Body : JSON
```json
[
	{
		type: string,
		unit: string,
		value: string | number | boolean | Date
	}
]
```

- Response : `Setting[]`