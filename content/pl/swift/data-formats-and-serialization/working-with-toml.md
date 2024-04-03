---
date: 2024-01-26 04:26:47.984840-07:00
description: "TOML (Tom's Obvious, Minimal Language) to format serializacji danych,\
  \ kt\xF3ry jest \u0142atwy do odczytania dzi\u0119ki swoim jasnym semantykom. Programi\u015B\
  ci u\u017Cywaj\u0105\u2026"
lastmod: '2024-03-13T22:44:35.777957-06:00'
model: gpt-4-0125-preview
summary: "TOML (Tom's Obvious, Minimal Language) to format serializacji danych, kt\xF3\
  ry jest \u0142atwy do odczytania dzi\u0119ki swoim jasnym semantykom."
title: Praca z TOML
weight: 39
---

## Jak to zrobić:
Na początek potrzebujesz parsera TOML. Swift nie ma wbudowanego, więc użyjmy `TOMLDecoder`. Zainstaluj go przez Swift Package Manager, a następnie serializuj i deserializuj TOML z łatwością.

```Swift
import TOMLDecoder

let tomlString = """
title = "Przykład TOML"

[owner]
name = "Tom Preston-Werner"
dob = 1979-05-27T07:32:00Z
"""

struct Config: Codable {
    let title: String
    let owner: Owner
}

struct Owner: Codable {
    let name: String
    let dob: Date
}

let decoder = TOMLDecoder()
if let configData = tomlString.data(using: .utf8) {
    do {
        let config = try decoder.decode(Config.self, from: configData)
        print("Tytuł: \(config.title), Właściciel: \(config.owner.name), Data urodzenia: \(config.owner.dob)")
    } catch {
        print("Błąd parsowania TOML: \(error)")
    }
}
```

Ten kod wypisuje:
```
Tytuł: Przykład TOML, Właściciel: Tom Preston-Werner, Data urodzenia: 1979-05-27 07:32:00 +0000
```

## Pogłębione spojrzenie
TOML został zaprojektowany przez Toma Preston-Wernera, współzałożyciela GitHuba, jako bardziej przyjazna dla człowieka alternatywa dla formatów takich jak JSON czy YAML. Ma na celu jasność, redukując szanse na błędną interpretację przez człowieka lub maszynę. Jeśli chodzi o alternatywy, YAML i JSON to zwykli podejrzani, z tym że YAML jest skierowany na czytelność dla ludzi, a JSON jako prostsza opcja przyjazna maszynom. Pracując z TOML w Swift, nie mamy natywnego parsera. Jednak biblioteki stron trzecich takie jak `TOMLDecoder` ułatwiają łatwą konwersję między ciągami TOML a typami Swift, zwłaszcza poprzez protokoły `Codable` wprowadzone w Swift 4, które usprawniły serializację.

## Zobacz także
- Standard TOML: https://toml.io
- GitHub dla `TOMLDecoder`: https://github.com/dduan/TOMLDecoder
- Dokumentacja Swift dotycząca `Codable`: https://developer.apple.com/documentation/swift/codable
- Porównanie formatów serializacji danych: https://pl.wikipedia.org/wiki/Porównanie_formatów_serializacji_danych
