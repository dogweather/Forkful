---
date: 2024-01-20 17:44:56.986546-07:00
description: "Utdrag av strenger er \xE5 hente deler fra en tekststreng. Programmerere\
  \ gj\xF8r det for \xE5 jobbe med spesifikke datasegmenter, validere input, eller\
  \ manipulere\u2026"
lastmod: '2024-03-13T22:44:40.961385-06:00'
model: gpt-4-1106-preview
summary: "Utdrag av strenger er \xE5 hente deler fra en tekststreng."
title: Uthenting av delstrenger
weight: 6
---

## Hvordan:
```Bash
# Ekstrahere med substr
streng="Hei, Norge!"
del=${streng:5:5}
echo $del  # Output: Norge

# Bruke 'cut' kommando
echo "Hei, Norge!" | cut -d "," -f2  # Output: Norge!

# Enkel pattern matching
echo ${streng#*, }  # Output: Norge!
```

## Dypdykk
I tidlige dager, hadde vi ikke mange innebygde strengoperasjoner i Bash. Vi støttet oss på eksterne verktøy som `cut`, `awk`, `grep`. Med Bash 2.0 (1996) kom `${parameter:offset:length}`, som var et fremskritt.  
Alternativer til innebygde Bash-metoder inkluderer programmer som `awk` og `sed`, som er kraftige tekstbehandlingsverktøy. Når det gjelder implementasjon, er det viktig å huske på at Bash er 0-indeksert, noe som betyr at tellingen starter fra 0.

## Se Også
- Bash manualen: https://www.gnu.org/savannah-checkouts/gnu/bash/manual/bash.html#Shell-Parameter-Expansion
- Advanced Bash-Scripting Guide: https://tldp.org/LDP/abs/html/string-manipulation.html
- En guide til `sed`: https://www.gnu.org/software/sed/manual/sed.html
- En introduksjon til `awk`: https://www.gnu.org/software/gawk/manual/gawk.html
