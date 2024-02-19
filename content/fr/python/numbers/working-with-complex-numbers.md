---
aliases:
- /fr/python/working-with-complex-numbers/
date: 2024-01-26 04:44:38.566328-07:00
description: "Les nombres complexes sont un ensemble de nombres de la forme `a + bi`,\
  \ o\xF9 `a` et `b` sont des nombres r\xE9els, et `i` est l'unit\xE9 imaginaire (`i^2\
  \ = -1`).\u2026"
lastmod: 2024-02-18 23:09:08.333335
model: gpt-4-0125-preview
summary: "Les nombres complexes sont un ensemble de nombres de la forme `a + bi`,\
  \ o\xF9 `a` et `b` sont des nombres r\xE9els, et `i` est l'unit\xE9 imaginaire (`i^2\
  \ = -1`).\u2026"
title: Manipulation des nombres complexes
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Les nombres complexes sont un ensemble de nombres de la forme `a + bi`, où `a` et `b` sont des nombres réels, et `i` est l'unité imaginaire (`i^2 = -1`). En programmation, nous les utilisons pour résoudre des problèmes dans divers domaines, comme le génie électrique, le traitement des signaux et l'informatique quantique.

## Comment faire :
Python prend en charge les nombres complexes de manière intégrée. Voici comment vous pouvez les manipuler :

```Python
# Création de nombres complexes
z = 4 + 5j
print(z)  # Sortie : (4+5j)

# Accès aux parties réelle et imaginaire
print(z.real)  # Sortie : 4.0
print(z.imag)  # Sortie : 5.0

# Arithmétique complexe
w = 1 - 2j
print(z + w)  # Sortie : (5+3j)
print(z - w)  # Sortie : (3+7j)
print(z * w)  # Sortie : (14+2j)
print(z / w)  # Sortie : (-3.6+1.2j)

# Module (valeur absolue)
print(abs(z))  # Sortie : 6.4031242374328485

# Conjugaison d'un nombre complexe
print(z.conjugate())  # Sortie : (4-5j)
```

## Plongée profonde
Les nombres complexes ont été conceptualisés pour la première fois par Gerolamo Cardano au XVIe siècle. Python, parmi d'autres langages de programmation, traite les nombres complexes comme des citoyens de première classe. Cela signifie qu'ils sont intégrés dans le langage, avec des fonctionnalités faciles à utiliser, évitant le besoin d'importer des bibliothèques externes pour les opérations de base.

Cependant, pour les calculs numériques lourds, Python dispose d'une bibliothèque appelée `cmath`, qui est spécifiquement pour les nombres complexes. Elle contient des fonctions supplémentaires comme `exp`, `log`, et des opérations trigonométriques.

Lorsque Python ne suffit pas, vous pourriez vous tourner vers des bibliothèques comme NumPy, en particulier pour les opérations sur les tableaux impliquant des nombres complexes. NumPy fournit des opérations optimisées et vectorisées qui sont cruciales pour la performance en calcul numérique.

## Voir aussi
Consultez ces ressources pour en savoir plus :

- Documentation officielle de Python sur les nombres complexes : https://docs.python.org/3/library/stdtypes.html#typesnumeric
- Documentation du module `cmath` : https://docs.python.org/3/library/cmath.html
- NumPy pour la gestion des tableaux de nombres complexes : https://numpy.org/doc/stable/user/absolute_beginners.html#the-basics
