---
title:                "Arrondir les nombres"
aliases:
- /fr/python/rounding-numbers/
date:                  2024-01-26T03:47:01.917175-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arrondir les nombres"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/python/rounding-numbers.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Arrondir des nombres signifie les ajuster pour les rapprocher d'une valeur plus simple ou plus significative. Les programmeurs arrondissent les nombres pour simplifier les résultats, limiter le nombre de décimales à afficher, ou pour certaines fins mathématiques.

## Comment faire :
Voici l'essentiel sur l'arrondissement des nombres en Python :

```python
# Arrondir un nombre à l'entier le plus proche
print(round(8.67))  # Résultat : 9

# Arrondir un nombre à un nombre spécifié de décimales
print(round(8.67, 1))  # Résultat : 8.7

# Les nombres pairs sont arrondis à l'inférieur et les nombres impairs sont arrondis à la hausse lorsqu'équidistants
print(round(2.5))  # Résultat : 2
print(round(3.5))  # Résultat : 4
```

## Plongée profonde
En Python, `round()` ne se contente pas de tronquer les décimales. Historiquement, Python, comme de nombreux autres langages, suit la règle du "arrondi à la demi au pair" ou "arrondi du banquier". Cela minimise l'erreur cumulative dans les sommes ou les moyennes, ce qui est important dans les calculs financiers.

Pour des alternatives, vous avez `math.floor()` et `math.ceil()` du module math de Python, qui arrondissent les nombres à l'entier inférieur ou supérieur le plus proche. Mais si c'est la précision que vous recherchez, la méthode `quantize()` du module `decimal` vous permet de spécifier le comportement d'arrondissement.

Sous le capot, `round()` traite avec des nombres à virgule flottante binaires. Comme certains décimales ne peuvent pas être exprimés exactement en binaire, vous pourriez avoir des surprises avec des cas comme `round(2.675, 2)` ne devenant pas `2.68` comme attendu. Faites appel à `decimal` ou `fractions` pour une haute précision.

## Voir aussi
- Documentation de Python sur les fonctions intégrées : https://docs.python.org/3/library/functions.html#round
- Arithmétique à point fixe et à virgule flottante `decimal` : https://docs.python.org/3/library/decimal.html
- Module math de Python : https://docs.python.org/3/library/math.html
