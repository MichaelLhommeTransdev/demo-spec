
## MCD

![Pasted image 20230125144840](../medias/Pasted%20image%2020230125144840.png)

## TS

```ts
interface Notification {
	id: number
	sGravite: string
	sTheme: string
	sTitre: string
	sMessage: string
	bEnvoiDesQuePossible: boolean
	dtimeDateEnvoi: Datetime
	sStatut: string
	bAnnuler: boolean
	bRestreindreAuxAdmin: boolean
	bRestreindreAuxKeyUsers: boolean
	iNb_PJ: number
	dtimeCreation: Datetime
	sParCreation: string
	dtimeLastModif: Datetime
	sParLastModification: string
	iNbEnvoyees: number
	iNbJAIME: number
	iNbJAIMEPAS: number
	iNbLUES: number
	iNbSuppr: number
	bArchivee: boolean
	dtArchivee: Datetime
}
```