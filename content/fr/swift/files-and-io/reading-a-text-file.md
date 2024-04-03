---
date: 2024-01-20 17:55:17.497244-07:00
description: "La lecture de fichiers texte consiste \xE0 acc\xE9der au contenu stock\xE9\
  \ dans des fichiers sur le disque pour pouvoir le manipuler ou l'analyser. Les\u2026"
lastmod: '2024-03-13T22:44:58.245984-06:00'
model: gpt-4-1106-preview
summary: "La lecture de fichiers texte consiste \xE0 acc\xE9der au contenu stock\xE9\
  \ dans des fichiers sur le disque pour pouvoir le manipuler ou l'analyser."
title: Lecture d'un fichier texte
weight: 22
---

## Comment faire :
```Swift
import Foundation

if let cheminDuFichier = Bundle.main.path(forResource: "exemple", ofType: "txt"),
   let contenu = try? String(contentsOfFile: cheminDuFichier) {
    print(contenu)
} else {
    print("Impossible de lire le fichier.")
}
```
Sortie échantillon :
```
Bonjour, ceci est le contenu de votre fichier texte.
```

## Zoom Sur Le Sujet
Historiquement, la lecture de fichiers est l'une des opérations les plus fondamentales en programmation. En Swift, `String(contentsOfFile:)` et `String(contentsOfURL:)` existent depuis les premières versions. Il y a d'autres moyens, comme l'utilisation de `FileHandle` ou de bas niveau avec `fopen` en C intégré, mais `String(contentsOfFile:)` est souvent le plus simple pour des fichiers textes. Pour gérer de gros fichiers ou des opérations plus complexes, vous pourriez avoir besoin de streamer le fichier avec `InputStream`. Attention à la gestion de l'encodage des fichiers, surtout si vous échangez des fichiers entre différents systèmes qui peuvent avoir des standards d'encodage différents.

## Voir Aussi
- [Apple Developer Documentation: String](https://developer.apple.com/documentation/swift/string)
- [Tutorial sur Ray Wenderlich pour la gestion de fichiers en Swift](https://www.raywenderlich.com/660-using-files-swift)
