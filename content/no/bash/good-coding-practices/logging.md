---
aliases:
- /no/bash/logging/
date: 2024-01-26 00:59:28.183435-07:00
description: "Logging er praksisen med \xE5 registrere hendelser, feil og annen viktig\
  \ informasjon fra kj\xF8rende prosesser i et program til en fil eller en utdatastr\xF8\
  m.\u2026"
lastmod: 2024-02-18 23:08:54.064570
model: gpt-4-1106-preview
summary: "Logging er praksisen med \xE5 registrere hendelser, feil og annen viktig\
  \ informasjon fra kj\xF8rende prosesser i et program til en fil eller en utdatastr\xF8\
  m.\u2026"
title: "Loggf\xF8ring"
---

{{< edit_this_page >}}

## Hva og hvorfor?

Logging er praksisen med å registrere hendelser, feil og annen viktig informasjon fra kjørende prosesser i et program til en fil eller en utdatastrøm. Programmerere gjør dette for å spore oppførselen til applikasjonene sine, feilsøke problemer og beholde en historisk oversikt over operasjoner som kan bistå med fremtidig feilsøking.

## Hvordan:

I Bash kan logging være så enkelt som å omdirigere eller legge til utdata i en fil. Her er et grunnleggende eksempel:

```Bash
echo "Starter skriptet..." >> script.log
# Dine skriptkommandoer her
echo "Skript fullført den $(date)" >> script.log
```

For noe mer avansert, kunne du inkorporere syslog for systemvid logging:

```Bash
logger "Egendefinert melding fra mitt skript"
```

`logger` sender en loggmelding til syslog-tjenesten, som så håndterer den i henhold til systemets syslog-konfigurasjon.

Eksempel på utdata fanget i `script.log`:

```Bash
Starter skriptet...
Skript fullført den Tir Mar 23 09:26:35 PDT 2021
```

## Dypdykk

Historisk sett i Unix-lignende systemer, har logging blitt fasilitert av syslog-tjenesten, som tillater forskjellige applikasjoner og deler av systemet å logge meldinger sentralt. Dette muliggjør implementeringen av en standardisert loggingmekanisme gjennom hele systemet.

Når det kommer til alternativer, kan noen vurdere å bruke `syslog-ng` eller `rsyslog` for mer avanserte loggingsfunksjoner, eller skrive logger til en tidsserie-database for analytiske formål. For applikasjoner med høyere nivåer av kompleksitet, kan det gi mening å bruke et dedikert loggingsbibliotek eller applikasjon som Log4j (i Java-økosystemet) eller Monolog (i PHP), som kan tilby strukturerte og konfigurerbare loggingsalternativer, selv for et skriptspråk som Bash.

Måten du implementerer logging på, avhenger i stor grad av din applikasjons behov. Hvis du bare trenger enkel utdata for å spore fremdriften til skriptet, er det enkelt og praktisk å legge til meldinger i en fil. Imidlertid, for mer skalerbar og robust logging, vil du integrere med et loggingssystem som støtter funksjoner som loggrotasjon, loggnivåer og fjernlogging.

## Se også

- `man`-sidene for `logger`- og `syslog`-funksjonene er alltid dine venner, prøv `man logger` eller `man syslog`.
- For et dybdegående blikk på systemlogging, vurder å lese dokumentasjonen for `rsyslog` og `syslog-ng`.
- For å finne ut mer om den historiske konteksten og prinsippene bak logging i Unix-lignende systemer, gir `Syslog`-protokollen dokumentert i RFC 5424 omfattende informasjon.
