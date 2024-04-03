---
date: 2024-01-20 17:41:34.124319-07:00
description: "Midlertidige filer er som engangsbestikk for data \u2013 de brukes litt,\
  \ og s\xE5 forsvinner de. Programmerere bruker dem for \xE5 lagre midlertidig data\
  \ som ikke\u2026"
lastmod: '2024-03-13T22:44:41.161189-06:00'
model: gpt-4-1106-preview
summary: "Midlertidige filer er som engangsbestikk for data \u2013 de brukes litt,\
  \ og s\xE5 forsvinner de."
title: Opprette en midlertidig fil
weight: 21
---

## How to:
Lag en midlertidig fil med Swift slik:

```Swift
import Foundation

let tempDirectoryURL = FileManager.default.temporaryDirectory
let tempFileURL = tempDirectoryURL.appendingPathComponent(UUID().uuidString)

do {
    let exampleData = "Hei! Dette er en midlertidig fil".data(using: .utf8)!
    try exampleData.write(to: tempFileURL)
    print("Midlertidig fil opprettet på: \(tempFileURL)")
} catch {
    print("Kunne ikke skrive til midlertidig fil: \(error)")
}
```

Output eksempel:
```
Midlertidig fil opprettet på: file:///private/var/folders/.../T/E75977E3-1DF9-4E09-B8C0-5EFCDF60C5D2
```

## Deep Dive
I gamle dager var det opp til utviklere å håndtere midlertidige filer selv. Dette kunne inkludere å skape, bruke og slette dem. Feil i denne prosessen kunne føre til datalekkasjer eller søppeldata som tar opp plass. I moderne operativsystemer som macOS, er det innebygde funksjoner for å håndtere midlertidige filer. Swift standardbibliotek inkluderer `FileManager`, som gir en enkel API for å jobbe med filsystemet.

Noen alternativer for å skape midlertidige filer er å bruke biblioteker fra tredjepart eller lavnivå C API-er, men `FileManager` gir nok funksjonalitet for de fleste behov.

Når det kommer til implementeringsdetaljer, så sikrer Swifts `UUID` at filnavnet er unikt, og bruk av `do-try-catch` blokken hjelper med å fange opp og håndtere eventuelle skrivefeil. Det er viktig å merke seg at mens filen blir laget i det midlertidige mappen, er det opp til utvikleren å slette filen etter bruk – hvis spesifikk levetid er nødvendig.

## See Also
- Swift Programming Language Guide: https://swift.org/documentation/#the-swift-programming-language
- Apple Developer Documentation on FileManager: https://developer.apple.com/documentation/foundation/filemanager
- UUID Class Reference: https://developer.apple.com/documentation/foundation/uuid
