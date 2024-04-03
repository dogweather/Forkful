---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:34.371036-07:00
description: "\xC5 jobbe med JSON i Bash-programmering inneb\xE6rer parsing, uttrekking\
  \ og manipulering av JSON-data direkte fra kommandolinjen. Programmerere gj\xF8\
  r ofte dette\u2026"
lastmod: '2024-03-13T22:44:40.995970-06:00'
model: gpt-4-0125-preview
summary: "\xC5 jobbe med JSON i Bash-programmering inneb\xE6rer parsing, uttrekking\
  \ og manipulering av JSON-data direkte fra kommandolinjen."
title: Arbeider med JSON
weight: 38
---

## Hvordan:
Bash selv mangler innebygd JSON-parsingkapasitet, men `jq` er en kraftig kommandolinje JSON-prosessor som fyller dette gapet. Her er hvordan du bruker den:

**Lese en JSON-fil:**

Eksempel `data.json`:
```json
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "location": {
    "city": "New York",
    "country": "USA"
  }
}
```

For å lese og trekke ut navnet fra JSON-filen:
```bash
jq '.name' data.json
```
Output:
```
"Jane Doe"
```

**Modifisere JSON-data:**

For å oppdatere byen til "Los Angeles" og skrive tilbake til filen:
```bash
jq '.location.city = "Los Angeles"' data.json > temp.json && mv temp.json data.json
```

**Parse JSON fra en variabel:**

Hvis du har JSON i en Bash-variabel, kan `jq` fortsatt behandle den:
```bash
json_string='{"name": "John Doe", "email": "john@example.com"}'
echo $json_string | jq '.name'
```
Output:
```
"John Doe"
```

**Jobbe med tabeller:**

Gitt en tabell med elementer i JSON:
```json
{
  "items": ["apple", "banana", "cherry"]
}
```

For å trekke ut det andre elementet (indeksering starter på 0):
```bash
jq '.items[1]' data.json
```
Output:
```
"banana"
```

For mer komplekse operasjoner og filtrering, har `jq` en omfattende håndbok og opplæringsprogrammer tilgjengelig på nettet, noe som gjør den til et allsidig verktøy for alle dine Bash/JSON-behov.
