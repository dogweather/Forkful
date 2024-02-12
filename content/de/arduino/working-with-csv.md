---
title:                "Arbeiten mit CSV"
aliases:
- de/arduino/working-with-csv.md
date:                  2024-02-03T19:18:52.500058-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeiten mit CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/arduino/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Arbeiten mit CSV (Comma-Separated Values)-Dateien in Arduino umfasst das Lesen von und Schreiben in CSV-Dateien, die üblicherweise auf einer SD-Karte gespeichert sind. Dies ermöglicht Datenaufzeichnung, Konfigurationseinstellungen und mehr. Programmierer bearbeiten oft CSV-Dateien für die Sammlung von Sensordaten, Speicherung von Konfigurationsparametern oder das Interface mit anderen Systemen, aufgrund ihrer Einfachheit und weiten Verbreitung über Plattformen hinweg.

## Wie:
Arduino besitzt keine integrierte Bibliothek speziell für den Umgang mit CSV-Dateien, aber man kann die `SD`- und `SPI`-Bibliotheken verwenden, um auf Dateien auf einer SD-Karte zuzugreifen, und dann CSV-Daten mithilfe grundlegender String-Manipulationstechniken parsen oder generieren. Bei der Verarbeitung komplexerer CSV-Manipulationen kann die Drittanbieterbibliothek `ArduinoCSV` für einfacheres Parsen und Schreiben genutzt werden.

**Lesen von CSV-Daten von einer SD-Karte:**
```cpp
#include <SPI.h>
#include <SD.h>

void setup() {
  Serial.begin(9600);
  if (!SD.begin(4)) {
    Serial.println("Initialisierung fehlgeschlagen!");
    return;
  }
  File dataFile = SD.open("data.csv");
  if (dataFile) {
    while (dataFile.available()) {
      String dataLine = dataFile.readStringUntil('\n');
      Serial.println(dataLine); // Gibt die CSV-Zeile aus
    }
    dataFile.close();
  } else {
    Serial.println("Fehler beim Öffnen von data.csv");
  }
}

void loop() {
  // Wird in diesem Beispiel nicht verwendet
}
```
*Beispielausgabe:*
```
SensorID, Timestamp, Wert
1, 1597840923, 23.5
2, 1597840987, 22.4
```

**Schreiben von CSV-Daten auf eine SD-Karte:**
```cpp
#include <SPI.h>
#include <SD.h>

void setup() {
  Serial.begin(9600);
  if (!SD.begin(4)) {
    Serial.println("Initialisierung fehlgeschlagen!");
    return;
  }
  File dataFile = SD.open("output.csv", FILE_WRITE);
  if (dataFile) {
    dataFile.println("SensorID, Timestamp, Wert"); // CSV-Header
    dataFile.println("1, 1597840923, 23.5"); // Beispieldatenzeile
    dataFile.close();
    Serial.println("Daten geschrieben");
  } else {
    Serial.println("Fehler beim Öffnen von output.csv");
  }
}

void loop() {
  // Wird in diesem Beispiel nicht verwendet
}
```
*Beispielausgabe:*
```
Daten geschrieben
```

**Verwendung von ArduinoCSV zum Parsen:**
Falls man sich mit komplexen CSV-Dateien beschäftigt, kann die `ArduinoCSV`-Bibliothek das Parsen erheblich vereinfachen. Dieses Beispiel setzt voraus, dass die `ArduinoCSV`-Bibliothek bereits installiert ist.

```cpp
#include <SPI.h>
#include <SD.h>
#include <ArduinoCSV.h>

void setup() {
  Serial.begin(9600);
  if (!SD.begin(4)) {
    Serial.println("Initialisierung fehlgeschlagen!");
    return;
  }
  File dataFile = SD.open("data.csv");
  if (dataFile) {
    CSVParser parser;
    while (dataFile.available()) {
      String dataLine = dataFile.readStringUntil('\n');
      if (parser.parseLine(dataLine)) {
        for (int i = 0; i < parser.count(); i++) {
          Serial.print(parser.getField(i)); // Druckt jedes Feld
          if (i < parser.count() - 1) {
            Serial.print(", ");
          }
        }
        Serial.println();
      }
    }
    dataFile.close();
  } else {
    Serial.println("Fehler beim Öffnen von data.csv");
  }
}

void loop() {
  // Wird in diesem Beispiel nicht verwendet
}
```
*Beispielausgabe:*
```
SensorID,  Timestamp,  Wert
1,  1597840923,  23.5
2,  1597840987,  22.4
```
In diesen Beispielen können Arduino-Projekte durch das Lesen von und Schreiben in CSV-Dateien auf einer SD-Karte einfach Daten sammeln, Konfigurationseinstellungen speichern oder Daten mit anderen Anwendungen in einem universell zugänglichen Format austauschen.
