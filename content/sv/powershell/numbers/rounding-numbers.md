---
date: 2024-01-26 03:46:31.386364-07:00
description: "Att avrunda tal handlar om att justera ett v\xE4rde till n\xE4rmaste\
  \ heltal eller angiven decimalplats. Programmerare avrundar tal f\xF6r att f\xF6\
  renkla data,\u2026"
lastmod: '2024-03-13T22:44:38.119159-06:00'
model: gpt-4-0125-preview
summary: "Att avrunda tal handlar om att justera ett v\xE4rde till n\xE4rmaste heltal\
  \ eller angiven decimalplats."
title: Avrundning av tal
weight: 13
---

## Hur man gör:
Du har några praktiska cmdlet:er och metoder i PowerShell för avrundning:

- `Round()`-metod från Math-klassen
```PowerShell
[Math]::Round(15.68) # Avrundar till 16
```
- Specificera decimaler:
```PowerShell
[Math]::Round(15.684, 2) # Avrundar till 15.68
```
- `Ceiling()` och `Floor()`, för att alltid avrunda uppåt eller nedåt:
```PowerShell
[Math]::Ceiling(15.2) # Avrundar upp till 16
[Math]::Floor(15.9) # Avrundar ned till 15
```

## Fördjupning
Avrundning av tal är ingen nykomling; det har funnits sedan antiken, användbart för handel, vetenskap och tidsmätning. När vi pratar om PowerShell följer `[Math]::Round()` som standard "Bankers avrundning", där 0.5 går till det närmaste jämna talet, vilket minskar bias i statistiska operationer.

Du är inte bara begränsad till `[Math]`-metoder. Vill du ha mer kontroll? Kolla in `[System.Math]::Round(Number, Digits, MidpointRounding)` där du kan ställa in hur mittpunkter hanteras: bort från noll eller mot jämnt (även kallat Bankers avrundning).

En annan vinkel: objektet `System.Globalization.CultureInfo`. Det hjälper med lokalanpassad formatering och avrundningspreferenser när du hanterar internationella tal.

## Se också
- Microsofts officiella dokumentation om Math-metoder: [Länk](https://learn.microsoft.com/sv-se/dotnet/api/system.math?view=net-7.0)
- Specificitet gällande avrundning av decimaler i .NET: [Länk](https://learn.microsoft.com/sv-se/dotnet/api/system.midpointrounding?view=net-7.0)
- Diskussioner om avrundning på StackOverflow: [Länk](https://stackoverflow.com/questions/tagged/rounding+powershell)
