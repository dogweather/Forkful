---
title:                "Arrondissement des nombres"
aliases:
- fr/go/rounding-numbers.md
date:                  2024-02-03T18:07:36.151911-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arrondissement des nombres"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/go/rounding-numbers.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Arrondir les nombres consiste à ajuster la valeur d’un nombre à son nombre entier le plus proche ou à un nombre spécifique de décimales. Les programmeurs font cela pour des raisons telles que l'amélioration de la lisibilité, la simplification des calculs ou la satisfaction des exigences de précision spécifiques au domaine.

## Comment faire :

En Go, il n'y a pas de fonction intégrée qui arrondit directement les nombres à un nombre spécifique de décimales dans le package math. Cependant, vous pouvez réaliser l'arrondi grâce à une combinaison de fonctions pour les nombres entiers ou implémenter une fonction personnalisée pour les décimales.

### Arrondir au nombre entier le plus proche :

Pour arrondir au nombre entier le plus proche, vous pouvez utiliser la fonction `math.Floor()` avec un ajout de 0,5 pour les nombres positifs, et `math.Ceil()` moins 0,5 pour les nombres négatifs, selon la direction vers laquelle vous souhaitez arrondir.

```go
package main

import (
	"fmt"
	"math"
)

func main() {
	fmt.Println(math.Floor(3.75 + 0.5))  // Affiche : 4
	fmt.Println(math.Ceil(-3.75 - 0.5)) // Affiche : -4
}
```

### Arrondir à un nombre spécifique de décimales :

Pour arrondir à un nombre spécifique de décimales, une fonction personnalisée peut être utilisée où vous multipliez le nombre par 10^n (où n est le nombre de décimales), l'arrondissez au nombre entier le plus proche comme précédemment, puis divisez par 10^n.

```go
package main

import (
	"fmt"
	"math"
)

func roundToDecimalPlace(number float64, places int) float64 {
	shift := math.Pow(10, float64(places))
	return math.Round(number*shift) / shift
}

func main() {
	fmt.Println(roundToDecimalPlace(3.14159, 2)) // Affiche : 3.14
	fmt.Println(roundToDecimalPlace(-3.14159, 3)) // Affiche : -3.142
}
```

## Approfondissement

Arrondir les nombres est une opération fondamentale en programmation informatique, liée au défi historique de représenter les nombres réels dans un système binaire. Le besoin d'arrondissement découle du fait que de nombreux nombres réels ne peuvent pas être représentés précisément en binaire, conduisant à des erreurs d'approximation.

En Go, l'approche de l'arrondissement est quelque peu manuelle par rapport aux langues qui offrent des fonctions d'arrondissement intégrées à des décimales spécifiques. Néanmoins, le package `math` de la bibliothèque standard de Go fournit les briques de base (comme `math.Floor` et `math.Ceil`) pour construire tout mécanisme d'arrondissement requis par l'application.

Cette approche manuelle, bien qu'apparemment plus laborieuse, offre aux programmeurs un contrôle plus fin sur la manière dont les nombres sont arrondis, répondant aux besoins de précision et d'exactitude de différentes applications. Les alternatives telles que les bibliothèques tierces ou la conception de fonctions d'arrondissement personnalisées peuvent fournir des solutions plus simples lorsqu'il s'agit de traiter des nombres complexes ou de nécessiter des opérations mathématiques plus avancées non couvertes par la bibliothèque standard.

En conclusion, bien que la bibliothèque standard de Go n'offre pas de fonctionnalité directe d'arrondissement au nombre de décimales, son ensemble complet de fonctions mathématiques permet aux développeurs de mettre en œuvre des solutions d'arrondissement robustes adaptées à leurs besoins spécifiques.
