---
date: 2024-01-20 17:56:27.305696-07:00
description: "Kommandolinjeargumenter lar brukere gi input til et skript n\xE5r de\
  \ kj\xF8rer det. Programmerere bruker dette for \xE5 lage fleksible og tilpassbare\
  \ scripts."
lastmod: '2024-03-13T22:44:41.032519-06:00'
model: gpt-4-1106-preview
summary: "Kommandolinjeargumenter lar brukere gi input til et skript n\xE5r de kj\xF8\
  rer det."
title: Lese kommandolinjeargumenter
weight: 23
---

## Hvordan:
```PowerShell
# script.ps1
param(
    [string]$name,
    [int]$age
)

Write-Host "Hei, $name! Du er $age år gammel."
```
Kjør scriptet:
```PowerShell
PS > .\script.ps1 -name "Ola" -age 28
```
Forventet output:
```
Hei, Ola! Du er 28 år gammel.
```

## Dypdykk
Kommandolinjeargumenter har vært en standard for brukerinput siden tidlige dager av programmering. I PowerShell, spesifiseres de ved å bruke `param`-blokken øverst i skriptene. Alternativer til `param` inkluderer `$args`-arrayet for en mer dynamisk, men mindre eksplisitt tilnærming. PowerShell-script kan også samhandle direkte med brukeren under kjøring gjennom cmdlets som `Read-Host`. Men å lese kommandolinjeargumenter fører til mindre brukerinteraksjon og kan lett integreres i automatiserte prosesser.

## Se Også
- Offisielle PowerShell dokumentasjonen på argumenter: [about_Functions_CmdletBindingAttribute](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_Functions_CmdletBindingAttribute)
- En grundig guide om PowerShell parametre: [about_Functions_Advanced_Parameters](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_Functions_Advanced_Parameters)
