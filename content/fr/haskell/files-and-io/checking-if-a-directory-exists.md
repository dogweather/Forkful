---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:24.209008-07:00
description: "V\xE9rifier si un r\xE9pertoire existe est une op\xE9ration fondamentale\
  \ dans de nombreuses t\xE2ches de programmation, permettant des actions conditionnelles\
  \ bas\xE9es\u2026"
lastmod: '2024-03-13T22:44:57.848850-06:00'
model: gpt-4-0125-preview
summary: "V\xE9rifier si un r\xE9pertoire existe est une op\xE9ration fondamentale\
  \ dans de nombreuses t\xE2ches de programmation, permettant des actions conditionnelles\
  \ bas\xE9es sur la pr\xE9sence ou l'absence de structures de r\xE9pertoires."
title: "V\xE9rifier si un r\xE9pertoire existe"
weight: 20
---

## Comment faire :
Haskell, grâce à sa bibliothèque de base, offre des moyens simples de vérifier l'existence d'un répertoire, principalement en utilisant le module `System.Directory`. Voyons un exemple de base :

```haskell
import System.Directory (doesDirectoryExist)

main :: IO ()
main = do
  let dirPath = "/chemin/vers/votre/repertoire"
  exists <- doesDirectoryExist dirPath
  putStrLn $ "Le répertoire existe-t-il ? " ++ show exists
```

Exemple de sortie, selon que le répertoire existe ou non :

```
Le répertoire existe-t-il ? True
```
Ou :
```
Le répertoire existe-t-il ? False
```

Pour des scénarios plus complexes ou une fonctionnalité supplémentaire, vous pourriez envisager une bibliothèque tierce populaire comme `filepath` pour manipuler et gérer les chemins de fichiers de manière plus abstraite. Cependant, pour le but simple de vérifier si un répertoire existe, le `System.Directory` de la bibliothèque de base est suffisant et efficace.

Rappelez-vous, travailler avec des systèmes de fichiers peut varier selon les plateformes, et l'approche de Haskell vise à abstraire certaines de ces différences. Testez toujours vos opérations de fichiers sur le système cible pour garantir un comportement attendu.
