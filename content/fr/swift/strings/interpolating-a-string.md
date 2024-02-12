---
title:                "Interpolation de chaînes de caractères"
aliases:
- /fr/swift/interpolating-a-string/
date:                  2024-01-20T17:51:45.359252-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolation de chaînes de caractères"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/swift/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
L'interpolation de chaînes permet d'insérer des valeurs dans une chaîne de caractères. On l'utilise pour composer des messages dynamiques, lisibles et personnalisables.

## How to:
```Swift
let name = "Marie"
let age = 28
let greeting = "Bonjour \(name), tu as \(age) ans!"
print(greeting)
```
Sortie: `Bonjour Marie, tu as 28 ans!`

```Swift
let temperature = 21.5
let weatherMessage = "Il fait \(temperature)°C aujourd'hui."
print(weatherMessage)
```
Sortie: `Il fait 21.5°C aujourd'hui.`

## Deep Dive
Historiquement, Swift a bouleversé la manipulation de chaînes en simplifiant l'interpolation, une amélioration par rapport à Objective-C et ses méthodes verbeuses, comme `stringWithFormat:`. Contrairement à la concaténation classique, l'interpolation permet d'insérer directement des expressions et des variables dans une chaîne sans casser le flux du texte.

En alternatives, on trouve `String(format:)`, similaire aux printf en C, et la concaténation, mais l'interpolation est plus concise et naturelle en Swift. Techniquement, Swift appelle la méthode `CustomStringConvertible` de chaque objet interpolé pour obtenir sa représentation en chaîne de caractères, permettant une personnalisation à travers le protocole.

## See Also
- La documentation Apple sur l'interpolation de chaînes: [Swift String Interpolation](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html#ID292)
- Un guide sur le protocole `CustomStringConvertible`: [Swift.org - CustomStringConvertible](https://developer.apple.com/documentation/swift/customstringconvertible)
