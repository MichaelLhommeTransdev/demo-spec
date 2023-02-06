Cette page permet aux utilisateurs d'accéder aux documentations. 

![Pasted image 20230125095656](../medias/Pasted%20image%2020230125095656.png)

![Pasted image 20230125095702](../medias/Pasted%20image%2020230125095702.png)

## Implémentation

Utilise le store de documentation pour afficher un tableau, chaque ligne contenant les informations ainsi qu'un lien pour télécharger le fichier joint.

Le tableau doit supporter la sélection de plusieurs lignes pour proposer un téléchargement multiple à l'utilisateur.

### Utilisation des services
- [DocumentationStore](../Store/DocumentationStore.md)
	- themes
	- documentations
	
- [DocumentationSVC](../Services/DocumentationSVC.md)
	- download(id)
	- downloadAll(ids[])

### Material
- [Table](https://material.angular.io/components/table/overview)