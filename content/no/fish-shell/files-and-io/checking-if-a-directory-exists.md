---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:21.172837-07:00
description: "\xC5 sjekke om en katalog eksisterer i Fish Shell gj\xF8r det mulig\
  \ for skript \xE5 ta beslutninger basert p\xE5 tilstedev\xE6relsen eller frav\xE6\
  ret av katalogstrukturer,\u2026"
lastmod: '2024-03-13T22:44:41.241881-06:00'
model: gpt-4-0125-preview
summary: "\xC5 sjekke om en katalog eksisterer i Fish Shell gj\xF8r det mulig for\
  \ skript \xE5 ta beslutninger basert p\xE5 tilstedev\xE6relsen eller frav\xE6ret\
  \ av katalogstrukturer, noe som muliggj\xF8r oppgaver som betingede filoperasjoner,\
  \ logging eller oppsett av milj\xF8."
title: Sjekker om en mappe eksisterer
weight: 20
---

## Hvordan gjøre det:
Fish Shell bruker `test`-kommandoen til å sjekke filtyper og karakteristikker, inkludert om et mål er en katalog. Her er et grunnleggende mønster for å sjekke om en katalog eksisterer:

```fish
if test -d /sti/til/katalog
    echo "Katalogen eksisterer"
else
    echo "Katalogen eksisterer ikke"
end
```
Eksempel på utskrift:
```
Katalogen eksisterer
```

For mer strømlinjeformede fil- og katalogoperasjoner, kan man vende seg til eksterne verktøy som `fd`, selv om det oftere brukes til å finne filer og kataloger fremfor bare å sjekke for eksistens. Men ved å kombinere det med Fish-scripting, kan man oppnå praktiske resultater:

```fish
set dir "/sti/til/søk"
if fd . $dir --type directory --max-depth 1 | grep -q $dir
    echo "Katalogen eksisterer"
else
    echo "Katalogen eksisterer ikke"
end
```

Dette `fd`-eksempelet søker etter katalogen på en spesifisert dybde, og `grep` sjekker for treff, noe som gjør det nyansert for detaljerte sjekker. Men, for det direkte formålet med å sjekke eksistens, er det å holde seg til Fish sin innebygde `test` både effektivt og rett på sak.
