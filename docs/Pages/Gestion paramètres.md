![Pasted image 20230125095726](../medias/Pasted%20image%2020230125095726.png)

![Pasted image 20230125095735](../medias/Pasted%20image%2020230125095735.png)

## Implémentation

Récupération des settings dans un état local lors du chargement de la page (**onNgInit**)
Affichage des données sous forme de tableau

#Question 
Input inline ou modal ou expandable row pour éditer les valeurs ?

### Validation
- Unité : maxLen = 100
- Valeur : cohérente par rapport au type

### Services
- [SettingsSVC](../Services/SettingsSVC.md)
	- listSettings
	- updateSettingValue(value, unit)

### Angular
- [Button](https://material.angular.io/components/button)
- [Select](https://material.angular.io/components/select)
- [Checkbox](https://material.angular.io/components/checkbox)
- [Table](https://material.angular.io/components/table/overview)