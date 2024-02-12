---
title:                "Comparer deux dates"
aliases:
- /fr/swift/comparing-two-dates/
date:                  2024-01-20T17:34:09.350680-07:00
model:                 gpt-4-1106-preview
simple_title:         "Comparer deux dates"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/swift/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi?)

Comparer deux dates, c'est décider si une date est plus tôt, plus tard ou la même qu'une autre. Les programmeurs le font pour gérer les événements, les dates limites et suivre la durée.

## How to: (Comment faire : )

```Swift
import Foundation

// Création de deux dates
let dateFormatter = DateFormatter()
dateFormatter.dateFormat = "yyyy/MM/dd HH:mm"
let firstDate = dateFormatter.date(from: "2023/04/01 09:30")!
let secondDate = dateFormatter.date(from: "2023/04/01 10:00")!

// Comparer les dates
if firstDate == secondDate {
    print("Les dates sont identiques.")
} else if firstDate < secondDate {
    print("La première date est plus tôt que la deuxième.")
} else {
    print("La première date est plus tard que la deuxième.")
}

// Utilisation de isEqual(to:), isBefore(value:) et isAfter(value:)
// dans une extension pour clarifier l'intention
extension Date {
    func isEqual(to otherDate: Date) -> Bool {
        return self == otherDate
    }
    func isBefore(_ otherDate: Date) -> Bool {
        return self < otherDate
    }
    func isAfter(_ otherDate: Date) -> Bool {
        return self > otherDate
    }
}

// Utilisation de l'extension
if firstDate.isEqual(to: secondDate) {
    print("Les dates sont identiques.")
} else if firstDate.isBefore(secondDate) {
    print("La première date est plus tôt que la deuxième.")
} else {
    print("La première date est plus tard que la deuxième.")
}
```

Sample Output:

```
La première date est plus tôt que la deuxième.
La première date est plus tôt que la deuxième.
```

## Deep Dive (Plongée en Profondeur)

Historiquement, Swift a hérité de la gestion de la date et de l'heure de Cocoa et Objective-C, où `NSDate` était omniprésent. Dans Swift, `NSDate` est devenu `Date` et a été amélioré avec des fonctionnalités de comparaison intuitives. 

Outre `Date`, le framework Foundation offre `Calendar` pour des comparaisons plus complexes, par exemple, trouver la différence entre deux dates avec des composants comme les mois ou les jours. Il y a aussi la classe `DateComponents`, qui permet de travailler avec des parties spécifiques d'une date.

En considérant les détails d'implémentation, il faut être prudent avec les fuseaux horaires et les calendriers lors de la comparaison des dates, car cela peut affecter le résultat.

## See Also (Voir Aussi)

- [Apple Documentation on Date](https://developer.apple.com/documentation/foundation/date)
