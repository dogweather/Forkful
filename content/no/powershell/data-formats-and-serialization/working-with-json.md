---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:37.316881-07:00
description: "PowerShells integrasjon med JSON (JavaScript Object Notation) handler\
  \ om parsing (lesing) og generering (skriving) av JSON-data, et vanlig format for\u2026"
lastmod: '2024-03-13T22:44:41.038305-06:00'
model: gpt-4-0125-preview
summary: "PowerShells integrasjon med JSON (JavaScript Object Notation) handler om\
  \ parsing (lesing) og generering (skriving) av JSON-data, et vanlig format for datautveksling\
  \ p\xE5 nettet."
title: Arbeider med JSON
weight: 38
---

## Hvordan:


### Parse JSON
For å lese eller parse JSON i PowerShell, kan du bruke `ConvertFrom-Json` cmdlet. Gitt en JSON-streng, konverterer denne cmdleten den til et PowerShell-objekt.

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

Eksempel på output:

```
John Doe
```

Dette eksemplet demonstrerer hvordan man parser en enkel JSON-streng for å få tilgang til egenskapene til det resulterende objektet.

### Generere JSON
For å generere JSON fra et PowerShell-objekt, kan du bruke `ConvertTo-Json` cmdlet. Dette er praktisk for å forberede data som skal sendes til en webtjeneste eller lagres i en konfigurasjonsfil.

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Angeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

Eksempel på output:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Angeles"
}
```

Dette kodeeksemplet lager et PowerShell-objekt og deretter konverterer det til en JSON-streng.
