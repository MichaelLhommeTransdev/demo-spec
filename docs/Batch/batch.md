# Mise en place des batch

## Paramétrage des batch

Les batch d'archivage et de suppression tourneront tous les jours à heure fixe.
L'heure d'activation de chacun des batch sera définie dans un fichier de propriétés externalisé

Chacun des batch aura aussi un paramétrage en table CRC_PARAM afin de savoir s'il doit tourner, et si c'est le cas permettre d'identifier la durée de rétention des données


## Batchs liés aux notifications
### Batch d'archivage des notifications
Le batch devra tout d'abord aller chercher les paramètres `bNotifAdmArchivageAuto` et `iNotifAdmArchivageJours` en table `CRC_PARAM`
Si la valeur du paramètre `bNotifAdmArchivageAuto` est à `false`, l'exécution s'arrête
Sinon, on exécute la requête qui va permettre d'archiver les notifications selon leur date de création

```sql
update CRC_NOTIF_ADMIN set archivee = ‘true’, Dtarchivee=CURRENT_DATE where convert(date, dateadd( day, iNotifAdmArchivageJours, DtimeCreation)) < CURRENT_DATE;
```


### Batch de suppression des notifications archivées
Le batch devra tout d'abord aller chercher les paramètres `bNotifAdmSupprAuto` et `iNotifAdmSupprJours` en table `CRC_PARAM`
Si la valeur du paramètre `bNotifAdmSupprAuto` est à `false`, l'exécution s'arrête
Sinon, on exécute les requêtes qui vont permettre de supprimer les notifications selon leur date d'archivage

```sql
Delete from CRC_NOTIF_ADMIN_USER where NOTIF_ADMIN_Id in (select NOTIF_ADMIN_Id from CRC_NOTIF_ADMIN WHERE dateadd(day, iNotifAdmSupprJours, Dtarchivee) < CURRENT_DATE);

Delete from CRC_NOTIF_ADMIN WHERE dateadd(day, iNotifAdmSupprJours, Dtarchivee) < CURRENT_DATE;
```

## Batch d'émission des notifications
Ce batch tournera toutes les n secondes / minutes (n à définir) afin de vérifier s'il y a des notifications à émettre
Il devra dans un premier temps vérifier s'il y a des notifications à émettre
S'il y en a, il devra créer une notification en base pour chaque utilisateur ciblé, et éventuellement émettre un mail pour les utilisateurs abonnés

- Récupération des notifications à émettre
```sql
Select n.NOTIF_ADMIN_Id, r.ROLE_ID from CRC_NOTIF_ADMIN n, CRC_NOTIF_RESTRIC_ROLE r where n.NOTIF_ADMIN_Id = r.NOTIF_ADMIN_Id AND n.[dtimeDateEnvoiPrevu] < CURRENT_TIMESTAMP AND n.DtimeDateEnvoi is null ;
```
- Récupération des utilisateurs ciblés
```sql
Select u.GUID, bNotif_Mail_Activated, bNotif_Web_Activated from REFLET_USER u, REFLET_USER_ROLE r, CRC_NOTIF_USER_OPTIONS o WHERE r.USER_AD = u.GUID AND u.GUID = o.GUID AND r.ROLE_ID IN ([liste des ROLE_ID récupérés plus haut]);
```
- Pour chaque utilisateur, on va créer la notification associée
  - Si  `bNotif_Mail_Activated` = false ET `bNotif_Web_Activated` = false
```sql
Insert into CRC_NOTIF_ADMIN_USER values (NOTIF_ADMIN_Id, GUID, ‘IGN’, false,false,true,true) ;
```
  - Sinon
```sql
Insert into CRC_NOTIF_ADMIN_USER values (NOTIF_ADMIN_Id, GUID, ‘ENV’, false,false,false,false) ;
```

- Puis envoyer un mail à tous les utilisateurs ayant activé les notifications par mail
  - Objet : [sTheme] - sTitre
  - Message : sMessage
  - Ajouter les pièces jointes de la notif au mail

- Et enfin on met à jour la table `CRC_NOTIF_ADMIN`

```sql
Update CRC_NOTIF_ADMIN set sStatut = ‘ENV’, dtimeDateEnvoi = CURRENT_TIMESTAMP, iNbEnvoyees = (select count(*) from CRC_NOTIF_ADMIN_USER where NOTIF_ADMIN_Id = [idCourant]), iNbLUES = (select count(*) from CRC_NOTIF_ADMIN_USER WHERE NOTIF_ADMIN_Id = [idCourant] AND bLue = true), iNbSuppr = (select count(*) from CRC_NOTIF_ADMIN_USER WHERE NOTIF_ADMIN_Id = [idCourant] AND bSuppr = true) WHERE NOTIF_ADMIN_Id = [idCourant]
```


## Batchs liés à la documentation
### Batch de suppression des documentations archivées
Le batch devra tout d'abord aller chercher les paramètres `bDocAdmSupprArchivageAuto` et `iDocAdmSupprArchivageJours` en table `CRC_PARAM`
Si la valeur du paramètre `bDocAdmSupprArchivageAuto` est à `false`, l'exécution s'arrête
Sinon, on exécute la requête qui va permettre de supprimer les documents selon leur date d'archivage

```sql
Delete from CRC_DOCUMENTATION WHERE bArchivee = true AND dateadd(day, iDocAdmSupprArchivageJours, dtDateArchivage) < CURRENT_DATE;
```

