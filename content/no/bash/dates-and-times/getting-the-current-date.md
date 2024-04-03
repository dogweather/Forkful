---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:47.967157-07:00
description: "\xC5 hente dagens dato i Bash involverer bruk av innebygde kommandoer\
  \ for \xE5 vise dato og tid i forskjellige formater. Programmerere bruker denne\u2026"
lastmod: '2024-03-13T22:44:40.985437-06:00'
model: gpt-4-0125-preview
summary: "\xC5 hente dagens dato i Bash involverer bruk av innebygde kommandoer for\
  \ \xE5 vise dato og tid i forskjellige formater."
title: "F\xE5 dagens dato"
weight: 29
---

## Hvordan:
I Bash er `date`-kommandoen ditt primære verktøy for å få tak i dagens dato og tid. Her er noen eksempler på hvordan du kan bruke den:

1. **Få dagens dato og tid i standardformatet:**

```bash
date
```

*Eksempel på utdata:*
```
Wed Apr 5 14:22:04 PDT 2023
```

2. **Tilpass utdataformatet:** Du kan spesifisere utdataformatet ved å bruke `+%` format-spesifikatorer. For eksempel, for å vise datoen i YYYY-MM-DD format:

```bash
date "+%Y-%m-%d"
```

*Eksempel på utdata:*
```
2023-04-05
```

3. **Få det nåværende UNIX tidsstempelet:** UNIX-tidsstempelet er antallet sekunder siden Unix Epoch (1. januar 1970). Dette er nyttig for skript som utfører beregninger basert på tidsforskjeller.

```bash
date "+%s"
```

*Eksempel på utdata:*
```
1672877344
```

Ingen populære tredjepartsbiblioteker brukes vanligvis til denne grunnleggende operasjonen i Bash, ettersom den innebygde `date`-kommandoen gir omfattende funksjonalitet. Imidlertid, for mer avanserte dato- og tidsmanipulasjoner, kan programmerere bruke andre programmeringsspråk eller verktøy som tilbyr biblioteker for datoaritmetikk og parsing, som for eksempel Pythons `datetime`-modul.
