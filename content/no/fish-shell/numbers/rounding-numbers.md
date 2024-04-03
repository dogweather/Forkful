---
date: 2024-01-26 03:44:05.968619-07:00
description: "\xC5 avrunde tall handler om \xE5 kutte av desimalplasser for \xE5 forenkle\
  \ dataene dine eller passe spesifikke formater. Programmerere gj\xF8r det for brukervennlig\u2026"
lastmod: '2024-03-13T22:44:41.219777-06:00'
model: gpt-4-0125-preview
summary: "\xC5 avrunde tall handler om \xE5 kutte av desimalplasser for \xE5 forenkle\
  \ dataene dine eller passe spesifikke formater."
title: Avrunding av tall
weight: 13
---

## Hvordan:
I Fish avhenger avrunding av tall av `math`-kommandoen. Bruk `math -s0` for å avrunde til nærmeste heltall.

```fish
# Avrund opp
echo (math -s0 "4.7")
# Utdata: 5

# Avrund ned
echo (math -s0 "4.3")
# Utdata: 4

# Avrund til to desimalplasser
echo (math -s2 "4.5678")
# Utdata: 4.57

# Avrund negativt tall
echo (math -s0 "-2.5")
# Utdata: -3
```

## Dypdykk
Historisk sett ble tall avrundet mer manuelt eller med eksterne verktøy, men i moderne skall som Fish, er det integrert i innebygde verktøy. Fish sin tilnærming ved bruk av `math`-kommandoen forenkler ting sammenlignet med eldre skall. Alternativer i andre programmeringsmiljøer varierer; språk som Python bruker funksjoner som `round()`, mens Bash kan kreve mer komplekse uttrykk eller `bc`-verktøyet. Fish sin implementering av avrunding forenkler skripting ved å holde matematikken inne i shell-miljøet i stedet for å påkalle andre verktøy eller språk.

## Se også
- Fish-dokumentasjon for `math`-kommandoen: https://fishshell.com/docs/current/cmds/math.html
- IEEE Standard for Flyttallaritmetikk (IEEE 754): https://ieeexplore.ieee.org/document/4610935
