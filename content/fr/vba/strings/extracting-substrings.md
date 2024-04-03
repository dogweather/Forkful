---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:53:07.442590-07:00
description: "Extraire des sous-cha\xEEnes dans Visual Basic pour Applications (VBA)\
  \ consiste \xE0 isoler des parties sp\xE9cifiques d'une cha\xEEne en fonction de\
  \ crit\xE8res donn\xE9s.\u2026"
lastmod: '2024-03-13T22:44:57.542127-06:00'
model: gpt-4-0125-preview
summary: "Extraire des sous-cha\xEEnes dans Visual Basic pour Applications (VBA) consiste\
  \ \xE0 isoler des parties sp\xE9cifiques d'une cha\xEEne en fonction de crit\xE8\
  res donn\xE9s."
title: "Extraction de sous-cha\xEEnes"
weight: 6
---

## Comment faire :
Dans VBA, vous utilisez principalement les fonctions `Mid`, `Left` et `Right` pour extraire des sous-chaînes. Ci-dessous, nous explorons ces fonctions avec des exemples :

1. **Mid** : Extrait une sous-chaîne d'une chaîne en commençant à une position spécifiée.
   ```basic
   Dim exampleString As String
   exampleString = "Bonjour le monde"
   Dim result As String
   result = Mid(exampleString, 9, 5)
   Debug.Print result  ' Sortie : le mo
   ```

2. **Left** : Extrait une sous-chaîne de la gauche de la chaîne, jusqu'à un nombre spécifié de caractères.
   ```basic
   Dim exampleString As String
   exampleString = "Bonjour le monde"
   Dim result As String
   result = Left(exampleString, 7)
   Debug.Print result  ' Sortie : Bonjour
   ```

3. **Right** : Extrait une sous-chaîne de la droite de la chaîne, jusqu'à un nombre spécifié de caractères.
   ```basic
   Dim exampleString As String
   exampleString = "Bonjour le monde"
   Dim result As String
   result = Right(exampleString, 5)
   Debug.Print result  ' Sortie : monde
   ```

Ces fonctions fondamentales constituent la base de l'extraction de sous-chaîne dans VBA, offrant des approches robustes et simples à la manipulation de chaînes.

## Exploration approfondie :
Historiquement, la capacité de manipuler des chaînes en programmation a été essentielle, avec BASIC (le précurseur du VBA) parmi les premiers à démocratiser cette capacité au début de l'informatique personnelle. Les fonctions `Mid`, `Left` et `Right` dans VBA héritent de cet héritage, offrant une interface simplifiée pour les programmeurs modernes.

Alors que ces fonctions sont assez efficaces pour de nombreuses tâches, l'émergence des Expressions Régulières dans les nouveaux langages a fourni un moyen plus puissant et souple de travailler avec le texte. Malgré cela, la simplicité immédiate et la disponibilité des fonctions de sous-chaîne traditionnelles VBA les rendent parfaitement adaptées pour les tâches rapides et pour ceux qui sont nouveaux en programmation.

Pour des opérations de parsing et de recherche plus complexes au sein des chaînes, VBA prend également en charge la correspondance de motifs à travers l'opérateur `Like` et les Expressions Régulières via l'objet `VBScript.RegExp`, bien que ces derniers nécessitent un peu plus de configuration et de compréhension pour être utilisés efficacement. Bien que ces outils offrent une plus grande puissance, la nature simple de `Mid`, `Left` et `Right` assure leur pertinence et leur utilité continue dans de nombreux programmes VBA.
