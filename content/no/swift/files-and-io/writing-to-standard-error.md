---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:49.154571-07:00
description: "Skriving til standardfeil (stderr) handler om \xE5 lede programmets\
  \ feilmeldinger eller diagnostiske utdata til en separat str\xF8m, forskjellig fra\u2026"
lastmod: '2024-03-13T22:44:41.158340-06:00'
model: gpt-4-0125-preview
summary: "Skriving til standardfeil (stderr) handler om \xE5 lede programmets feilmeldinger\
  \ eller diagnostiske utdata til en separat str\xF8m, forskjellig fra standardutdata\
  \ (stdout)."
title: Skriving til standardfeil
weight: 25
---

## Hvordan:
I Swift kan skriving til standardfeil gjøres ved å bruke `FileHandle`-klassen for direkte tilgang til stderr. Her er et enkelt eksempel:

```swift
import Foundation

// Definer en melding
let errorMessage = "En feil oppstod.\n"

// Konverter meldingen til data
if let data = errorMessage.data(using: .utf8) {
    // Skriv feilmeldingen til stderr
    FileHandle.standardError.write(data)
}
```

Utdata til stderr (vanligvis sett i en konsoll eller terminal):
```
En feil oppstod.
```

For mer kompleks logging eller når du jobber med eksterne biblioteker, kan man vurdere å bruke et tredjepartsbibliotek som **SwiftLog**. Selv om **SwiftLog** ikke skriver til stderr direkte ut av boksen, kan du implementere et tilpasset loggingsbakstykke for å oppnå dette. Her er et forenklet eksempel på å definere en tilpasset logghandler som skriver til stderr:

Først, legg til **SwiftLog** i prosjektets avhengigheter i `Package.swift`:
```swift
// swift-tools-version:5.3

import PackageDescription

let package = Package(
    name: "DittPakkeNavn",
    dependencies: [
        .package(url: "https://github.com/apple/swift-log.git", from: "1.0.0"),
    ],
    targets: [
        .target(
            name: "DittMålNavn",
            dependencies: [
                .product(name: "Logging", package: "swift-log"),
            ]),
    ]
)
```

Deretter, implementer en tilpasset logghandler som skriver til stderr:

```swift
import Logging
import Foundation

struct StderrLogHandler: LogHandler {
    let label: String
    
    var logLevel: Logger.Level = .info
    
    func log(level: Logger.Level, message: Logger.Message, metadata: Logger.Metadata?, source: String, file: String, function: String, line: UInt) {
        let output = "\(message)\n"
        if let data = output.data(using: .utf8) {
            FileHandle.standardError.write(data)
        }
    }
    
    subscript(metadataKey metadataKey: String) -> Logger.Metadata.Value? {
        get { return nil }
        set(newValue) { }
    }
    
    var metadata: Logger.Metadata {
        get { return [:] }
        set(newMetadata) { }
    }
}

// Bruk
LoggingSystem.bootstrap(StderrLogHandler.init)
let logger = Logger(label: "com.example.dittapp")

logger.error("Dette er en feilmelding")
```

Utdata til stderr:
```
Dette er en feilmelding
```

Denne tilpassede handleren lar deg rute dine SwiftLog-feilmeldinger direkte til standardfeil, og integrerer sømløst med andre loggmeldinger applikasjonen din kan generere.
