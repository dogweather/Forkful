---
date: 2024-01-26 01:11:47.603171-07:00
description: "Code in Funktionen zu organisieren bedeutet, Codeabschnitte, die spezifische\
  \ Aufgaben erf\xFCllen, zusammenzufassen und ihnen einen Namen zu geben. Dies wird\u2026"
lastmod: '2024-03-13T22:44:54.109471-06:00'
model: gpt-4-1106-preview
summary: "Code in Funktionen zu organisieren bedeutet, Codeabschnitte, die spezifische\
  \ Aufgaben erf\xFCllen, zusammenzufassen und ihnen einen Namen zu geben."
title: Code in Funktionen organisieren
weight: 18
---

## Wie geht das:
Lassen Sie uns eine Funktion schreiben, um die Summe von zwei Zahlen zu berechnen. Einfach, aber es veranschaulicht den Punkt.

```PowerShell
function Add-Numbers {
    param (
        [int]$FirstNum,
        [int]$SecondNum
    )
    return $FirstNum + $SecondNum
}

# Die Funktion mit 5 und 10 aufrufen
$sum = Add-Numbers -FirstNum 5 -SecondNum 10
Write-Output "Die Summe ist $sum"
```

Beispielausgabe:

```
Die Summe ist 15
```

## Tiefere Einblicke
Funktionen in PowerShell, wie in den meisten Sprachen, sind nichts Neues. Wir haben Code seit den Tagen von Fortran kompartimentiert. Es geht darum, 'das Rad nicht neu zu erfinden'. Alternativen? Sicher, Skripte oder Cmdlets. Aber ihnen fehlt die Sauberkeit und Kontextsensitivität von Funktionen innerhalb von Skripten.

Implementierung? Funktionen können grundlegend sein wie unser Beispiel oder komplex mit Bereichen, Pipeline-Eingaben und mehr. Nehmen Sie `Advanced Functions`. Sie ahmen Cmdlets nach, mit Parametern, die Attribute haben, wie z.B. `[Parameter(Mandatory=$true)]`. Das ist ein Vorgeschmack auf die Flexibilität von PowerShell.

## Siehe auch
- [about_Functions_Advanced_Parameters](https://docs.microsoft.com/de-de/powershell/module/microsoft.powershell.core/about/about_functions_advanced_parameters?view=powershell-7.1)
- [about_Script_Blocks](https://docs.microsoft.com/de-de/powershell/module/microsoft.powershell.core/about/about_script_blocks?view=powershell-7.1)
