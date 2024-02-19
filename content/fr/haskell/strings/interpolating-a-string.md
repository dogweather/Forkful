---
aliases:
- /fr/haskell/interpolating-a-string/
date: 2024-01-20 17:51:23.521828-07:00
description: "L'interpolation de cha\xEEnes de caract\xE8res permet d'ins\xE9rer des\
  \ variables ou des expressions directement dans une cha\xEEne. Les programmeurs\
  \ l'utilisent pour\u2026"
lastmod: 2024-02-18 23:09:08.859661
model: gpt-4-1106-preview
summary: "L'interpolation de cha\xEEnes de caract\xE8res permet d'ins\xE9rer des variables\
  \ ou des expressions directement dans une cha\xEEne. Les programmeurs l'utilisent\
  \ pour\u2026"
title: "Interpolation de cha\xEEnes de caract\xE8res"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
L'interpolation de chaînes de caractères permet d'insérer des variables ou des expressions directement dans une chaîne. Les programmeurs l'utilisent pour simplifier la concaténation de chaînes et pour améliorer la lisibilité du code.

## Comment faire :
Haskell n'offre pas l'interpolation de chaînes nativement comme dans d'autres langages. Pour interpoler, il faut utiliser des bibliothèques comme `printf` ou `interpolate`. Voici quelques exemples :

```haskell
import Text.Printf (printf)

-- Avec printf
name = "monde"
greeting = printf "Bonjour, %s!" name  -- "Bonjour, monde!"

-- Avec interpolate (il faut d'abord installer le paquet interpolate)
{-# LANGUAGE QuasiQuotes #-}
import Data.String.Interpolate (i)

-- Avec i (interpolate)
name = "monde"
greeting = [i|Bonjour, #{name}!|]  -- "Bonjour, monde!"
```

## Plongée Profonde
Historiquement, Haskell ne s'est pas concentré sur l'interpolation de chaînes car la philosophie du langage préconise la fonctionnalité par rapport à la syntaxe sucrée. La concaténation explicite via des fonctions telles que `(++)` et l'utilisation de la composition de fonctions sont des approches plus traditionnelles en Haskell. Comparativement, `printf` vient de l'héritage C et est moins typé sauf si on utilise des versions plus typesafe.

Le package `interpolate` utilise la technique des quasi-quotes, une fonctionnalité depuis la version GHC 6.10, pour approximer une fonctionnalité d'interpolation dans le langage. Cela rend le code plus proche d'autres langues qui supportent l'interpolation nativement, comme Ruby ou JavaScript.

Alternativement, vous pouvez utiliser `fmt` qui fournit une DSL pour le formatage qui peut être plus sécurisée. Il faut garder en tête que chaque bibliothèque externe rajoute une dépendance à votre projet.

## Voir Aussi

- [`printf` documentation](https://hackage.haskell.org/package/base-4.16.1.0/docs/Text-Printf.html)
- [`interpolate` package](https://hackage.haskell.org/package/interpolate)
- [`fmt` library](https://hackage.haskell.org/package/fmt-0.6.1.2/docs/Fmt.html)
