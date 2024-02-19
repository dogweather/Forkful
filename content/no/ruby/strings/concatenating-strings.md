---
aliases:
- /no/ruby/concatenating-strings/
date: 2024-01-20 17:35:46.704887-07:00
description: "I programmering betyr \xE5 \"konkatenere\" strenger \xE5 sette dem sammen\
  \ til \xE9n. Programutviklere konkatenere strenger for \xE5 bygge setninger, lage\
  \ meldinger,\u2026"
lastmod: 2024-02-18 23:08:54.428978
model: gpt-4-1106-preview
summary: "I programmering betyr \xE5 \"konkatenere\" strenger \xE5 sette dem sammen\
  \ til \xE9n. Programutviklere konkatenere strenger for \xE5 bygge setninger, lage\
  \ meldinger,\u2026"
title: "Sammensl\xE5ing av strenger"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
I programmering betyr å "konkatenere" strenger å sette dem sammen til én. Programutviklere konkatenere strenger for å bygge setninger, lage meldinger, eller sammenslå brukerinput - kjekt og ofte nødvendig.

## Hvordan:
Konkatenere strenger kan gjøres på noen måter i Ruby. Her er noen eksempler:

```Ruby
# Med pluss-operator (+)
hilsen = "Hei, " + "verden!"
puts hilsen # => Hei, verden!

# Med shovel-operator (<<)
navn = "Ola"
navn << " Nordmann"
puts navn # => Ola Nordmann

# Med interpolering
fornavn = "Kari"
etternavn = "Nordmann"
fullt_navn = "#{fornavn} #{etternavn}"
puts fullt_navn # => Kari Nordmann

# Med `concat`-metoden
melding = "Ha en"
melding.concat(" fin dag!")
puts melding # => Ha en fin dag!
```

## Dypdykk
I Ruby sin tidlige dager, var konkatenere strenger like enkelt som nå. Men, performance og minnebruk var tema. Hver bruk av `+` skaper en ny streng, mens `<<` endrer eksisterende, sparer minne.

Alternativer som array-join metoden (`array.join`) er også brukt, spesielt når du har flere strenger:

```Ruby
arr = ["God", "dag", "til", "deg"]
setning = arr.join(" ")
puts setning # => God dag til deg
```

Implementasjonsdetaljer viser at Ruby håndterer strenger dynamisk og objektorientert, så hver streng er et objekt med metoder for manipulasjon, inkludert konkatenasjon.

## Se Også:
- Ruby dokumentasjon for String: [Ruby-Doc.org: String](https://ruby-doc.org/core-2.7.0/String.html)
- En guide til strenger i Ruby: [RubyGuides: Ruby Strings](https://www.rubyguides.com/2018/01/ruby-string-methods/)
