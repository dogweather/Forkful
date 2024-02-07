---
title:                "Einen Datum aus einem String analysieren"
date:                  2024-02-03T19:15:33.684292-07:00
model:                 gpt-4-0125-preview
simple_title:         "Einen Datum aus einem String analysieren"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/swift/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Das Parsen eines Datums aus einem String umfasst die Umwandlung von textuellen Datums- und Zeitangaben in ein `Date`-Objekt. Dieser Prozess ist essenziell in Anwendungen, in denen Daten als Strings kommuniziert werden, wie bei API-Antworten oder Benutzereingaben. Dadurch wird die Manipulation und Formatierung von Daten erleichtert.

## Wie geht das:

### Verwendung von Foundations `DateFormatter`
Die Standardbibliothek von Swift, Foundation, bietet `DateFormatter` für die Umwandlung von Strings in `Date`-Objekte und umgekehrt. Um ein Datum aus einem String zu parsen, gibt man das Datumsformat an, das dem String entspricht, und verwendet dann den Formatter für das Parsen.

```swift
import Foundation

let dateString = "2023-04-30"
let formatter = DateFormatter()
formatter.dateFormat = "yyyy-MM-dd"
if let date = formatter.date(from: dateString) {
    print("Geparstes Datum: \(date)")
} else {
    print("Datum konnte nicht geparsed werden")
}
// Beispiel-Ausgabe: Geparstes Datum: 2023-04-29 22:00:00 +0000
```

Beachten Sie, dass die Ausgabe je nach Ihrer Zeitzone variieren kann.

### Verwendung von ISO8601DateFormatter
Für ISO 8601 Datumsformate bietet Swift einen spezialisierten Formatter, `ISO8601DateFormatter`, der den Parsing-Prozess vereinfacht.

```swift
import Foundation

let dateString = "2023-04-30T15:00:00+00:00"
let isoFormatter = ISO8601DateFormatter()
if let date = isoFormatter.date(from: dateString) {
    print("Geparstes ISO8601 Datum: \(date)")
} else {
    print("ISO8601 Datum konnte nicht geparsed werden")
}
// Beispiel-Ausgabe: Geparstes ISO8601 Datum: 2023-04-30 15:00:00 +0000
```

### Verwendung einer Drittanbieter-Bibliothek: SwiftDate
Während Swift robuste Werkzeuge für das Parsen von Daten bietet, bieten Drittanbieter-Bibliotheken wie SwiftDate noch mehr Flexibilität und Komfort. Nachdem Sie SwiftDate zu Ihrem Projekt hinzugefügt haben, wird das Parsen so einfach wie:

```swift
import SwiftDate

let dateString = "April 30, 2023"
if let date = dateString.toDate("MMMM dd, yyyy") {
    print("Mit SwiftDate geparstes Datum: \(date)")
} else {
    print("Datum konnte mit SwiftDate nicht geparsed werden")
}
// Beispiel-Ausgabe: Mit SwiftDate geparstes Datum: 2023-04-30 00:00:00 +0000
```

SwiftDate vereinfacht das Parsen mit natürlicher Sprache und einer breiten Palette von Datumsformaten und ist damit eine leistungsstarke Ergänzung für Ihr Swift-Programmierwerkzeugset.
