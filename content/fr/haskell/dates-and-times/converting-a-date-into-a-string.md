---
date: 2024-01-20 17:36:43.360644-07:00
description: "Convertir une date en cha\xEEne nous permet de la formater pour l'affichage.\
  \ Les programmeurs le font pour rendre les dates compr\xE9hensibles par les humains\u2026"
lastmod: '2024-03-13T22:44:57.845919-06:00'
model: gpt-4-1106-preview
summary: "Convertir une date en cha\xEEne nous permet de la formater pour l'affichage."
title: "Conversion d'une date en cha\xEEne de caract\xE8res"
weight: 28
---

## Comment faire :
```Haskell
import Data.Time

-- Convertit une date en une chaîne avec un formatage standard
dateToString :: IO String
dateToString = do
    current_time <- getCurrentTime
    let date = utctDay current_time
    return $ showGregorian date

main :: IO ()
main = do
    dateString <- dateToString
    putStrLn dateString
```
Sortie possible :
```
2023-03-15
```

## Plongeon en profondeur
Haskell utilise le package `time` pour gérer les dates. Historiquement, `Data.Time` est le module standard pour travailler avec le temps et les dates, succédant à des bibliothèques moins complètes. Alternativement, on peut utiliser `formatTime` pour un contrôle précis sur le format de sortie. L'implémentation repose sur des types abstraits comme `UTCTime`, ce qui assure la validité des données.

## Voir aussi
- [Haskell `time` package](https://hackage.haskell.org/package/time)
- [`Data.Time.Format` documentation](https://hackage.haskell.org/package/time-1.9.3/docs/Data-Time-Format.html)
- [Haskell Hierarchical Libraries](https://downloads.haskell.org/~ghc/latest/docs/html/libraries/)
