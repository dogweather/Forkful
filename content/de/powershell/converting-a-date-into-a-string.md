---
title:                "Datum in einen String umwandeln"
date:                  2024-01-20T17:37:16.432071-07:00
model:                 gpt-4-1106-preview
simple_title:         "Datum in einen String umwandeln"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/powershell/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Umwandeln eines Datums in einen String ermöglicht es uns, das Datum in einem benutzerfreundlichen oder spezifischen Format zu präsentieren. Programmierer tun dies oft für Log-Dateien, Benutzeroberflächen oder beim Exportieren von Daten.

## So geht's:
```PowerShell
# Aktuelles Datum im Standardformat bekommen
$Heute = Get-Date
$HeuteString = $Heute.ToString()
Write-Output $HeiteString

# Spezifisches Format: YYYY-MM-DD
$HeuteStringFormatiert = $Heute.ToString("yyyy-MM-dd")
Write-Output $HeuteStringFormatiert

# Angepasstes Format: Tag.Monat.Jahr Stunde:Minute
$IndividuellesFormat = $Heute.ToString("dd.MM.yyyy HH:mm")
Write-Output $IndividuellesFormat
```
Sample Output:
```
Mittwoch, 2. Mai 2023 12:34:56
2023-05-02
02.05.2023 12:34
```

## Deep Dive
Ursprünglich hatten Computer Mühe mit der Interpretation von Daten und Zeiten, da diese menschliche Konstrukte sind. Um eine universelle Handhabung zu gewährleisten, wurden Standardformate entwickelt. Das Formatieren von Datumswerten zu Strings ist besonders wichtig für die Internationalisierung, da unterschiedliche Kulturen Datumsangaben unterschiedlich darstellen. 

PowerShell verwendet die .NET-Framework-Klasse [DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime?view=net-7.0) für Datum- und Zeitoperationen. Mit der `ToString()`-Methode und Formatparametern können wir präzise steuern, wie das Datum als Text dargestellt wird. Es gibt auch die Möglichkeit, kultur-spezifische Formate mit der `CultureInfo`-Klasse zu verwenden.

Alternativ könnte man die `Get-Date`-Cmdlet's `-Format` Parameter nutzen:
```PowerShell
$FormatiertesDatum = Get-Date -Format "dd.MM.yyyy HH:mm"
Write-Output $FormatiertesDatum
```

## Siehe Auch
- Microsoft Docs zu [Get-Date](https://docs.microsoft.com/de-de/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.0)
- Microsoft Docs zu [DateTime-Klasse](https://docs.microsoft.com/de-de/dotnet/api/system.datetime?view=net-7.0)
- Artikel zur [Internationalisierung von Datums- und Zeitformaten in .NET](https://docs.microsoft.com/de-de/dotnet/standard/base-types/custom-date-and-time-format-strings)
