---
title:                "Omvandla en sträng till gemener"
html_title:           "Arduino: Omvandla en sträng till gemener"
simple_title:         "Omvandla en sträng till gemener"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/gleam/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Att konvertera en sträng till gemener innebär att ändra alla stora bokstäver till småtbokstäver i en given textsträng. Programmerare gör detta för att underlätta textmatchning och sortering, eftersom datorer skiljer på stora och små bokstäver.

## Hur man gör:
I Gleam används funktionen `to_lower` i `string`-modulen för att konvertera till gemener. Här är ett exempel:

```Gleam
import gleam/string

fn main() -> Nil {
  let sträng = "Hej VÄRLDEN!"
  let gentemener = string.to_lower(sträng)
  assert(gentemener == "hej världen!")
}
```

Kör denna kod, och utmatningen kommer att bli:
```Gleam
"hej världen!"
```

## Fördjupning
Historiskt sett användes konvertering till gemener i början av datortiden för att spara utrymme, eftersom det inte fanns plats för både stora och små bokstäver i vissa lagringssystem. I Gleam och de flesta moderna språk, används detta för jämförelser och sortering. 

Ett alternativ till `string.to_lower` kan vara att skriva en egen funktion, men detta rekommenderas inte eftersom det är troligt att det blir fel. 

`to_lower`-funktionen i Gleam fungerar genom att gå igenom varje tecken i strängen, kolla om det är en stor bokstav, och om det är, ändra den till en liten bokstav.