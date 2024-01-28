---
title:                "Arrondir les nombres"
date:                  2024-01-26T03:43:56.218890-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arrondir les nombres"
programming_language: "Elm"
category:             "Elm"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/elm/rounding-numbers.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Arrondir les nombres consiste à ajuster un décimal à sa valeur entière la plus proche ou à un nombre spécifié de chiffres fractionnaires. Les programmeurs arrondissent pour réduire la complexité, améliorer la lisibilité ou répondre aux exigences de précision.

## Comment faire :

Le module `Basics` d'Elm fournit des fonctions pratiques pour l'arrondissement : `round`, `floor` et `ceiling`. Voici comment les utiliser.

```elm
import Basics exposing (round, floor, ceiling)

-- Arrondir au nombre entier le plus proche
round 3.14    --> 3
round 3.5     --> 4

-- Arrondir à l'inférieur
floor 3.999   --> 3

-- Arrondir à la supérieure
ceiling 3.001 --> 4

-- Tronquer les décimales sans arrondir
truncate 3.76 --> 3
```

Elm propose également `toLocaleString` pour arrondir à un nombre fixe de décimales :

```elm
import Float exposing (toLocaleString)

-- Arrondir à deux décimales
toLocaleString 2 3.14159 --> "3.14"
```

## Approfondissement

Elm est un langage fonctionnel fortement typé qui relègue les effets secondaires aux "bords" de l'architecture. Cela signifie que des fonctions comme l'arrondissement doivent être pures et prévisibles. Historiquement, l'arrondissement est une opération commune dans de nombreux langages de programmation qui traitent de l'imprécision de l'arithmétique à virgule flottante.

L'approche d'Elm en matière d'arrondissement est simple - les fonctions sont pures et adhèrent aux définitions mathématiques pour round, floor et ceiling. Elm anticipe les besoins courants en fournissant des fonctions intégrées, car la gestion de la précision est une exigence fréquente, notamment dans la finance et les graphiques.

Les alternatives aux fonctions intégrées d'Elm pourraient inclure des implémentations personnalisées utilisant des opérations arithmétiques, mais cela ajoute une complexité inutile lorsque la bibliothèque standard fait déjà le travail de manière efficace.

Dans sa version actuelle, Elm utilise l'arithmétique à virgule flottante sous-jacente de JavaScript pour ces opérations, restant ainsi conforme à la norme IEEE 754, ce qui est à retenir lorsqu'on considère la précision et les éventuelles erreurs à virgule flottante.

## Voir également

- Documentation officielle du module `Basics` d'Elm : https://package.elm-lang.org/packages/elm/core/latest/Basics
- Un regard détaillé sur le fonctionnement des nombres à virgule flottante en informatique : https://floating-point-gui.de/
- Module `Float` d'Elm pour plus d'opérations à virgule flottante : https://package.elm-lang.org/packages/elm/core/latest/Float
