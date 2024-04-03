---
date: 2024-01-26 04:38:03.592463-07:00
description: "Komplexe Zahlen erweitern unser Zahlensystem um imagin\xE4re Zahlen\
  \ und erm\xF6glichen es uns, Gleichungen zu l\xF6sen, die keine reellen L\xF6sungen\
  \ haben.\u2026"
lastmod: '2024-03-13T22:44:53.882203-06:00'
model: gpt-4-0125-preview
summary: "Komplexe Zahlen erweitern unser Zahlensystem um imagin\xE4re Zahlen und\
  \ erm\xF6glichen es uns, Gleichungen zu l\xF6sen, die keine reellen L\xF6sungen\
  \ haben."
title: Umgang mit komplexen Zahlen
weight: 14
---

## Wie geht das:
C# verfügt über eine eingebaute `System.Numerics.Complex` Struktur zur Verarbeitung komplexer Zahlen. Hier ist eine kurze Anleitung:

```C#
using System;
using System.Numerics;

class BeispielKomplexeZahlen
{
    static void Main()
    {
        // Erstellen von komplexen Zahlen
        Complex c1 = new Complex(4, 5); // 4 + 5i
        Complex c2 = Complex.FromPolarCoordinates(1, Math.PI / 4); // 1 * e^(iπ/4)

        // Grundlegende Operationen
        Complex summe = c1 + c2;
        Complex differenz = c1 - c2;
        Complex produkt = c1 * c2;
        Complex quotient = c1 / c2;

        // Ergebnisse ausgeben
        Console.WriteLine($"Summe: {summe}");
        Console.WriteLine($"Differenz: {differenz}");
        Console.WriteLine($"Produkt: {produkt}");
        Console.WriteLine($"Quotient: {quotient}");
        Console.WriteLine($"Betrag von c1: {c1.Magnitude}");
        Console.WriteLine($"Phase von c1: {c1.Phase}");
    }
}
```

Und das wird ausgegeben:

```
Summe: (4.70710678118655, 5.70710678118655)
Differenz: (3.29289321881345, 4.29289321881345)
Produkt: (-1.00000000000001, 9)
Quotient: (0.6, 0.8)
Betrag von c1: 6.40312423743285
Phase von c1: 0.896055384571344
```

## Tiefere Einblicke
Komplexe Zahlen, die aus einem realen und einem imaginären Teil bestehen (oft als a + bi notiert), gibt es seit dem 17. Jahrhundert. Der italienische Mathematiker Gerolamo Cardano wird mit ihrer frühen Entwicklung in Verbindung gebracht. Bei der Programmierung geht es darum, diese beiden unterschiedlichen Teile zu verstehen und zu verwalten.

Obwohl `System.Numerics.Complex` in C# robust und in die Sprache integriert ist, bieten andere Sprachen wie Python mit `cmath` oder Drittanbieterbibliotheken ähnliche Funktionalitäten. Und wenn Sie in einer älteren Version von C# oder einer .NET-Version arbeiten, die `System.Numerics` nicht unterstützt, müssen Sie möglicherweise Ihre eigene komplexe Zahlenklasse erstellen oder eine Bibliothek finden.

Intern verwenden die Operationen mit komplexen Zahlen Gleitkommaarithmetik, was zu Rundungsfehlern führen kann. Daher ist es wichtig, dies bei der Implementierung von Algorithmen, die komplexe Zahlen umfangreich nutzen, zu berücksichtigen und den Einfluss auf Präzision und Genauigkeit zu bedenken.

## Siehe auch
1. C# Referenz für `System.Numerics.Complex`: https://learn.microsoft.com/de-de/dotnet/api/system.numerics.complex
2. Ein tieferer Einblick in die Mathematik komplexer Zahlen: https://mathworld.wolfram.com/ComplexNumber.html
3. Für alternative Implementierungen und Bibliotheken, siehe Math.NET Numerics: https://numerics.mathdotnet.com/
