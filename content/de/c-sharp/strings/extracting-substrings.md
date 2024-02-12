---
title:                "Teilstrings extrahieren"
aliases:
- de/c-sharp/extracting-substrings.md
date:                  2024-01-20T17:45:27.032258-07:00
model:                 gpt-4-1106-preview
simple_title:         "Teilstrings extrahieren"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/c-sharp/extracting-substrings.md"
---

{{< edit_this_page >}}

## Was & Warum?

Das Extrahieren von Teilzeichenketten greift bestimmte Abschnitte aus einer längeren Zeichenkette heraus. Programmierer tun das, um Daten zu analysieren, zu verarbeiten oder spezifische Informationen darzustellen.

## So geht's:

```C#
using System;

class SubstringExample {
    static void Main() {
        string phrase = "C# macht Spaß!";
        string sub = phrase.Substring(3, 5); // Nimmt "macht" heraus
        
        Console.WriteLine(sub); // Ausgabe: macht
    }
}
```

Weitere Methoden:

```C#
using System;

class MoreSubstringExamples {
    static void Main() {
        string text = "Hallo Welt, hier ist C#!";
        
        // Von Start bis Ende
        string startToEnd = text.Substring(6); // Ergebnis: "Welt, hier ist C#!"
        Console.WriteLine(startToEnd);
        
        // Manipulieren und Teilstring extrahieren
        string replaceAndSubstring = text.Replace("Welt", "Programmierer").Substring(0, 15);
        Console.WriteLine(replaceAndSubstring); // Ausgabe: Hallo Programmierer
    }
}
```

## Tiefgang:

Teilzeichenketten zu extrahieren ist keine neue Idee. Schon frühe Programmiersprachen boten ähnliche Funktionen. Der `.Substring()`-Methode in C# könnte man vorhalten, dass sie nicht die modernste oder effizienteste Art ist, Teilstrings zu managen. 

Es gibt Alternativen: `Span<T>` und `Memory<T>` aus C# 7.2 bieten performantere Zugriffe auf Teile einer Zeichenkette ohne zusätzliche Speicherzuweisung. Das kann besonders bei großen Textmengen oder in performancekritischen Anwendungen hilfreich sein.

Bei der Implementierung ist zu beachten, dass `Substring()` bei ungültigen Indizes eine `ArgumentOutOfRangeException` wirft. Vorsicht also bei dynamischen Daten!

## Siehe Auch:

- Microsoft Dokumentation zu `String.Substring` Method: [docs.microsoft.com](https://docs.microsoft.com/en-us/dotnet/api/system.string.substring)
- Performance-Überlegungen zu `Span<T>` und `Memory<T>`: [docs.microsoft.com](https://docs.microsoft.com/en-us/dotnet/api/system.memory-1)
- StackOverflow Diskussionen über Substrings in C#: [stackoverflow.com](https://stackoverflow.com/questions/tagged/substring+c%23)
