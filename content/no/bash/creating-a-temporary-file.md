---
title:                "Opprette en midlertidig fil"
date:                  2024-01-20T17:39:24.573368-07:00
model:                 gpt-4-1106-preview
simple_title:         "Opprette en midlertidig fil"
programming_language: "Bash"
category:             "Bash"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/bash/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Oppretting av midlertidige filer lar oss holde data midlertidig under programmets kjøring. Programmerere gjør dette for sikkerhetskopiering, for å unngå databehandlingstap ved feil, eller når vi trenger et sted å sette fra oss data uten å påvirke permanente filer.

## Hvordan gjør man det:
```Bash
# Opprett en midlertidig fil med mktemp-kommandoen
temp_file=$(mktemp)
echo "Dette er en test" > "${temp_file}"

# Vis innholdet i den midlertidige filen
cat "${temp_file}"

# Slett den midlertidige filen etter bruk
rm "${temp_file}"
```
Eksempelutskrift:
```
Dette er en test
```

## Dypdykk
Opprettelsen av midlertidige filer i UNIX-lignende systemer har lenge vært vanlig, gjort med verktøy som `mktemp`, som ble tilgjengelig på 1980-tallet. Tidligere var det vanlig å bruke `$$` (prosessens ID) for å navngi midlertidige filer, men dette kunne lede til sikkerhetsproblemer. `mktemp` løser dette ved å skape en unik fil i `/tmp`-katalogen med en tilfeldig del i navnet. En alternativ måte er å bruke `tempfile`-kommandoen, skjønt `mktemp` er oftere anbefalt grunnet større fleksibilitet og bredere tilgjengelighet. Implementeringsdetaljene til `mktemp` kan inkludere et prefiks, suffiks, og spesifisering av katalog.

## Se også
- Bash-håndboken: https://www.gnu.org/software/bash/manual/
- `mktemp` man-side: https://linux.die.net/man/1/mktemp
- Advanced Bash-Scripting Guide: https://tldp.org/LDP/abs/html/