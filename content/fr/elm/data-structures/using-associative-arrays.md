---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:49.049169-07:00
description: "Les tableaux associatifs, ou comme les appelle Elm, les Dictionnaires,\
  \ associent des cl\xE9s \xE0 des valeurs de mani\xE8re \xE0 rendre la recherche,\
  \ l'insertion et\u2026"
lastmod: '2024-03-13T22:44:57.681369-06:00'
model: gpt-4-0125-preview
summary: "Les tableaux associatifs, ou comme les appelle Elm, les Dictionnaires, associent\
  \ des cl\xE9s \xE0 des valeurs de mani\xE8re \xE0 rendre la recherche, l'insertion\
  \ et la suppression de valeurs extr\xEAmement rapides."
title: Utilisation des tableaux associatifs
weight: 15
---

## Comment faire :
Dans Elm, vous travaillez avec les Dictionnaires dans le module `Dict`, alors plongeons dans un exemple rapide :

```Elm
import Dict exposing (Dict)

-- Initialisation d'un dictionnaire avec des clés String et des valeurs Int
exampleDict : Dict String Int
exampleDict = Dict.fromList [("apple", 5), ("banana", 2), ("orange", 8)]

-- Ajout ou mise à jour d'une valeur
updatedDict = Dict.insert "grape" 10 exampleDict

-- Récupération d'une valeur (remarquez le type Maybe, car la clé peut ne pas être présente)
fruitCount : Maybe Int
fruitCount = Dict.get "apple" updatedDict

-- Suppression d'une paire clé-valeur
finalDict = Dict.remove "banana" updatedDict

-- Conversion d'un dictionnaire en liste
dictToList = Dict.toList finalDict
```

Exemple de sortie lors de l'affichage de `dictToList` :

```Elm
[("apple", 5), ("grape", 10), ("orange", 8)]
```

Cela démontre les opérations de base : création, mise à jour, accès et itération sur un Dictionnaire.

## Plongée en profondeur
À l'intérieur, les Dictionnaires dans Elm utilisent une structure connue sous le nom d'arbre AVL - un type d'arbre binaire de recherche auto-équilibré. Ce choix établit un équilibre entre assurer que des opérations comme insert, get et remove aient de bonnes performances (complexité temporelle logarithmique) et maintenir la simplicité dans la manipulation des données.

Malgré les points forts du `Dict` d'Elm, ce n'est pas une solution universelle. Pour des collections qui sont ordonnées ou doivent être parcourues séquentiellement, List ou Array pourraient être plus appropriés. De plus, lorsqu'on travaille avec un ensemble fixe de clés connues, utiliser des types personnalisés (la version des énumérations par Elm) pourrait offrir plus de sécurité de type et une intention plus claire dans votre code.

Dans l'écosystème d'Elm, `Dict` offre un moyen fiable de gérer des collections de paires clé-valeur où les clés sont uniques et l'ordre n'a pas d'importance. Tandis que des structures plus récentes ou plus sophistiquées peuvent émerger, le module `Dict` reste un outil fondamental dans la boîte à outils du programmeur Elm pour sa simplicité et son efficacité dans la manipulation de tableaux associatifs.
