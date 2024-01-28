---
title:                "Att arbeta med TOML"
date:                  2024-01-26T04:26:53.627027-07:00
model:                 gpt-4-0125-preview
simple_title:         "Att arbeta med TOML"
programming_language: "Swift"
category:             "Swift"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/swift/working-with-toml.md"
---

{{< edit_this_page >}}

## Vad & Varför?
TOML (Toms Uppenbara, Minimala Språk) är ett data-serialiseringsformat som är lätt att läsa på grund av dess klara semantik. Programmerare använder TOML för konfigurationsfiler där läsbarhet för människor och enkel tolkning för maskiner är nyckeln.

## Hur man gör:
För att börja behöver du en TOML-tolk. Swift har inte en inbyggd sådan, så låt oss använda `TOMLDecoder`. Installera den via Swift Package Manager och sedan serialisera och deserialisera TOML med lätthet.

```Swift
import TOMLDecoder

let tomlString = """
title = "TOML-exempel"

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
        print("Titel: \(config.title), Ägare: \(config.owner.name), Födelsedag: \(config.owner.dob)")
    } catch {
        print("Fel vid tolkning av TOML: \(error)")
    }
}
```

Den här koden ger utdata:
```
Titel: TOML-exempel, Ägare: Tom Preston-Werner, Födelsedag: 1979-05-27 07:32:00 +0000
```

## Fördjupning
TOML designades av Tom Preston-Werner, medgrundare av GitHub, som ett mer människovänligt alternativ till format som JSON eller YAML. Det strävar efter tydlighet, vilket minskar chanserna för feltolkning av en människa eller maskin. När det gäller alternativ är YAML och JSON de vanliga misstänkta, med YAML lutat mot läsbarhet för människor och JSON som det enklare maskinvänliga alternativet. När vi arbetar med TOML i Swift har vi ingen inbyggd tolk. Dock underlättar tredjepartsbibliotek som `TOMLDecoder` enkel omvandling mellan TOML-strängar och Swift-typer, specifikt via `Codable`-protokoll introducerade i Swift 4 som strömlinjeformat serialisering.

## Se även
- TOML-standarden: https://toml.io
- GitHub för `TOMLDecoder`: https://github.com/dduan/TOMLDecoder
- Swift-dokumentation om `Codable`: https://developer.apple.com/documentation/swift/codable
- Jämförelse av data-serialiseringsformat: https://en.wikipedia.org/wiki/Comparison_of_data-serialization_formats
