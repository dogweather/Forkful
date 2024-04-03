---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:41.318032-07:00
description: "\xC5 sjekke om en katalog eksisterer i filsystemet er essensielt for\
  \ \xE5 h\xE5ndtere filstrukturer fra dine Swift-applikasjoner. Denne oppgaven gj\xF8\
  r det mulig for\u2026"
lastmod: '2024-03-13T22:44:41.156287-06:00'
model: gpt-4-0125-preview
summary: "\xC5 sjekke om en katalog eksisterer i filsystemet er essensielt for \xE5\
  \ h\xE5ndtere filstrukturer fra dine Swift-applikasjoner."
title: Sjekker om en mappe eksisterer
weight: 20
---

## Hvordan:
Swifts Foundation-rammeverk tilbyr `FileManager`-klassen, som har metoder for å håndtere filsystemet. Du kan bruke `FileManager` for å sjekke om en katalog eksisterer. Her er et kodeutdrag om hvordan du gjør dette:

```swift
import Foundation

let fileManager = FileManager.default
let path = "/sti/til/din/katalog"

if fileManager.fileExists(atPath: path, isDirectory: nil) {
    print("Katalogen eksisterer")
} else {
    print("Katalogen eksisterer ikke")
}
```

Men, dette sjekker for både filer og kataloger. Hvis du spesifikt ønsker å verifisere at en katalog eksisterer, må du sende en peker til en Boolesk verdi i `isDirectory`:

```swift
import Foundation

let fileManager = FileManager.default
let path = "/sti/til/din/katalog"
var isDirectory: ObjCBool = false

if fileManager.fileExists(atPath: path, isDirectory: &isDirectory), isDirectory.boolValue {
    print("Katalogen eksisterer")
} else {
    print("Katalogen eksisterer ikke")
}
```

### Bruke et tredjepartsbibliotek
Per nå krever vanligvis ikke sjekking for eksistensen av en katalog i Swift tredjepartsbiblioteker på grunn av robustheten til `FileManager`-klassen. Men, for mer kompleks filmanipulasjon og sjekking, tilbyr biblioteker som **Files** av John Sundell en mer Swift-vennlig API.

Slik kan du bruke det:

Først, legg til Files i prosjektet ditt via Swift Package Manager.

Deretter kan du sjekke for eksistensen av en katalog slik:

```swift
import Files

do {
    _ = try Folder(path: "/sti/til/din/katalog")
    print("Katalogen eksisterer")
} catch {
    print("Katalogen eksisterer ikke")
}
```

Merk: Siden tredjepartsbiblioteker kan endres, referer alltid til den nyeste dokumentasjonen for bruk og beste praksiser.
