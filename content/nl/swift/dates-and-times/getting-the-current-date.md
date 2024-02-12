---
title:                "Het huidige datum ophalen"
aliases:
- /nl/swift/getting-the-current-date/
date:                  2024-01-28T22:01:12.317199-07:00
model:                 gpt-4-0125-preview
simple_title:         "Het huidige datum ophalen"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/swift/getting-the-current-date.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

In Swift houdt het verkrijgen van de huidige datum in dat je toegang krijgt tot de huidige tijd- en datuminstellingen van het systeem. Programmeurs doen dit om gebeurtenissen van een tijdstempel te voorzien, taken te plannen, of gewoon de datum en tijd in hun apps weer te geven.

## Hoe:

Het verkrijgen van de huidige datum en tijd in Swift is eenvoudig:

```Swift
import Foundation

let currentDate = Date()
print(currentDate)
```
Voorbeelduitvoer:
```
2023-04-10 16:20:32 +0000
```
Als je een specifiek formaat wilt:

```Swift
import Foundation

let formatter = DateFormatter()
formatter.dateFormat = "yyyy-MM-dd HH:mm:ss"
let formattedDate = formatter.string(from: Date())
print(formattedDate)
```
Voorbeelduitvoer:
```
2023-04-10 16:20:32
```

## Diepgaande Beschouwing

De `Date` struct in Swift maakt deel uit van het Foundation framework, dat afkomstig is van Objective-C's `NSDate`. In de loop van de tijd heeft Swift een moderne benadering geleverd met `Date` die expressiever en veiliger is.

Er zijn alternatieven voor `Date()` om de huidige tijd te verkrijgen. Bijvoorbeeld, `NSDate()`, dat ongeveer hetzelfde is maar minder Swift-vriendelijk, en APIs op een lager niveau, zoals `gettimeofday()`, voor het verkrijgen van preciezere systeemtijd. Maar, `Date()` is de eerste keus voor de meeste Swift-ontwikkelaars omdat het gebruiksgemak combineert met voldoende precisie voor typische gebruiksscenario's.

`Date()` in Swift verkrijgt systeemtijd, die vaak in Gecoördineerde Universele Tijd (UTC) is. Dus wanneer je het direct afdrukt zonder een formaat, verschijnt het met een UTC-afwijking. Daarom zijn formatters populair; ze passen de datum en tijd aan een gespecificeerde tijdzone en formaat aan, waardoor het op het scherm mensvriendelijk wordt weergegeven. Je eigen tijdzoneaanpassingen implementeren zonder formatters is mogelijk, maar is het opnieuw uitvinden van het wiel en vatbaar voor fouten vanwege veranderingen in de zomertijd en schrikkelseconden.

## Zie Ook
- De officiële `Date` documentatie van Apple: [Date - Apple Developer Documentation](https://developer.apple.com/documentation/foundation/date)
- DateFormatter gids: [DateFormatter - Apple Developer Documentation](https://developer.apple.com/documentation/foundation/dateformatter)
- Voor diepgaandere inzichten in datum en tijd in computersystemen, bekijk [de video van Computerphile op YouTube](https://www.youtube.com/watch?v=-5wpm-gesOY).
