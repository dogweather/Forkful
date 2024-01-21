---
title:                "Hämta en webbsida"
date:                  2024-01-20T17:45:19.404103-07:00
model:                 gpt-4-1106-preview
simple_title:         "Hämta en webbsida"
programming_language: "Swift"
category:             "Swift"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/swift/downloading-a-web-page.md"
---

{{< edit_this_page >}}

# Hämta en webbsida med Swift

## Vad & Varför?
Hämtning av en webbsida innebär att ladda ner dess HTML-innehåll. Programmörer gör detta för att läsa eller bearbeta information från webben.

## Hur gör man:
Swift-kod för att hämta en webbsida ser ungefär så här ut:

```swift
import Foundation

let url = URL(string: "https://example.com")!
let task = URLSession.shared.dataTask(with: url) { data, response, error in
    if let error = error {
        print("Client error: \(error.localizedDescription)")
        return
    }
    
    guard let httpResponse = response as? HTTPURLResponse,
        (200...299).contains(httpResponse.statusCode) else {
        print("Server error")
        return
    }
    
    if let mimeType = httpResponse.mimeType, mimeType == "text/html",
       let data = data,
       let string = String(data: data, encoding: .utf8) {
        print(string)
    }
}

task.resume()
```
Exempelutdata:

```html
<!doctype html>
<html>
  <head>
    <title>Exempelsida</title>
  </head>
  <body>
    <p>Hej från example.com!</p>
  </body>
</html>
```

## Fördjupning
Att hämta en sida är inte nytt. Sedan internets begynnelse har vi laddat ner webbsidor, och metoder har förbättrats över tid. Från enkla HTTP GET-anrop i tidiga dagar till asynkrona bibliotek och ramverk idag.

Alternativ till `URLSession` inkluderar tredjepartsbibliotek som `Alamofire` eller `AFNetworking` (för äldre iOS-appar). Valet beror på behovet av avancerade funktioner eller enklare kodstruktur.

Implementationen ovan är grundläggande. Den hanterar inte omfattande felhantering, autentisering eller komplexa hjälptjänster (cookies, sessioner, headers). Även hantering av olika textkodningar och innehållstyper utöver `text/html` är en del av en fullständig lösning.

## Se även
- Apples dokumentation för [URLSession](https://developer.apple.com/documentation/foundation/urlsession)
- [Alamofire](https://github.com/Alamofire/Alamofire) – En Swift-baserad HTTP-nätverksbibliotek.
- [Swift URLSession tutorial](https://www.raywenderlich.com/3244963-urlsession-tutorial-getting-started) på raywenderlich.com.
- För designmönster och arkitektur, kolla [iOS Design Patterns](https://developer.apple.com/design/human-interface-guidelines/ios/overview/themes/).