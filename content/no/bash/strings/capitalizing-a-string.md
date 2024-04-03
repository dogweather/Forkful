---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:53.082612-07:00
description: "\xC5 sette stor forbokstav i en streng i Bash inneb\xE6rer \xE5 omdanne\
  \ det f\xF8rste tegnet i strengen til en stor bokstav, mens resten av strengen forblir\
  \ uendret.\u2026"
lastmod: '2024-03-13T22:44:40.955797-06:00'
model: gpt-4-0125-preview
summary: "\xC5 sette stor forbokstav i en streng i Bash inneb\xE6rer \xE5 omdanne\
  \ det f\xF8rste tegnet i strengen til en stor bokstav, mens resten av strengen forblir\
  \ uendret."
title: Sette stor bokstav i en streng
weight: 2
---

## Hvordan:
Bash har ikke en innebygd funksjon spesifikt for å sette stor bokstav i strenger, men du kan oppnå dette ved å bruke parameterutvidelse eller eksterne verktøy som `awk`. Her er noen måter å sette stor bokstav i en streng i Bash:

**Ved bruk av parameterutvidelse:**

Denne metoden manipulerer strengen direkte i skallet.

```bash
str="hello world"
capitalized="${str^}"
echo "$capitalized"
```
Utskrift:
```
Hello world
```

**Ved bruk av `awk`:**

`awk` er et kraftig tekstbehandlingsverktøy tilgjengelig på de fleste Unix-lignende operativsystemer, som kan benyttes for å sette stor bokstav i strenger.

```bash
str="hello world"
echo "$str" | awk '{print toupper(substr($0, 1, 1)) tolower(substr($0, 2))}'
```
Utskrift:
```
Hello world
```

**Ved bruk av `sed`:**

For en mer tradisjonell tilnærming kan `sed` benyttes for å sette stor bokstav i den første bokstaven av en streng. Men, det er litt mer komplekst sammenlignet med de tidligere metodene.

```bash
str="hello world"
echo "$str" | sed 's/./\u&/'
```
Utskrift:
```
Hello world
```

Disse kodene demonstrerer hvordan man setter stor forbokstav på den første bokstaven i en streng i Bash, og understreker fleksibiliteten til skripting i skallet når det gjelder tekstmanipulering.
