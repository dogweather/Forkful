---
title:                "Analyse av HTML"
date:                  2024-01-20T15:34:06.387643-07:00
html_title:           "Arduino: Analyse av HTML"
simple_title:         "Analyse av HTML"
programming_language: "Swift"
category:             "Swift"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/swift/parsing-html.md"
---

{{< edit_this_page >}}

## What & Why?
Hva er HTML-parsing, og hvorfor driver vi med det? Parsing av HTML betyr å trekke ut data fra en webside sin kode. Programmerere gjør det for å kunne jobbe med, analysere, eller endre innhold dynamisk.

## How to:
For å parse HTML i Swift, kan du bruke biblioteket SwiftSoup. Før du starter, må du installere SwiftSoup via SPM eller CocoaPods. Her er et grunnleggende eksempel:

```Swift
import SwiftSoup

let html = "<html><head><title>Første eksempel</title></head><body><p>Hei, SwiftSoup!</p></body></html>"
do {
    let doc = try SwiftSoup.parse(html)
    if let bodyText = try doc.body()?.text() {
        print(bodyText)  // Skriver ut: "Hei, SwiftSoup!"
    }
} catch Exception.Error(let type, let message) {
    print("Got an error of type: \(type) with message: \(message)")
} catch {
    print("An error occurred")
}
```

## Deep Dive
Parsing av HTML er ikke nytt. Før Swift var det vanlig i språk som JavaScript og Python. Med tiden har Swift-utviklere fått sine egne verktøy, som SwiftSoup, basert på Java-biblioteket Jsoup. Alternativer til SwiftSoup inkluderer Kanna og hpple, men SwiftSoup er ofte foretrukket for dets lignende API til Jsoup.

Implementasjonsdetaljene innebærer rendring av HTML som et DOM (Document Object Model) tre hvor elementene kan traverseres og manipuleres. Riktig feilhåndtering er kritisk, siden HTML fra weben kan være uforutsigbar og må renskes for å unngå sikkerhetsproblemer som XSS (Cross-Site Scripting).

## See Also
Dykke dypere?
- SwiftSoup GitHub: https://github.com/scinfu/SwiftSoup
- Jsoup hjemmeside (for inspirasjon): https://jsoup.org
- W3C HTML Parser spesifikasjoner: https://www.w3.org/TR/html5/syntax.html#parsing
