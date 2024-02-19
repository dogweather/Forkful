---
aliases:
- /fr/python/writing-a-text-file/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:28:56.442243-07:00
description: "\xC9crire dans un fichier texte avec Python est une t\xE2che fondamentale\
  \ qui implique de cr\xE9er ou d'ouvrir un fichier, puis d'y ajouter du texte ou\
  \ de le\u2026"
lastmod: 2024-02-18 23:09:08.360510
model: gpt-4-0125-preview
summary: "\xC9crire dans un fichier texte avec Python est une t\xE2che fondamentale\
  \ qui implique de cr\xE9er ou d'ouvrir un fichier, puis d'y ajouter du texte ou\
  \ de le\u2026"
title: "R\xE9diger un fichier texte"
---

{{< edit_this_page >}}

## Quoi et pourquoi ?
Écrire dans un fichier texte avec Python est une tâche fondamentale qui implique de créer ou d'ouvrir un fichier, puis d'y ajouter du texte ou de le remplacer. Cette fonctionnalité est cruciale pour l'enregistrement de données, la gestion de configuration, et le stockage des résultats générés par des programmes, ce qui en fait un outil de base mais essentiel dans l'arsenal d'un programmeur.

## Comment faire :
### Utiliser la fonction intégrée `open()`
La fonction intégrée `open()` de Python est le moyen le plus courant d'écrire dans des fichiers. La fonction permet de spécifier le mode dans lequel le fichier est ouvert - 'w' pour écrire (en remplacement), 'a' pour ajouter, et 'w+' pour écrire+lire.

```python
# Écrire dans un nouveau fichier ou remplacer un fichier existant
with open('exemple.txt', 'w') as fichier:
    fichier.write("Bonjour, le monde !\n")

# Ajouter du texte à un fichier
with open('exemple.txt', 'a') as fichier:
    fichier.write("Ajout de plus de texte.\n")

# Lire le fichier pour vérifier
with open('exemple.txt', 'r') as fichier:
    print(fichier.read())
```
**Exemple de sortie :**
```
Bonjour, le monde !
Ajout de plus de texte.
```
### Utiliser `pathlib.Path`
Pour une approche plus orientée objet, la classe `Path` du module `pathlib` offre une méthode pour écrire dans des fichiers. C'est une méthode populaire pour les bases de code Python plus récentes.

```python
from pathlib import Path

# Écrire/Remplacer un fichier
Path('exemple2.txt').write_text("Ceci est l'exemple 2.\n")

# Lire le fichier pour vérifier
print(Path('exemple2.txt').read_text())

# Note : `Path.write_text` remplace toujours le contenu du fichier. 
# Pour ajouter, vous devrez ouvrir le fichier comme montré dans la section précédente.
```
**Exemple de sortie :**
```
Ceci est l'exemple 2.
```

### Bibliothèques tierces
Pour des opérations de fichier complexes, des bibliothèques tierces comme `pandas` (pour les fichiers CSV, Excel) peuvent être un atout considérable. Voici un rapide exemple d'écriture d'un DataFrame dans un fichier CSV en utilisant `pandas`, démontrant son utilité au-delà des simples fichiers texte.

```python
# Cet exemple nécessite pandas : pip install pandas
import pandas as pd

# Création d'un simple DataFrame
data = pd.DataFrame({'Colonne1': [1, 2, 3], 'Colonne2': ['A', 'B', 'C']})

# Écrire le DataFrame dans un fichier CSV
data.to_csv('exemple.csv', sans_index=False)

# Lire le CSV pour vérifier
print(pd.read_csv('exemple.csv'))
```
**Exemple de sortie :**
```
   Colonne1 Colonne2
0         1        A
1         2        B
2         3        C
```

En utilisant ces méthodes, les programmeurs Python peuvent gérer efficacement les opérations sur les fichiers, répondant à la fois aux besoins simples et complexes de manipulation de données.
