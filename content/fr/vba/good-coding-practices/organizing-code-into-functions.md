---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:56:22.166036-07:00
description: "L'organisation du code en fonctions dans Visual Basic pour Applications\
  \ (VBA) implique de d\xE9composer un programme en pi\xE8ces plus petites et g\xE9\
  rables,\u2026"
lastmod: '2024-03-13T22:44:57.585464-06:00'
model: gpt-4-0125-preview
summary: "L'organisation du code en fonctions dans Visual Basic pour Applications\
  \ (VBA) implique de d\xE9composer un programme en pi\xE8ces plus petites et g\xE9\
  rables, connues sous le nom de fonctions."
title: Organiser le code en fonctions
weight: 18
---

## Comment faire :
Dans VBA, les fonctions sont définies en utilisant les instructions `Function` et `End Function`. Voici un exemple simple de création d'une fonction qui calcule la surface d'un rectangle :

```basic
Function CalculateArea(length As Double, width As Double) As Double
    CalculateArea = length * width
End Function
```

Pour appeler cette fonction dans votre code VBA et afficher le résultat dans une boîte de message, vous utiliseriez :

```basic
Sub ShowArea()
    Dim area As Double
    area = CalculateArea(10, 5)
    MsgBox "La surface est " & area
End Sub
```

Lors de l'exécution, ce code affiche une boîte de message indiquant : `La surface est 50`.

### Passer des variables ByRef et ByVal
VBA vous permet de passer des variables aux fonctions soit par référence (`ByRef`) soit par valeur (`ByVal`). Le premier cas signifie que la variable originale peut être modifiée par la fonction, tandis que le dernier passe une copie, protégeant la variable originale des changements.

```basic
Function ModifyValue(ByRef num As Integer)
    num = num + 5
End Function

Function PreserveValue(ByVal num As Integer) As Integer
    num = num + 5
    PreserveValue = num
End Function
```

## Plongée profonde
VBA, en tant que langage de programmation piloté par les événements, met un accent significatif sur les fonctions et les sous-routines pour gérer diverses tâches. Contrairement à de nombreux langages modernes, VBA possède une caractéristique unique où le mot-clé `Function` ne déclare pas seulement un bloc de code réutilisable, mais permet également une valeur de retour implicite directement attribuée au nom de la fonction.

Historiquement, la conception des fonctions VBA a été influencée par des paradigmes de programmation antérieurs où l'encapsulation et la modularité étaient progressivement reconnues pour leur importance dans le développement de logiciels. Ce contexte historique a conduit VBA à adopter une approche quelque peu conservatrice mais fonctionnelle pour organiser le code.

Bien que VBA soit puissant dans ses environnements natifs (par exemple, les applications Microsoft Office), il est essentiel de noter que le monde de la programmation a évolué. Des langages comme Python offrent une syntaxe plus simple et une vaste bibliothèque standard, les rendant une alternative favorable pour diverses applications en dehors de la suite Office. Cependant, lorsqu'on travaille au sein des produits Microsoft Office, les capacités d'intégration et d'automatisation que VBA fournit sont inégalées.

Il vaut la peine de noter que malgré son âge, la communauté autour de VBA reste active, trouvant continuellement des moyens innovants pour tirer parti de sa fonctionnalité. Pourtant, à mesure que l'industrie du logiciel évolue vers des langages plus modernes, polyvalents et robustes, les programmeurs familiers avec VBA sont encouragés à explorer ces alternatives pour des tâches non liées à Office afin d'élargir leur boîte à outils de codage.
