---
aliases:
- /nl/powershell/working-with-csv/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:08.959895-07:00
description: "Werken met CSV (Comma-Separated Values) omvat het omgaan met tekstgegevens\
  \ die door komma's zijn gesplitst in rijen en kolommen. Programmeurs werken met\u2026"
lastmod: 2024-02-18 23:09:02.116375
model: gpt-4-0125-preview
summary: "Werken met CSV (Comma-Separated Values) omvat het omgaan met tekstgegevens\
  \ die door komma's zijn gesplitst in rijen en kolommen. Programmeurs werken met\u2026"
title: Werken met CSV
---

{{< edit_this_page >}}

## Wat & Waarom?

Werken met CSV (Comma-Separated Values) omvat het omgaan met tekstgegevens die door komma's zijn gesplitst in rijen en kolommen. Programmeurs werken met CSV voor gegevensuitwisseling tussen programma's en systemen vanwege de eenvoud en brede ondersteuning.

## Hoe te:

### Een CSV-bestand importeren
```PowerShell
$data = Import-Csv -Path "pad\naar\uwbestand.csv"
$data
```
**Voorbeelduitvoer:**
```
Naam        Beroep       Locatie
----        ----------   --------
John Doe    Ontwikkelaar New York
Jane Smith  Analist      San Francisco
```

### Exporteren naar een CSV-bestand
```PowerShell
$data | Export-Csv -Path "pad\naar\nieuwbestand.csv" -NoTypeInformation
```
**Maakt "nieuwbestand.csv" met de gegevens van `$data`.**

### Een Rij Toevoegen aan CSV-gegevens
```PowerShell
$newRow = [PSCustomObject]@{
    Naam       = 'Emily Clark'
    Beroep     = 'Ontwerper'
    Locatie    = 'Austin'
}
$data += $newRow
$data | Export-Csv -Path "pad\naar\uwbestand.csv" -NoTypeInformation
```

### Specifieke Kolommen Selecteren
```PowerShell
$data | Select-Object Naam, Locatie
```
**Voorbeelduitvoer:**
```
Naam        Locatie
----        --------
John Doe    New York
Jane Smith  San Francisco
Emily Clark Austin
```

## Uitgediept

Historisch gezien hebben CSV-bestanden hun wortels in de vroege computertijd als een eenvoudige manier om tabelgegevens te organiseren zonder dat complexe bestandsformaten nodig zijn. Alternatieven, zoals XML en JSON, bieden rijkere gegevensstructuren, maar CSV blinkt uit voor tabelgegevens vanwege de leesbaarheid, lage overhead en het gemak van bewerking met eenvoudige teksteditors. In PowerShell omvatten de cmdlets `Import-Csv` en `Export-Csv` de implementatiedetails, waarbij de bestands-I/O en gegevensomzetting naar en van .NET-objecten worden afgehandeld.

## Zie Ook

- [PowerShell-documentatie over Import-Csv](https://docs.microsoft.com/nl-nl/powershell/module/microsoft.powershell.utility/import-csv)
- [PowerShell-documentatie over Export-Csv](https://docs.microsoft.com/nl-nl/powershell/module/microsoft.powershell.utility/export-csv)
