---
date: 2024-01-20 17:47:03.985386-07:00
description: "Die L\xE4nge eines Strings zu bestimmen bedeutet, die Anzahl der Zeichen\
  \ zu z\xE4hlen, die er enth\xE4lt. Das ist n\xFCtzlich, um Text zu verarbeiten,\
  \ Grenzen zu\u2026"
lastmod: '2024-03-13T22:44:53.879375-06:00'
model: gpt-4-1106-preview
summary: "Die L\xE4nge eines Strings zu bestimmen bedeutet, die Anzahl der Zeichen\
  \ zu z\xE4hlen, die er enth\xE4lt."
title: "Ermittlung der Zeichenkettenl\xE4nge"
weight: 7
---

## Anleitung:
Um die Länge eines Strings in C# zu bekommen, verwenden wir die `Length`-Eigenschaft. Sieh dir das Beispiel an:

```C#
string beispiel = "Hallo Welt";
Console.WriteLine(beispiel.Length);  // Gibt die Länge aus: 10
```

Ausgabe:

```
10
```

## Tiefergehende Einblicke:
Die `.Length`-Eigenschaft gibt es in C# seit der ersten Version. Sie gibt einen `int` zurück, der die Anzahl der `char`-Elemente im String anzeigt. Da `.Length` eine Eigenschaft ist, erfolgt der Zugriff schnell und effizient, ohne dass der String durchlaufen werden muss. Alternative Methoden, wie etwa die Verwendung eines For-Loops, um manuell die Zeichen zu zählen, sind unnötig und ineffizient. In der Unicode-Welt kann die Länge irreführend sein, da einige Zeichen als mehrere `char`-Instanzen repräsentiert werden – das aber nur als Randnote.

## Siehe Auch:
- Microsoft-Dokumentation zur `Length`-Eigenschaft: [Microsoft Docs: String.Length Property](https://docs.microsoft.com/en-us/dotnet/api/system.string.length)
- Ein Artikel zur Unicode-Verarbeitung in C#: [Understanding Characters, Strings and Encoding in .NET](https://www.codeproject.com/Articles/17201/Understanding-Characters-Strings-and-Encoding-in-N)
- Stack Overflow Diskussionen zur String-Längenbestimmung: [Stack Overflow: How to get the length of a string](https://stackoverflow.com/questions/228038/best-way-to-reverse-a-string)
