---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:13.191332-07:00
description: "I PowerShell \xE4r kontrollen om en katalog finns en vanlig uppgift\
  \ som hj\xE4lper skript att fatta beslut baserat p\xE5 filsystemets struktur\u2014\
  till exempel f\xF6r att\u2026"
lastmod: '2024-03-13T22:44:38.140085-06:00'
model: gpt-4-0125-preview
summary: "I PowerShell \xE4r kontrollen om en katalog finns en vanlig uppgift som\
  \ hj\xE4lper skript att fatta beslut baserat p\xE5 filsystemets struktur\u2014till\
  \ exempel f\xF6r att undvika fel genom att bekr\xE4fta att en m\xE5lkatalog finns\
  \ p\xE5 plats innan man f\xF6rs\xF6ker l\xE4sa fr\xE5n eller skriva till den."
title: Kontrollera om en katalog existerar
weight: 20
---

## Hur man gör:
PowerShell erbjuder ett enkelt sätt att kontrollera närvaron av en katalog med hjälp av cmdleten `Test-Path`. Denna cmdlet returnerar ett booleskt värde som indikerar om den angivna sökvägen finns. Så här kan du använda den:

```powershell
# Kontrollera om en katalog finns
$directoryPath = "C:\ExamplePath"
$directoryExists = Test-Path -Path $directoryPath
Write-Output "Finns katalogen? $directoryExists"
```

Exempelutskrift för en katalog som finns:

```
Finns katalogen? True
```

Och för en katalog som inte finns:

```
Finns katalogen? False
```

För mer komplexa skript, särskilt de som interagerar med nätverksdelningar eller molnlagring, kan du behöva ytterligare kontroller eller funktionalitet som inte direkt är tillgänglig genom `Test-Path`. I sådana fall kan det vara fördelaktigt att använda tredjepartsmoduleller eller bibliotek för PowerShell, även om de flesta rutinuppgifter kan utföras med PowerShell:s inbyggda cmdlets. Fram till min sista kunskapsuppdatering har det inte funnits något allmänt accepterat tredjepartsbibliotek specifikt för att kontrollera katalogexistens bortom vad `Test-Path` erbjuder, främst eftersom `Test-Path` i sig är både robust och effektivt för detta ändamål.
