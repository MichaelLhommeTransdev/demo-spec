## MCD

![Pasted image 20230203155254](../medias/Pasted%20image%2020230203155254.png)

## TS

```ts
enum Role {
	CRC_User,
	CRC_Admin,
	CRC_KeyUser,
	CRC_Maintenance,
	CRC_NotifFI,
	CRC_NotifIVM,
	CRC_NotifIPO
}

interface User {
	name: string
	roles: Role[]
	favorites: MenuId[]
	notifMail: boolean
	notifweb: boolean
}
```

## Endpoints

### GET /users/me

- Body : empty
- Response : `User`

### PATCH /users/me

!!! INFO
	Les 3 champs sont optionnels, au moins un requis, plusieurs possible

!!! QUESTION
	#question
	Pour les favoris, envoi de la liste complète à chaque fois ? Sinon endpoint dédié

- Body : 
```json
{
 notifMail: boolean,
 notifWeb: boolean,
 favorites: MenuId[]
}
```
- Response : `User`
