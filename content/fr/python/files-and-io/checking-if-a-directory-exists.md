---
title:                "Vérifier si un répertoire existe"
date:                  2024-02-03T19:08:11.560208-07:00
model:                 gpt-4-0125-preview
simple_title:         "Vérifier si un répertoire existe"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/python/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Vérifier si un répertoire existe en Python consiste à confirmer la présence d'un dossier dans le système de fichiers avant d'effectuer des opérations telles que la lecture ou l'écriture de fichiers. Les programmeurs font cela pour éviter des erreurs telles que `FileNotFoundError`, assurant que l'application se comporte de manière fiable et ne plante pas lors de la tentative d'interaction avec les répertoires.

## Comment faire :

Python fournit des moyens natifs de vérifier l'existence d'un répertoire en utilisant les modules `os` et `pathlib`. Voici des exemples pour les deux :

### Utiliser le module `os`
```python
import os

# Spécifier le chemin du répertoire
dir_path = "/chemin/vers/repertoire"

# Vérifier si le répertoire existe
if os.path.isdir(dir_path):
    print(f"Le répertoire {dir_path} existe.")
else:
    print(f"Le répertoire {dir_path} n'existe pas.")
```

### Utiliser le module `pathlib`
```python
from pathlib import Path

# Spécifier le chemin du répertoire
dir_path = Path("/chemin/vers/repertoire")

# Vérifier si le répertoire existe
if dir_path.is_dir():
    print(f"Le répertoire {dir_path} existe.")
else:
    print(f"Le répertoire {dir_path} n'existe pas.")
```

### Bibliothèques tierces
Bien que la bibliothèque standard de Python soit suffisante pour vérifier si un répertoire existe, des bibliothèques comme `pathlib2` peuvent être des alternatives pour une cohérence à travers les versions de Python ou pour des fonctionnalités additionnelles.

***Note :*** Avec les dernières versions de Python, `pathlib` est assez robuste pour la plupart des cas d'usage, rendant les bibliothèques tierces moins nécessaires pour cette tâche spécifique.
