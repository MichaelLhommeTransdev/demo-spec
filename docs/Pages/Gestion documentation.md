#RiskMedium

![Pasted image 20230125095526](../medias/Pasted%20image%2020230125095526.png)

![Pasted image 20230125095452](../medias/Pasted%20image%2020230125095452.png)

## Estimation

Durée : 2j
Risque : 1

## Implémentation

#TODO Split composants

### Validation

Thèmes :
- code : maxLen = 3
- name : maxLen = 100
- short : maxLen = 30

Settings : 
- maxSize : strict positive
- delayBeforeClean : strict postive

Documentation :
- name : maxLen = 100
- short : maxLen = 30
- version : maxLen = 10
- file : size <= Settings maxSize

### Services
- [DocumentationSVC](../Services/DocumentationSVC.md)
	- add
	- update
	- delete
	- addTheme
	- updateTheme
	- deleteTheme

### Material
- [Table](https://material.angular.io/components/table)
- [Slide toggle](https://material.angular.io/components/slide-toggle)
- [Button](https://material.angular.io/components/button)
- [Checkbox](https://material.angular.io/components/checkbox)o

### Autre
- Uploader