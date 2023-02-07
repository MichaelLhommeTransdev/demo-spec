Un simple tableau permettant l'affichage et la suppression des thèmes de documentation.

![](/medias/documentation_themes_table.png)

## Implémentation

L'édition est accessible via un bouton présent sur chaque ligne, et la création de nouveaux thèmes via un bouton général. Ces deux actions ouvrent un [formulaire dialogue](./DocumentationThemeFormDialog.md).

!!! warning
    La suppression ne doit pas être possible si des documentations existent pour ce thème (champ `itemsCount` > 0)

## Utilisation des services

- [DocumentationStore](/Store/DocumentationStore)