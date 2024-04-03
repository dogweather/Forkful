---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:15:58.798542-07:00
description: "\xC5 analysere en dato fra en streng inneb\xE6rer \xE5 konvertere tekstuelle\
  \ dato- og tidsrepresentasjoner til et `Date`-objekt. Denne prosessen er essensiell\
  \ i\u2026"
lastmod: '2024-03-13T22:44:41.151551-06:00'
model: gpt-4-0125-preview
summary: "\xC5 analysere en dato fra en streng inneb\xE6rer \xE5 konvertere tekstuelle\
  \ dato- og tidsrepresentasjoner til et `Date`-objekt."
title: Analysering av en dato fra en streng
weight: 30
---

## Hvordan:


### Bruke Foundation's `DateFormatter`
Swifts standardbibliotek, Foundation, tilbyr `DateFormatter` for å konvertere strenger til `Date`-objekter og omvendt. For å analysere en dato fra en streng, spesifiserer du datoformatet som matcher strengen, deretter bruker du formatteren til å analysere det.

```swift
import Foundation

let dateString = "2023-04-30"
let formatter = DateFormatter()
formatter.dateFormat = "yyyy-MM-dd"
if let date = formatter.date(from: dateString) {
    print("Analysert dato: \(date)")
} else {
    print("Klarte ikke å analysere dato")
}
// Eksempelutdata: Analysert dato: 2023-04-29 22:00:00 +0000
```

Merk at utdata kan variere basert på din tidssone.

### Bruke ISO8601DateFormatter
For ISO 8601 datoformater, tilbyr Swift en spesialisert formatter, `ISO8601DateFormatter`, som forenkler analyseringsprosessen.

```swift
import Foundation

let dateString = "2023-04-30T15:00:00+00:00"
let isoFormatter = ISO8601DateFormatter()
if let date = isoFormatter.date(from: dateString) {
    print("Analysert ISO8601 dato: \(date)")
} else {
    print("Klarte ikke å analysere ISO8601 dato")
}
// Eksempelutdata: Analysert ISO8601 dato: 2023-04-30 15:00:00 +0000
```

### Bruke et tredjepartsbibliotek: SwiftDate
Selv om Swift tilbyr robuste verktøy for datumsanalyse, tilbyr tredjepartsbiblioteker som SwiftDate enda mer fleksibilitet og bekvemmelighet. Etter å ha lagt til SwiftDate i prosjektet ditt, blir parsing så enkel som:

```swift
import SwiftDate

let dateString = "April 30, 2023"
if let date = dateString.toDate("MMMM dd, yyyy") {
    print("Analysert dato med SwiftDate: \(date)")
} else {
    print("Klarte ikke å analysere dato med SwiftDate")
}
// Eksempelutdata: Analysert dato med SwiftDate: 2023-04-30 00:00:00 +0000
```

SwiftDate forenkler parsing med naturlig språk og et bredt utvalg av datoformater, noe som gjør det til en kraftig tillegg til ditt Swift programmeringsverktøysett.
