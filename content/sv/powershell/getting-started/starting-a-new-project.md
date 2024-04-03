---
date: 2024-01-20 18:04:14.252299-07:00
description: "Starta ett nytt projekt inneb\xE4r att skapa en grund f\xF6r all kod\
  \ som kommer. Programmerare g\xF6r detta f\xF6r att organisera och definiera ramar\
  \ f\xF6r deras\u2026"
lastmod: '2024-03-13T22:44:38.126656-06:00'
model: gpt-4-1106-preview
summary: "Starta ett nytt projekt inneb\xE4r att skapa en grund f\xF6r all kod som\
  \ kommer."
title: "Att p\xE5b\xF6rja ett nytt projekt"
weight: 1
---

## Så här gör du:
För att sparka igång ett nytt PowerShell-projekt, kan du börja med att skapa en ny katalog och initialisera en git-repository för versionshantering. Använd `New-Item` för att skapa nya filer, som ett grundläggande skript eller en manifestfil för moduler.

```PowerShell
# Skapa ny katalog 
New-Item -Path 'C:\MyNewProject' -ItemType Directory

# Gå in i katalogen
Set-Location -Path 'C:\MyNewProject'

# Initialisera en ny git-repository 
git init

# Skapa en ny PowerShell-skriptfil
New-Item -Path 'C:\MyNewProject' -Name 'StartScript.ps1' -ItemType File

# Visa innehållet i katalogen
Get-ChildItem -Path 'C:\MyNewProject'
```

## Fördjupning:
Projektstrukturering i PowerShell blev mer relevant med introduktionen av PowerShell-moduler. Moduler består av skript, binära filer och manifest som gör det enklare att dela och återanvända kod. Historiskt har PowerShell bytt fokus från en ren kommando-orienterad miljö till ett mer skript- och utvecklingsorienterat språk. Alternativ till PowerShell för projektstart inkluderar bash-skript för Linux eller batch-filer för Windows. Vikten av versionhantering med verktyg som Git är central i dagens utvecklingssammanhang.

## Se även:
- [Pro Git book](https://git-scm.com/book/en/v2)
