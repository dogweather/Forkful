---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:31.959069-07:00
description: "Regul\xE4re Ausdr\xFCcke (regex) sind Zeichenfolgen, die ein Suchmuster\
  \ bilden, das haupts\xE4chlich f\xFCr die Stringsuche und -manipulation verwendet\
  \ wird.\u2026"
lastmod: '2024-03-13T22:44:54.091625-06:00'
model: gpt-4-0125-preview
summary: "Regul\xE4re Ausdr\xFCcke (regex) sind Zeichenfolgen, die ein Suchmuster\
  \ bilden, das haupts\xE4chlich f\xFCr die Stringsuche und -manipulation verwendet\
  \ wird."
title: "Regul\xE4re Ausdr\xFCcke verwenden"
weight: 11
---

## Wie geht das:
In PowerShell können Sie die Operatoren `-match`, `-replace` und `-split` unter anderen verwenden, um Aktionen mit regulären Ausdrücken durchzuführen. Lassen Sie uns einige Beispiele erkunden:

### Verwendung von `-match` um zu prüfen, ob ein String einem Muster entspricht
Dieser Operator gibt `$true` zurück, wenn das Muster innerhalb des Strings gefunden wird, und andernfalls `$false`.

```powershell
"hello world" -match "\w+orld"
# Ausgabe: Wahr
```

### Extrahieren von Treffern
Sie können den abgeglichenen Wert abrufen, indem Sie auf die automatische Variable `$matches` zugreifen.

```powershell
if ("I have 100 apples" -match "\d+") {
    "Gefundene Zahl: " + $matches[0]
}
# Ausgabe: Gefundene Zahl: 100
```

### Verwendung von `-replace` für Substitutionen
Der `-replace` Operator ersetzt alle Vorkommen eines Musters mit einem angegebenen Ersatzstring.

```powershell
"foo bar baz" -replace "ba[rz]", "qux"
# Ausgabe: foo qux qux
```

### Aufteilen von Strings mit `-split`
Teilt einen String in ein Array von Teilstrings basierend auf einem regex-Muster auf.

```powershell
"The quick-brown_fox jumps" -split "[-_ ]"
# Ausgabe: The quick brown fox jumps
```

### Fortgeschrittenes Musterabgleichen
PowerShell unterstützt auch komplexere regex-Operationen über die `[regex]` Klasse, die Ihnen Zugriff auf Methoden wie `Matches()`, `Replace()` und `Split()` gibt.

```powershell
[regex]::Matches("June 24, August 9, Dec 12", "\b[A-Za-z]+\b").Value
# Ausgabe: June August Dec

[regex]::Replace("100,000", "\B(?=(?:\d{3})+(?!\d))", ",")
# Ausgabe: 100,000

[regex]::Split("one,two;three four", ",|;| ")
# Ausgabe: one two three four
```

Diese Beispiele zeigen die Kraft und Vielseitigkeit von regulären Ausdrücken in PowerShell für die Datenmanipulation und das Musterabgleichen. Durch die Nutzung von regex können Programmierer komplexe Textverarbeitungen effizient durchführen.
