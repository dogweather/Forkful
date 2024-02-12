---
title:                "Een tekstbestand lezen"
aliases:
- nl/powershell/reading-a-text-file.md
date:                  2024-01-28T22:04:56.663855-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een tekstbestand lezen"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/powershell/reading-a-text-file.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Een tekstbestand lezen betekent de inhoud ervan ophalen in een vorm waar je programma mee kan werken. Programmeurs doen dit voor gegevensverwerking, configuratie, loggen – altijd wanneer een bestand voor mensen leesbaar betrokken is.

## Hoe:
Laten we beginnen met de basis! Zo lees je uit een tekstbestand in PowerShell:

```PowerShell
# Haal de inhoud van een bestand op
$content = Get-Content -Path "C:\pad\naar\jouw\bestand.txt"
# Toon de inhoud in de console
Write-Output $content
```

Een voorbeelduitvoer zou er zo uit kunnen zien als je bestand een paar regels tekst bevatte:
```
Hallo, PowerShell!
Einde van bestand.
```

Wil je nu regel voor regel lezen?

```PowerShell
# Lees het bestand regel voor regel
$lines = Get-Content -Path "C:\pad\naar\jouw\bestand.txt" -ReadCount 0
foreach ($line in $lines) {
    Write-Output $line
}
```

Zelfde voorbeelduitvoer als hierboven, maar één regel tegelijk verwerkt.

## Diepere duik
Lang voor PowerShell waren command-line tools zoals `cat` in UNIX-achtige systemen of `type` in DOS de standaard voor het lezen van bestanden. Get-Content van PowerShell is het scherpe gereedschap hiervoor vandaag de dag, met extra voordelen zoals regel-voor-regellezen, wat helpt om geheugenoverbelasting bij enorme bestanden te voorkomen.

Naast `Get-Content`, hebben we `.NET`-klassen tot onze beschikking voor meer controle – maak kennis met `System.IO.StreamReader`:

```PowerShell
$stream = [System.IO.StreamReader] "C:\pad\naar\jouw\bestand.txt"
try {
    while ($line = $stream.ReadLine()) {
        Write-Output $line
    }
}
finally {
    $stream.Close()
}
```

Dit is een meer geheugenefficiënte methode, nuttig voor enorme tekstbergen.

Alternatieven? Nou, je zou `Import-Csv` kunnen gebruiken voor CSV-bestanden of `ConvertFrom-Json` voor JSON als je gegevens in gestructureerde objecten wilt scheppen. Maar blijf bij `Get-Content` voor het ruwe tekstwerk.

## Zie Ook
Bekijk de officiële documentatie voor meer schatten:

- [Get-Content Documentatie](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content)
- [Over Automatische Variabelen](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_automatic_variables) - Dit geeft inzicht in variabelen zoals `$_`, die handig kunnen zijn voor inline verwerking.
- [PowerShell's .NET-mogelijkheden gebruiken](https://docs.microsoft.com/en-us/powershell/scripting/developer/hosting/adding-and-invoking-commands?view=powershell-7.1) - Voor diegenen die dieper duiken in het .NET-framework binnen PowerShell.
