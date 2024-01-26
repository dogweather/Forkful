---
title:                "Recherche et remplacement de texte"
date:                  2024-01-20T17:58:37.325811-07:00
model:                 gpt-4-1106-preview
simple_title:         "Recherche et remplacement de texte"
programming_language: "Swift"
category:             "Swift"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/swift/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why?
Chercher et remplacer du texte, c'est un peu comme chasser les fautes de frappe et les corriger. Programmers le font pour nettoyer des données, mettre à jour des infos ou modifier du code plus vite que Flash sous caféine.

## How to:
```swift
var phrase = "Le renard brun rapide saute par-dessus le chien paresseux."

// Chercher et remplacer avec `replacingOccurrences(of:with:)`
let nouveauTexte = phrase.replacingOccurrences(of: "brun", with: "roux")
print(nouveauTexte) // "Le renard roux rapide saute par-dessus le chien paresseux."

// Utiliser des expressions régulières (regex) pour les remplacements complexes
let regexTexte = phrase.replacingOccurrences(of: "\\s+", with: "-", options: .regularExpression)
print(regexTexte) // "Le-renard-brun-rapide-saute-par-dessus-le-chien-paresseux."
```

## Deep Dive
L'histoire des recherches textuelles informatiques remonte aux premiers jours de programmation. À cette époque, la vitesse n'était pas ouf, mais l'importance de manipuler efficacement du texte était déjà claire. Avec Swift, Apple a simplifié la syntaxe en proposant des fonctions comme `replacingOccurrences(of:with:)`. Pour plus de puissance, on peut utiliser les expressions régulières qui offrent une flexibilité incroyable. Attention quand même, parce que cette puissance vient avec une complexité qui peut vite donner mal au crâne. Alternatives? Bibliothèques tierces comme `Regex` ou langages de scripting tels que Python ont leurs propres atouts, mais Swift tient la route pour la plupart des jobs.

## See Also
- [Apple Developer Documentation on String](https://developer.apple.com/documentation/swift/string)
- [Ray Wenderlich's Regex Tutorial in Swift](https://www.raywenderlich.com/5765-regular-expressions-tutorial-getting-started-with-regexes-in-swift)
- [NSRegularExpression Apple Docs](https://developer.apple.com/documentation/foundation/nsregularexpression)
