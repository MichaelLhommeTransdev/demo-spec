Détail de l'interface `User` utilisée pour représenter l'utilisateur actuellement connecté. Les traitements associés sont gérés par le [store utilisateur](../Store/UserStore.md) et le [service utilisateur](../Services/UserSVC.md)
## TypeScript

```ts
enum Role {
	CRC_User = "CRC_User",
	CRC_Admin = "CRC_Admin",
	CRC_KeyUser = "CRC_KeyUser",
	CRC_Maintenance = "CRC_Maintenance",
	CRC_NotifFI = "CRC_NotifFI",
	CRC_NotifIVM = "CRC_NotifIVM",
	CRC_NotifIPO = "CRC_NotifIPO"
}

interface User {
	name: string
	roles: Role[]
	favorites: MenuID[]
	notifMail: boolean
	notifweb: boolean
}
```

## MCD d'origine

![Pasted image 20230203155254](../medias/Pasted%20image%2020230203155254.png)
