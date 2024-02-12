---
title:                "Arbeta med JSON"
aliases:
- /sv/powershell/working-with-json/
date:                  2024-02-03T19:23:35.086469-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeta med JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/powershell/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

PowerShells integration med JSON (JavaScript Object Notation) handlar om att tolka (läsa) och generera (skriva) JSON-data, ett gemensamt format för datautbyte på webben. Programmerare arbetar med JSON för att interagera med webb-API:er, konfigurationsfiler eller för att underlätta datautbyte mellan olika språk och plattformar på grund av dess lätta vikt och språkoberoende natur.

## Hur man:

### Tolka JSON

För att läsa eller tolka JSON i PowerShell kan du använda `ConvertFrom-Json` cmdleten. Givet en JSON-sträng konverterar denna cmdlet den till ett PowerShell-objekt.

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

Exempel på utdata:

```
John Doe
```

Detta exempel demonstrerar hur man tolkar en enkel JSON-sträng för att komma åt egenskaper hos det resulterande objektet.

### Generera JSON

För att generera JSON från ett PowerShell-objekt kan du använda cmdleten `ConvertTo-Json`. Detta är praktiskt för att förbereda data som ska skickas till en webbtjänst eller sparas i en konfigurationsfil.

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Angeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

Exempel på utdata:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Angeles"
}
```

Detta kodstycke skapar ett PowerShell-objekt och konverterar det sedan till en JSON-sträng.
