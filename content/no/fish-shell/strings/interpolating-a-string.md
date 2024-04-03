---
date: 2024-01-20 17:50:37.467224-07:00
description: "Interpolering av strenger lar deg bake inn variabler eller uttrykk i\
  \ en tekststreng. Det gj\xF8r koden mer fleksibel og lesbar n\xE5r du skal bygge\
  \ dynamisk\u2026"
lastmod: '2024-03-13T22:44:41.211508-06:00'
model: gpt-4-1106-preview
summary: Interpolering av strenger lar deg bake inn variabler eller uttrykk i en tekststreng.
title: Interpolering av en streng
weight: 8
---

## Slik gjør du:
Interpoler en variabel i Fish:

```Fish Shell
set name "Verden"
echo "Hei, $name!"
```

Utskrift:

```
Hei, Verden!
```

Loop og interpoler:

```Fish Shell
for color in blå rød grønn
    echo "Eplet er $color"
end
```

Utskrift:

```
Eplet er blå
Eplet er rød
Eplet er grønn
```

## Dypdykk
Historisk har flere skall som Bash brukt forskjellig syntaks for interpolering, for eksempel `"$variabel"`. Fish Shell gjør ikke ting for forskjellig – det er rett fram og greit. Andre skall kan kreve mer kompleks syntaks eller bruk av eksterne kommandoer som `expr` eller `sed` for enkelte operasjoner.

Interpolering i Fish blir håndtert direkte i skallskriptene uten bruk av eksterne kommandoer, noe som fører til raskere utførelse og mindre skriving. Dette gjør koden ren og vedlikeholdsvennlig.

Fish har ingen eksplosiv syntaks for å utføre variabelinterpolering. Det er bare å sette `$` foran variabelnavnet der du vil ha verdien erstattet.

## Se også
- Fish dokumentasjon om variabler: `https://fishshell.com/docs/current/#variables`
- Tutorial for Fish Shell scripting: `https://fishshell.com/docs/current/tutorial.html`
- Stack Overflow for spesifikke spørsmål og svar om Fish: `https://stackoverflow.com/questions/tagged/fish`
