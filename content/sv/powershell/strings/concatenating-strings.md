---
date: 2024-01-20 17:35:26.032386-07:00
description: "Sammanslagning av str\xE4ngar inneb\xE4r att kl\xE4mma ihop tv\xE5 eller\
  \ fler textbitar till en. Programmerare g\xF6r detta f\xF6r att bygga meningar,\
  \ skapa dynamiska\u2026"
lastmod: '2024-03-13T22:44:38.116094-06:00'
model: gpt-4-1106-preview
summary: "Sammanslagning av str\xE4ngar inneb\xE4r att kl\xE4mma ihop tv\xE5 eller\
  \ fler textbitar till en."
title: "Sammanslagning av str\xE4ngar"
weight: 3
---

## Hur gör man:
Concatenering är enkelt i PowerShell. Använd plus-tecknet (+) eller den inbyggda -join operatorn.

```PowerShell
# Med plus-tecknet
$greeting = "Hej, " + "värld!"
Write-Output $greeting

# Resultat: Hej, värld!

# Med -join
$words = "PowerShell", "är", "kul!"
$sentence = $words -join " "
Write-Output $sentence

# Resultat: PowerShell är kul!
```

## Djupdykning:
Historiskt sett har strängsammanslagning varit centralt i många programmeringsspråk. I PowerShell har det alltid varit lätt med hjälp av '+' operatören. Effektivitetsmässigt kan stora mängder sammanslagningar leda till prestandaproblem då varje operation skapar en ny sträng i minnet. Alternativ till -join och '+' inkluderar `StringBuilder` i .NET, vilket PowerShell kan utnyttja när man jobbar med mycket stora strängar för bättre prestanda. Däremot är `StringBuilder` överkurs för de flesta script och enkla sammanslagningar.
