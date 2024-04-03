---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:27:36.462027-07:00
description: "\xC9crire dans un fichier texte avec Fish Shell vous permet de stocker\
  \ des donn\xE9es de mani\xE8re persistante, facilitant ainsi la r\xE9cup\xE9ration\
  \ ou la\u2026"
lastmod: '2024-03-13T22:44:58.344133-06:00'
model: gpt-4-0125-preview
summary: "\xC9crire dans un fichier texte avec Fish Shell vous permet de stocker des\
  \ donn\xE9es de mani\xE8re persistante, facilitant ainsi la r\xE9cup\xE9ration ou\
  \ la manipulation des donn\xE9es soit par le m\xEAme script Fish soit par d'autres\
  \ programmes."
title: "R\xE9diger un fichier texte"
weight: 24
---

## Comment faire :
Pour écrire dans un fichier texte en Fish, vous pouvez utiliser la commande `echo` combinée avec des opérateurs de redirection. Il n'y a pas de bibliothèques tierces populaires spécifiquement pour l'écriture de fichiers en Fish, car les commandes intégrées du shell sont simples et efficaces à cet effet.

### Écrire du texte dans un nouveau fichier ou écraser un fichier existant :
```fish
echo "Bonjour, Fish Shell !" > output.txt
```
Cette commande écrit "Bonjour, Fish Shell !" dans `output.txt`, en créant le fichier s'il n'existe pas ou en l'écrasant s'il existe.

### Ajouter du texte à un fichier existant :
Si vous souhaitez ajouter du texte à la fin d'un fichier existant sans supprimer son contenu actuel, utilisez l'opérateur d'ajout `>>` :
```fish
echo "Ajout d'une nouvelle ligne au fichier." >> output.txt
```

### Écrire plusieurs lignes :
Vous pouvez écrire plusieurs lignes dans un fichier en utilisant echo avec un caractère de nouvelle ligne `\n`, ou vous pouvez enchaîner plusieurs commandes echo à l'aide de points-virgules :
```fish
echo "Première Ligne\nDeuxième Ligne" > output.txt
# OU
echo "Première Ligne" > output.txt; echo "Deuxième Ligne" >> output.txt
```

### Exemple de sortie :
Pour voir le contenu de `output.txt` après avoir exécuté les commandes ci-dessus, utilisez la commande `cat` :
```fish
cat output.txt
```
```plaintext
Première Ligne
Deuxième Ligne
```
Remplacer ou ajouter des textes comme montré manipule le contenu du fichier selon vos besoins, démontrant des manières simples mais puissantes de travailler avec des fichiers texte en Fish Shell.
