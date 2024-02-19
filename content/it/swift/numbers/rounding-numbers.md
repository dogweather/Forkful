---
aliases:
- /it/swift/rounding-numbers/
date: 2024-01-26 03:46:52.871494-07:00
description: "Arrotondare i numeri significa approssimare un valore numerico a una\
  \ precisione specifica, tipicamente per rimuovere decimali indesiderati. I\u2026"
lastmod: 2024-02-18 23:08:56.207857
model: gpt-4-0125-preview
summary: "Arrotondare i numeri significa approssimare un valore numerico a una precisione\
  \ specifica, tipicamente per rimuovere decimali indesiderati. I\u2026"
title: Arrotondamento dei numeri
---

{{< edit_this_page >}}

## Cosa & Perché?

Arrotondare i numeri significa approssimare un valore numerico a una precisione specifica, tipicamente per rimuovere decimali indesiderati. I programmatori arrotondano per gestire la memoria, migliorare la leggibilità e soddisfare requisiti specifici del dominio come vincoli di valuta.

## Come fare:

Swift offre diversi modi per arrotondare i numeri. Ecco un assaggio:

```Swift
let original = 3.14159

// Arrotondamento standard
let standardRounded = round(original) // 3.0

// Arrotondamento a un punto decimale specifico
let decimalRounded = Double(round(original * 1000) / 1000) // 3.142

// Arrotondamento verso il basso
let roundedDown = floor(original) // 3.0

// Arrotondamento verso l'alto
let roundedUp = ceil(original) // 4.0

print("Standard: \(standardRounded), Decimale: \(decimalRounded), Verso il basso: \(roundedDown), Verso l'alto: \(roundedUp)")
```

Output: `Standard: 3.0, Decimale: 3.142, Verso il basso: 3.0, Verso l'alto: 4.0`

## Approfondimento

Storicamente, l'arrotondamento è un concetto matematico che precede i computer, essenziale nel commercio e nella scienza. Il framework `Foundation` di Swift offre una funzionalità di arrotondamento completa:

- `round(_: )` è il buon vecchio arrotondamento a metà verso l'alto.
- `floor(_: )` e `ceil(_: )` gestiscono l'arrotondamento direzionale.
- `rounded(.up/.down/.toNearestOrAwayFromZero)` offre un controllo più fine con l'enum delle regole di arrotondamento.

Sii consapevole del tipo `Decimal` per calcoli finanziari precisi, il quale evita errori di virgola mobile. Esplora anche `NSDecimalNumber` per la compatibilità con Objective-C.

## Vedi Anche

- Standard IEEE per l'aritmetica in virgola mobile (IEEE 754): [IEEE 754](https://ieeexplore.ieee.org/document/4610935)
