---
title:                "Interpolering av en streng"
aliases:
- no/bash/interpolating-a-string.md
date:                  2024-01-20T17:50:17.560921-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolering av en streng"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/bash/interpolating-a-string.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Interpolering av en streng betyr å sette inn variabler eller uttrykk inni en tekststreng. Programmere bruker det for å bygge dynamisk innhold og meldinger.

## Hvordan:
```Bash
name="Verden"
echo "Hei, $name!"
# Output: Hei, Verden!
```

Du kan også bruke krøllparenteser for klarhet:
```Bash
greeting="hei"
target="Verden"
echo "${greeting}, ${target}!"
# Output: hei, Verden!
```

Og for å manipulere verdien under interpoleringen:
```Bash
item="apple"
echo "I have ${item}s"
# Output: I have apples
```

## Dypdykk:
Strenginterpolering i kodespråk har vært rundt en stund. I eldre språk som Perl, ble dette populært på 80-tallet. Bash, arvingen til Sh shell, adopterte også denne funksjonen.

Alternativer til interpolering i Bash kan være å bruke `echo` med flere argumenter eller `printf` for mer formatert utskrift:
```Bash
echo "Hello" $name "!"
# Samme utskrift uten interpolering

printf "Hei, %s!\n" "$name"
# Mer kontroll over formatet
```

Implementeringsdetaljer? I Bash blir alt mellom dobbelte sitater utvidet eller `evaluated`. Det betyr at variabler, uttrykk, og kommandoer innenfor " " får kjørt sin funksjon.

## Se Også:
- Bash manualen: https://www.gnu.org/software/bash/manual/
- Advanced Bash-Scripting Guide: https://tldp.org/LDP/abs/html/
- Wiki om Shell Script: https://en.wikipedia.org/wiki/Shell_script

Disse kildene gir mer inngående kunnskap om Bash-skripting og dens funksjoner.
