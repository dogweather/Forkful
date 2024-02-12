---
title:                "Sette stor bokstav i en streng"
aliases:
- /no/clojure/capitalizing-a-string/
date:                  2024-02-03T19:04:53.738362-07:00
model:                 gpt-4-0125-preview
simple_title:         "Sette stor bokstav i en streng"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/clojure/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å sette stor bokstav i en streng innebærer å endre strengen slik at dens første tegn er en stor bokstav, mens resten av strengen forblir uendret. Programmerere utfører ofte stor bokstavsetting av strenger for å sikre datakonsistens, spesielt for navn og steder, eller for å overholde grammatiske regler i brukergrensesnitt.

## Hvordan:
Clojure, som er et JVM-språk, lar deg bruke Java String-metoder direkte. Her er et grunnleggende eksempel på hvordan du setter stor bokstav i en streng i Clojure:

```clojure
(defn capitalize-string [s]
  (if (empty? s)
    s
    (str (clojure.string/upper-case (subs s 0 1)) (subs s 1))))

(capitalize-string "hello world!") ; => "Hello world!"
```

Clojure inkluderer ikke en innebygd funksjon spesifikt for å sette stor bokstav i strenger, men som vist, kan du enkelt oppnå dette ved å kombinere `clojure.string/upper-case`, `subs` og `str` funksjoner.

For en mer kortfattet løsning og håndtering av mer komplekse strengmanipulasjoner, kan det hende du vender deg til et tredjepartsbibliotek. Et slikt populært bibliotek i Clojure-økosystemet er `clojure.string`. Imidlertid, per min siste oppdatering, tilbyr det ikke en direkte `capitalize`-funksjon utover det som er demonstrert med Clojures kjernefunksjonaliteter, så metoden vist ovenfor er din direkte tilnærming uten å trekke inn ekstra biblioteker spesifikt for stor bokstavsetting.

Husk, når du jobber med strenger i Clojure som samhandler med Java-metoder, jobber du effektivt med Java-strenger, noe som gjør at du kan utnytte hele arsenalt av Javas String-metoder direkte i Clojure-koden din om nødvendig.
