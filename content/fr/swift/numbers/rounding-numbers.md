---
date: 2024-01-26 03:46:49.451668-07:00
description: "Arrondir des nombres signifie approximer une valeur num\xE9rique \xE0\
  \ une pr\xE9cision sp\xE9cifique, typiquement pour \xE9liminer les d\xE9cimales\
  \ ind\xE9sirables. Les\u2026"
lastmod: '2024-03-13T22:44:58.215056-06:00'
model: gpt-4-0125-preview
summary: "Arrondir des nombres signifie approximer une valeur num\xE9rique \xE0 une\
  \ pr\xE9cision sp\xE9cifique, typiquement pour \xE9liminer les d\xE9cimales ind\xE9\
  sirables."
title: Arrondir les nombres
weight: 13
---

## Comment faire :
Swift offre plusieurs manières d'arrondir les nombres. En voici un aperçu :

```Swift
let original = 3.14159

// Arrondissement standard
let standardRounded = round(original) // 3.0

// Arrondissement à un nombre spécifique de décimales
let decimalRounded = Double(round(original * 1000) / 1000) // 3.142

// Arrondissement à l'inférieur
let roundedDown = floor(original) // 3.0

// Arrondissement à la hausse
let roundedUp = ceil(original) // 4.0

print("Standard: \(standardRounded), Decimal: \(decimalRounded), Inférieur: \(roundedDown), Supérieur: \(roundedUp)")
```

Sortie : `Standard: 3.0, Decimal: 3.142, Inférieur: 3.0, Supérieur: 4.0`

## Plongée profonde
Historiquement, l'arrondissement est un concept mathématique antérieur aux ordinateurs, essentiel dans le commerce et la science. Le cadre `Foundation` de Swift offre des fonctionnalités d'arrondissement complètes :

- `round(_: )` est le bon vieux arrondissement à la demi-supérieure.
- `floor(_: )` et `ceil(_: )` gèrent l'arrondissement directionnel.
- `rounded(.up/.down/.toNearestOrAwayFromZero)` offre un contrôle plus fin avec l'énumération des règles d'arrondissement.

Soyez conscient du type `Decimal` pour des calculs financiers précis, qui évite les erreurs de point flottant. Explorez également `NSDecimalNumber` pour la compatibilité avec Objective-C.

## Voir aussi
- Norme IEEE pour l'arithmétique à virgule flottante (IEEE 754) : [IEEE 754](https://ieeexplore.ieee.org/document/4610935)
