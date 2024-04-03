---
date: 2024-01-20 17:39:24.573368-07:00
description: "Oppretting av midlertidige filer lar oss holde data midlertidig under\
  \ programmets kj\xF8ring. Programmerere gj\xF8r dette for sikkerhetskopiering, for\
  \ \xE5 unng\xE5\u2026"
lastmod: '2024-03-13T22:44:40.993978-06:00'
model: gpt-4-1106-preview
summary: "Oppretting av midlertidige filer lar oss holde data midlertidig under programmets\
  \ kj\xF8ring."
title: Opprette en midlertidig fil
weight: 21
---

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
