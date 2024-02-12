---
title:                "Arbeiten mit CSV"
aliases:
- /de/swift/working-with-csv/
date:                  2024-02-03T19:21:32.422500-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeiten mit CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/swift/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?

Die Arbeit mit CSV-Dateien (Comma-Separated Values, Werte getrennt durch Kommas) beinhaltet das Parsen und Generieren strukturierter Daten aus Textdateien, bei denen jede Zeile einen Datensatz repräsentiert und jeder Datensatz aus durch Kommas getrennten Feldern besteht. Programmierer beschäftigen sich oft mit dieser Tätigkeit, um tabellarische Daten leicht zu importieren, exportieren und zu manipulieren, da das Format aufgrund seiner Einfachheit und Lesbarkeit plattform- und sprachenübergreifend breit unterstützt wird.

## Wie:

In Swift gibt es keine native Unterstützung für das direkte Parsen von CSV-Dateien, aber man kann CSV-Daten verarbeiten, indem man die `String`-Methoden zum Teilen der Inhalte verwendet oder auf Drittanbieter-Bibliotheken wie SwiftCSV für einen einfacheren Ansatz zurückgreift. Hier sind beide Methoden:

### Manuelles Parsen ohne externe Bibliotheken
```swift
// Betrachten Sie einen einfachen CSV-String
let csvString = """
name,age,city
John Doe,29,New York
Jane Smith,34,Los Angeles
"""

// Teilen Sie den CSV-String in Zeilen
let rows = csvString.components(separatedBy: "\n")

// Extrahieren Sie die Schlüssel aus der ersten Zeile
let keys = rows.first?.components(separatedBy: ",")

// Iterieren Sie über die Zeilen, beginnend mit der zweiten
var result: [[String: String]] = []
for row in rows.dropFirst() {
    let values = row.components(separatedBy: ",")
    let dict = Dictionary(uniqueKeysWithValues: zip(keys!, values))
    result.append(dict)
}

// Beispiel-Ausgabe
print(result)
// Gibt aus: [{"city": "New York", "age": "29", "name": "John Doe"}, {"city": "Los Angeles", "age": "34", "name": "Jane Smith"}]
```
Dieser Ansatz ist unkompliziert, mangelt es jedoch an Robustheit, besonders bei CSV-Dateien, die Spezialfälle wie Kommas in Werten, Zeilenumbrüche innerhalb von Feldern usw. enthalten.

### Verwendung der SwiftCSV-Bibliothek
Fügen Sie zuerst SwiftCSV Ihrem Projekt hinzu, indem Sie es in Ihre `Package.swift`-Abhängigkeiten einschließen:
```swift
.package(url: "https://github.com/swiftcsv/SwiftCSV.git", from: "0.5.6")
```
Dann importieren und verwenden Sie es wie folgt:
```swift
import SwiftCSV

// Nehmen Sie an, `csvString` ist wie oben definiert

// Erstellen Sie ein CSV-Objekt
if let csv = try? CSV(string: csvString) {
    // Greifen Sie auf die Zeilen als Wörterbücher zu
    let rows = csv.namedRows
    
    // Beispiel-Ausgabe
    print(rows)
    // Gibt aus: [{"city": "New York", "age": "29", "name": "John Doe"}, {"city": "Los Angeles", "age": "34", "name": "Jane Smith"}]
}
```
SwiftCSV vereinfacht das Parsen, indem es automatisch mit Nuancen wie eingekapselten Kommas, Zeilenumbrüchen in Feldern und Zeichenkodierungen umgeht. Denken Sie jedoch daran, mögliche Fehler in realen Anwendungen zu behandeln, insbesondere beim Umgang mit externen Datenquellen.
