---
aliases:
- /no/haskell/reading-a-text-file/
date: 2024-01-20 17:54:42.265959-07:00
description: "\xC5 lese en tekstfil betyr \xE5 hente og bruke informasjon lagret i\
  \ en fil p\xE5 datamaskinen. Programmere gj\xF8r dette for \xE5 behandle data, konfigurere\
  \ programmer,\u2026"
lastmod: 2024-02-18 23:08:53.951503
model: gpt-4-1106-preview
summary: "\xC5 lese en tekstfil betyr \xE5 hente og bruke informasjon lagret i en\
  \ fil p\xE5 datamaskinen. Programmere gj\xF8r dette for \xE5 behandle data, konfigurere\
  \ programmer,\u2026"
title: Lese en tekstfil
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å lese en tekstfil betyr å hente og bruke informasjon lagret i en fil på datamaskinen. Programmere gjør dette for å behandle data, konfigurere programmer, eller for å lagre resultater til videre bruk.

## Hvordan:
```Haskell
import System.IO

-- Enkleste måten å lese innholdet av en tekstfil:
main = do
    innhold <- readFile "eksempel.txt"
    putStr innhold
```
_Det forventede utdata vil være innholdet av `eksempel.txt` vist på skjermen._

Eller med "lazy IO" for store filer:

```Haskell
main = do
    withFile "storfil.txt" ReadMode (\handle -> do
        innhold <- hGetContents handle
        putStr innhold)
```
_Forventet utdata: innholdet av `storfil.txt`._

## Dypdykk
Historisk sett har I/O vært problematisk i funksjonelle språk som Haskell grunnet deres 'pure functions'. `readFile` og lignende funksjoner løser dette ved å bruke "lazy IO", som leser filen i blokker ved behov. Et alternativ til "lazy IO" er "strict IO" der man leser hele filen på en gang, som kan være mer forutsigbart i forhold til ressursbruk og feilhåndtering.

I Haskell er det flere måter å lese filer på:
- `readFile`: bra for små til medium størrelser.
- `readFile` og `lines`: for lesing linje for linje.
- `hGetContents` med `withFile`: "lazy IO" for store filer.
- Biblioteker som `text` og `bytestring` for ytelse og minnehåndtering.

Implementeringsdetaljer er viktige for å forstå hvordan Haskell håndterer filer. "Lazy IO" kan være uberegnelig når det gjelder ressurser, siden det holder filen åpen til garbage-collectoren rydder opp. Med "strict IO", vet du nøyaktig når filen lukkes.

## Se Også
- [Haskell I/O Tutorial](https://wiki.haskell.org/IO_inside)
- [Haskell bytestring library](https://hackage.haskell.org/package/bytestring)
- [Haskell text library](https://hackage.haskell.org/package/text)
- [Real World Haskell: Input and Output](http://book.realworldhaskell.org/read/io.html)
