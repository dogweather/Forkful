---
date: 2024-01-20 17:38:43.396336-07:00
description: "Ein String in Kleinbuchstaben umzuwandeln, bedeutet, jeden Gro\xDFbuchstaben\
  \ in seinem \xC4quivalent in Kleinbuchstaben zu \xE4ndern. Programmierer nutzen\
  \ das, um\u2026"
lastmod: '2024-03-13T22:44:54.253430-06:00'
model: gpt-4-1106-preview
summary: "Ein String in Kleinbuchstaben umzuwandeln, bedeutet, jeden Gro\xDFbuchstaben\
  \ in seinem \xC4quivalent in Kleinbuchstaben zu \xE4ndern."
title: Umformung eines Strings in Kleinbuchstaben
weight: 4
---

## How to: (Wie geht das?)
In JavaScript wandelt die Funktion `toLowerCase()` eines String-Objekts den gesamten Text in Kleinbuchstaben um. Hier ist es in Aktion:

```javascript
let greeting = "Hallo Welt!";
let lowerCaseGreeting = greeting.toLowerCase();

console.log(lowerCaseGreeting); // "hallo welt!"
```

Ganz einfach, richtig? Der Output ist ein kleingeschriebener Text, egal, wie der ursprüngliche String aussieht.

## Deep Dive (Tiefer eintauchen)
Die Funktion `toLowerCase()` gibt es schon eine Weile und spielt seit langem eine wichtige Rolle bei Textverarbeitung und -vergleich. Historisch gesehen verhindert diese Funktionalität Probleme mit der Groß- und Kleinschreibung und ist besonders nützlich bei der Suchfunktionalität in Datenbanken und Webanwendungen.

### Alternativen
Es gibt auch die Funktion `toLocaleLowerCase()`, die ähnlich wirkt, aber Besonderheiten bezüglich der länderspezifischen Buchstaben berücksichtigt – zum Beispiel das deutsche "ß":

```javascript
let germanText = "Straße";
console.log(germanText.toLowerCase()); // "straße"
console.log(germanText.toLocaleLowerCase('de-DE')); // "straße"
```

### Implementierungsdetails
`toLowerCase()` durchläuft jeden Buchstaben im String und prüft dessen Unicode-Wert. Wenn der Buchstabe ein Großbuchstabe ist, wird er basierend auf den Unicode-Regeln in den entsprechenden Kleinbuchstaben umgewandelt.

## See Also (Siehe auch)
- MDN Web Docs für `toLowerCase()`: https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase
- Unicode-Standard: https://unicode.org/
- JavaScript Equality Table für Stringvergleiche: https://dorey.github.io/JavaScript-Equality-Table/
