---
aliases:
- /no/haskell/concatenating-strings/
date: 2024-01-20 17:35:00.273360-07:00
description: "Sammenkjeding av strenger handler om \xE5 sl\xE5 sammen tekster til\
  \ \xE9n. Programmerere gj\xF8r dette for \xE5 bygge setninger, vise data og kombinere\
  \ brukerinput."
lastmod: 2024-02-18 23:08:53.927163
model: gpt-4-1106-preview
summary: "Sammenkjeding av strenger handler om \xE5 sl\xE5 sammen tekster til \xE9\
  n. Programmerere gj\xF8r dette for \xE5 bygge setninger, vise data og kombinere\
  \ brukerinput."
title: "Sammensl\xE5ing av strenger"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Sammenkjeding av strenger handler om å slå sammen tekster til én. Programmerere gjør dette for å bygge setninger, vise data og kombinere brukerinput.

## Hvordan:
I Haskell, bruker vi `(++)` operatoren eller `concat` funksjonen. Her er litt kode:

```Haskell
-- Bruker (++)
hilsen :: String
hilsen = "Hei, " ++ "verden!"

-- Output: "Hei, verden!"

-- Med concat
navnListe :: [String]
navnListe = concat ["Norden", " og ", "Sør"]

-- Output: "Norden og Sør"
```

## Dypdykk
I Haskell, som er en funksjonell programmeringsspråk, er strengsammenslåing en grunnleggende operasjon. Funksjonaliteten har vært en del av Haskell siden starten (på 1990-tallet), inspirert av lignende konsepter i tidligere funksjonelle språk som Lisp. Det finnes alternativer til `(++)` som `concat`, `intercalate` og `foldr`, som gir ulike nyanser for mer kompliserte behov. Internt, strenger er lister av tegn (`[Char]`), og sammenkjeding blir en liste-operasjon.

## Se Også
- [Learn You a Haskell for Great Good! on Strings](http://learnyouahaskell.com/starting-out#strings)
