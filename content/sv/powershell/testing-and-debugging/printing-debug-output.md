---
date: 2024-01-20 17:53:03.951997-07:00
description: "Att skriva ut fels\xF6kningsdata inneb\xE4r att visa tempor\xE4r information\
  \ f\xF6r att f\xF6rst\xE5 vad koden g\xF6r. Programmerare g\xF6r detta f\xF6r att\
  \ snabbt hitta och \xE5tg\xE4rda\u2026"
lastmod: '2024-03-13T22:44:38.128475-06:00'
model: gpt-4-1106-preview
summary: "Att skriva ut fels\xF6kningsdata inneb\xE4r att visa tempor\xE4r information\
  \ f\xF6r att f\xF6rst\xE5 vad koden g\xF6r."
title: "Skriva ut fels\xF6kningsdata"
weight: 33
---

## Så här gör du:
Använd `Write-Host` för enkel utskrift. För mer kontroll, använd `Write-Debug` eller `Write-Verbose` samt deras motsvarande inställningar.

```PowerShell
# Enkel utskrift med Write-Host
Write-Host "Här är något att titta på!"

# Aktiverar och använder Write-Debug
$DebugPreference = 'Continue'
Write-Debug "Det här är en debug-meddelande."

# Aktiverar och använder Write-Verbose
$VerbosePreference = 'Continue'
Write-Verbose "Det här är en verbose-meddelande."
```

Sample output:
```
Här är något att titta på!
DEBUG: Det här är en debug-meddelande.
VERBOSE: Det här är en verbose-meddelande.
```

## Fördjupning
I tidigare PowerShell-versioner användes `Write-Host` flitigt men det skapade problem då utskrifterna inte kunde fångas eller vidarebefordras. `Write-Debug` och `Write-Verbose` skapades för att ge kontroll och kunna sätta olika nivåer av loggning. Dessa kommandon är användbara när skripten blir mer komplexa. `Write-Debug` är bra för detaljer som endast är viktiga under utveckling medan `Write-Verbose` är till för att ge användbara körtidsinformation.

## Se även
- Microsofts dokumentation över Write-Host: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-host
- Officiell hjälp om about_Preference_Variables: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables
