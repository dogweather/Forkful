---
aliases:
- /sv/clojure/finding-the-length-of-a-string/
date: 2024-01-20 17:47:10.480137-07:00
description: "Att hitta str\xE4ngl\xE4ngden inneb\xE4r att r\xE4kna antalet tecken\
  \ i en str\xE4ng. Programmerare g\xF6r detta f\xF6r att validera indata, begr\xE4\
  nsa l\xE4ngden, eller f\xF6r att\u2026"
lastmod: 2024-02-18 23:08:51.453705
model: gpt-4-1106-preview
summary: "Att hitta str\xE4ngl\xE4ngden inneb\xE4r att r\xE4kna antalet tecken i en\
  \ str\xE4ng. Programmerare g\xF6r detta f\xF6r att validera indata, begr\xE4nsa\
  \ l\xE4ngden, eller f\xF6r att\u2026"
title: "Hitta l\xE4ngden p\xE5 en str\xE4ng"
---

{{< edit_this_page >}}

## Vad & Varför?
Att hitta stränglängden innebär att räkna antalet tecken i en sträng. Programmerare gör detta för att validera indata, begränsa längden, eller för att manipulera text effektivt.

## Hur man gör:
```Clojure
;; Använd `count` för att hitta längden på en sträng
(count "Hej, Sverige!")
;; => 13

;; Det fungerar också på listor och andra samlingar
(count [1 2 3 4 5])
;; => 5
```

## Djupdykning
I Clojure, som i många funktionella språk, är `count` en grundläggande funktion som används för att hitta antalet element i en samling. Historiskt sett har det alltid varit viktigt att veta längden på en datastruktur för att organisera och hantera information effektivt. Alternativ till `count` inkluderar att använda `length` i andra språk eller att iterera genom en sträng och räkna tecken, vilket är en ineffektiv metod i Clojure. Implementationen av `count` är optimerad för olika samlingstyper; för en sträng är det en direkt operation, men för länkade listor måste hela listan genomgås för att få fram en längd.

## Se även
- Clojure-dokumentationen om `count`: [https://clojuredocs.org/clojure.core/count](https://clojuredocs.org/clojure.core/count)
- En diskussion om att hantera strängar i Clojure: [https://clojure.org/guides/faq#string_funcs](https://clojure.org/guides/faq#string_funcs)
- Artikel om funktionella språk och datastrukturer: [https://www.braveclojure.com/functional-programming/](https://www.braveclojure.com/functional-programming/)
