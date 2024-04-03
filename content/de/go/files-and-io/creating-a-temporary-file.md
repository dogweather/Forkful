---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:55:11.086599-07:00
description: "Das Erstellen einer tempor\xE4ren Datei in Go erm\xF6glicht die Generierung\
  \ einer nicht-persistenten Datei, die f\xFCr den kurzfristigen Gebrauch bestimmt\
  \ ist,\u2026"
lastmod: '2024-03-13T22:44:53.309004-06:00'
model: gpt-4-0125-preview
summary: "Das Erstellen einer tempor\xE4ren Datei in Go erm\xF6glicht die Generierung\
  \ einer nicht-persistenten Datei, die f\xFCr den kurzfristigen Gebrauch bestimmt\
  \ ist, haupts\xE4chlich f\xFCr Aufgaben wie das Speichern von Zwischendaten oder\
  \ die Unterst\xFCtzung bei Batch-Verarbeitungs-Jobs."
title: "Erstellung einer tempor\xE4ren Datei"
weight: 21
---

## Wie:
In Go bot das `ioutil` Paket ursprünglich Hilfsmittel zur Erstellung von temporären Dateien. Doch ab Go 1.16 wurde die Benutzung der Funktionen der `os` und `io/ioutil` Pakete in besser organisierte Bereiche gefördert. Jetzt werden die `os` und `io` Pakete bevorzugt behandelt, um mit temporären Dateien umzugehen.

Hier ist eine Schritt-für-Schritt-Anleitung zur Erstellung, Beschreibung und Löschung einer temporären Datei:

1. **Erstellen einer temporären Datei:**

Mit der Funktion `os.CreateTemp` können Sie eine temporäre Datei erstellen. Ohne Angabe eines Verzeichnisses verwendet es den Standard-Temp-Ordner Ihres Betriebssystems.

```go
package main

import (
    "io/ioutil"
    "log"
    "os"
)

func main() {
    tmpFile, err := ioutil.TempFile("", "Beispiel.*.txt")
    if err != nil {
        log.Fatal(err)
    }
    log.Printf("Temporäre Datei erstellt: %s\n", tmpFile.Name())

    defer os.Remove(tmpFile.Name()) // Aufräumen
}
```

2. **In die temporäre Datei schreiben:**

Das Schreiben in die Datei kann mit der `Write` Methode oder anderen Schreibfunktionen aus den `io` oder `bufio` Paketen erreicht werden.

```go
_, err = tmpFile.Write([]byte("Hallo, Welt!"))
if err != nil {
    log.Fatal(err)
}
```

3. **Aus der temporären Datei lesen:**

Das Lesen erfolgt ähnlich, indem die `Read` Methode der Datei oder Hilfsmittel aus den `io` oder `bufio` Paketen verwendet werden.

```go
data, err := ioutil.ReadFile(tmpFile.Name())
if err != nil {
    log.Fatal(err)
}
log.Printf("Gelesene Daten: %s\n", string(data))
```

4. **Die temporäre Datei löschen:**

Während die Anweisung `defer os.Remove(tmpFile.Name())` in der Erstellungsphase sicherstellt, dass die temporäre Datei nach Beendigung des Programms gelöscht wird, kann die explizite Löschung nach Bedarf verwaltet werden.

Beispielausgabe:
```
2023/04/01 15:00:00 Temporäre Datei erstellt: /tmp/Beispiel.123456.txt
2023/04/01 15:00:00 Gelesene Daten: Hallo, Welt!
```

## Vertiefung
Der Mechanismus hinter der Handhabung von temporären Dateien in Go hat sich entwickelt. Ursprünglich wurde das Erstellen von temporären Dateien überwiegend durch die jetzt veraltete Funktion `ioutil.TempFile` verwaltet, was breitere Trends in der Softwareentwicklung hin zu sichereren und effizienteren Dateiverarbeitungspraktiken widerspiegelt. Der Übergang, diese Funktionalitäten in die `os` und `io` Pakete mit Go 1.16 zu integrieren, signalisiert einen breiteren Schub zur Straffung der Standardbibliothek der Sprache und fördert die Verwendung von einheitlicheren und kohäsiveren APIs.

Während die Verwendung von temporären Dateien eine gängige und oft wesentliche Praxis in der Programmierung ist, ist es wichtig zu beachten, dass sich zu stark auf sie zu verlassen, um große Datenmengen zu speichern oder für langfristige Aufgaben, zu Leistungsproblemen führen kann. Darüber hinaus können, wenn die Erstellung von temporären Dateien nicht streng kontrolliert wird oder wenn sie nicht adäquat aufgeräumt werden, Ressourcenlecks entstehen, die das Dateisystem negativ beeinträchtigen könnten. In Szenarien, die eine persistente Speicherung erfordern oder die Verarbeitung erheblicher Datenströme beinhalten, bieten Alternativen wie Datenbanken oder im Speicher befindliche Datenspeicher oft eine bessere Leistung und Zuverlässigkeit im Vergleich zu temporären Dateien.
