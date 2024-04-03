---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:34.599150-07:00
description: "Integracja PowerShell z JSON (JavaScript Object Notation) dotyczy parsowania\
  \ (odczytu) oraz generowania (zapisu) danych JSON, co jest powszechnym formatem\u2026"
lastmod: '2024-03-13T22:44:35.651312-06:00'
model: gpt-4-0125-preview
summary: Integracja PowerShell z JSON (JavaScript Object Notation) dotyczy parsowania
  (odczytu) oraz generowania (zapisu) danych JSON, co jest powszechnym formatem wymiany
  danych w sieci.
title: Praca z JSON
weight: 38
---

## Jak to zrobić:


### Parsowanie JSON
Aby odczytać lub sparsować JSON w PowerShell, można użyć polecenia `ConvertFrom-Json`. Dla danego ciągu JSON, to polecenie przekształca go w obiekt PowerShell. 

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

Przykładowe wyjście:

```
John Doe
```

Ten przykład pokazuje, jak sparsować prosty ciąg JSON, aby uzyskać dostęp do właściwości wynikowego obiektu.

### Generowanie JSON
Aby wygenerować JSON z obiektu PowerShell, można użyć polecenia `ConvertTo-Json`. Jest to przydatne do przygotowania danych do wysłania do usługi sieciowej lub zapisania do pliku konfiguracyjnego.

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Angeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

Przykładowe wyjście:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Angeles"
}
```

Ten fragment kodu tworzy obiekt PowerShell, a następnie przekształca go na ciąg JSON.
