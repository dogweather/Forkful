---
title:                "Beregning av en dato i fremtiden eller fortiden"
date:                  2024-01-20T17:32:11.584586-07:00
model:                 gpt-4-1106-preview
simple_title:         "Beregning av en dato i fremtiden eller fortiden"
programming_language: "Swift"
category:             "Swift"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/swift/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Regne ut en fremtidig eller fortidig dato betyr å beregne en dato før eller etter et bestemt startpunkt. Programmerere gjør dette for å håndtere tidsbestemte funksjoner som gjentagende hendelser, frister eller tidsfrister.

## Slik Gjør Du:
```Swift
import Foundation

// I dagens dato
let iDag = Date()

// Kalenderen vi bruker
let kalender = Calendar.current

// Legger til 5 dager til dagens dato
if let omFemDager = kalender.date(byAdding: .day, value: 5, to: iDag) {
    print("Om fem dager er det: \(omFemDager)")
}

// Trekker fra 3 uker fra dagens dato
if let forTreUkerSiden = kalender.date(byAdding: .weekOfYear, value: -3, to: iDag) {
    print("For tre uker siden var det: \(forTreUkerSiden)")
}
```

Forventet output vil være datoer for fem dager frem og tre uker tilbake, basert på dagens dato.

## Dypdykk
Dato- og tidsberegninger er fundamentale i mange apps, som kalendere eller påminnelsesprogrammer. Swifts `Date` og `Calendar` klasser kommer fra Foundation-rammeverket og viser en evolusjon fra de enklere tidshåndteringssystemene som var tilgjengelige i tidlige programmeringsspråk. Alternativer inkluderer tredjeparts biblioteker som `SwiftDate`, som ofte har mer funksjonalitet, men `Foundation` tilbyr det som trengs for de fleste basisbehov.

For å kalkulere fremtidige og fortidige datoer bruker vi `Calendar` klassens metoder som `date(byAdding:value:to:)`, som er kraftfull men også enkel i bruk. Denne funksjonaliteten håndterer forskjellige tidsenheter og tar hensyn til utfordringer som skuddår og tidsendringer som sommertid.

## Se Også
- Swift dokumentasjon for [Date](https://developer.apple.com/documentation/foundation/date)
- Swift dokumentasjon for [Calendar](https://developer.apple.com/documentation/foundation/calendar)