---
title:                "Konvertera en sträng till gemener"
aliases:
- sv/clojure/converting-a-string-to-lower-case.md
date:                  2024-01-20T17:38:04.950570-07:00
model:                 gpt-4-1106-preview
simple_title:         "Konvertera en sträng till gemener"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/clojure/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Att konvertera en sträng till små bokstäver innebär att ändra varje bokstav till dess motsvarighet i gemener. Programmerare gör detta för att normalisera textdata för sökning, sortering eller andra jämförelser där skiftlägen inte ska spela någon roll.

## Hur man gör:
```Clojure
;; Använd `clojure.string/lower-case` för att konvertera till små bokstäver
(require '[clojure.string :as str])

;; Exempel på strängkonvertering
(def example-string "Hej Världen!")
(def lower-case-string (str/lower-case example-string))

;; Utskrift av det converterade strängen
(println lower-case-string) ;; => "hej världen!"
```

## Djupdykning
Att konvertera strängar till små bokstäver är en standardoperation i de flesta programmeringsspråk, och Clojure är inget undantag. Historiskt har behovet av att jämföra strängar utan att skiftläge påverkar resultatet varit viktigt, särskilt i databaser och sökmotorer.

Alternativt kan programmerare använda Java-metoder direkt tack vare Clojures interop-förmåga med Java:

```Clojure
(.toLowerCase "Hej Världen!") ;; => "hej världen!"
```

Detaljer kring implementering kan variera beroende på underliggande plattform och teckenuppsättning. Clojure använder JVM:ns metoder vilket innebär att den tar hänsyn till lokala inställningar och Unicode-standarder.

## Se även
- Clojure's official string API documentation: [clojure.string](https://clojure.github.io/clojure/clojure.string-api.html)
- Oracle's Java String documentation for `.toLowerCase()`: [Java String Docs](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#toLowerCase())
