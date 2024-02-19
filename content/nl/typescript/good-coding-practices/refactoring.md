---
aliases:
- /nl/typescript/refactoring/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:05:56.147417-07:00
description: "Refactoring is het proces van het herstructureren van bestaande computercode\
  \ zonder het externe gedrag ervan te veranderen. Programmeurs doen dit om de\u2026"
lastmod: 2024-02-18 23:09:01.582361
model: gpt-4-0125-preview
summary: "Refactoring is het proces van het herstructureren van bestaande computercode\
  \ zonder het externe gedrag ervan te veranderen. Programmeurs doen dit om de\u2026"
title: Refactoring
---

{{< edit_this_page >}}

## Wat & Waarom?
Refactoring is het proces van het herstructureren van bestaande computercode zonder het externe gedrag ervan te veranderen. Programmeurs doen dit om de code schoner, onderhoudbaarder te maken en de complexiteit te verminderen, wat het gemakkelijker maakt om te begrijpen voor iemand die nieuw is.

## Hoe te:
Beschouw een TypeScript-functie die betere tijden heeft gekend - het is een beetje een rommeltje en kan wat liefde en zorg gebruiken:

```typescript
function userInfo(data: any): string {
    return "User Info: " + data.name + ", " + data.age + ", " + data.email + ";" ;
}
```
Gerefactord, kan dit er zo uitzien:

```typescript
interface User {
    name: string;
    age: number;
    email: string;
}

function formatUserInfo(user: User): string {
    return `User Info: ${user.name}, ${user.age}, ${user.email};`;
}
```

Het tweede voorbeeld is robuuster, maakt gebruik van TypeScript's type systeem met een `interface` om potentiële runtimefouten te voorkomen en de leesbaarheid te verbeteren.

## Diepgaand
Refactoring is geen modern concept; het evolueerde met programmeren, en werd meer geformaliseerd met de uitgave van Martin Fowler's boek "Refactoring: Improving the Design of Existing Code" in 1999. Het is cruciaal in een Agile ontwikkelomgeving, waarbij het adaptieve codewijzigingen vergemakkelijkt. Enkele alternatieven voor handmatige refactoring zijn geautomatiseerde tools zoals TSLint of TypeScript's eigen taalserver die bepaalde refactoringtaken voor je kan suggereren of zelfs uitvoeren. Implementatiedetails omvatten meestal het herkennen van "codegeuren", zoals dubbele code, lange methoden of grote klassen, en het toepassen van patronen om te verhelpen - zoals het extraheren van methoden, verplaatsen naar meer geschikte klassen of het gebruik van eenvoudigere constructies. Deze patronen zijn de sleutel tot het begrijpen van het hoe en waarom van refactoring.

## Zie Ook
- [Het boek "Refactoring: Improving the Design of Existing Code" door Martin Fowler](https://martinfowler.com/books/refactoring.html)
- [TSLint voor statische codeanalyse](https://palantir.github.io/tslint/)
- [Codegeuren Begrijpen](https://refactoring.guru/refactoring/smells)
