---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:05.816405-07:00
description: "Das \xDCberpr\xFCfen, ob ein Verzeichnis in Elixir existiert, bezieht\
  \ sich darauf, die Anwesenheit eines Verzeichnisses an einem bestimmten Pfad im\
  \ Dateisystem\u2026"
lastmod: '2024-03-13T22:44:53.549918-06:00'
model: gpt-4-0125-preview
summary: "Das \xDCberpr\xFCfen, ob ein Verzeichnis in Elixir existiert, bezieht sich\
  \ darauf, die Anwesenheit eines Verzeichnisses an einem bestimmten Pfad im Dateisystem\
  \ zu verifizieren."
title: "\xDCberpr\xFCfung, ob ein Verzeichnis existiert"
weight: 20
---

## Wie:
Die Standardbibliothek von Elixir bietet eine unkomplizierte Möglichkeit, die Existenz eines Verzeichnisses über das `File` Modul zu überprüfen. Hier ist, wie Sie es nutzen können:

```elixir
if File.dir?("path/to/directory") do
  IO.puts "Verzeichnis existiert!"
else
  IO.puts "Verzeichnis existiert nicht."
end
```

Beispieloutput, unter der Annahme, dass das Verzeichnis nicht existiert:
```
Verzeichnis existiert nicht.
```

Für fortgeschrittenere Interaktionen mit dem Dateisystem, einschließlich der Überprüfung der Existenz von Verzeichnissen, könnten Sie darüber nachdenken, Drittanbieterbibliotheken wie `FileSystem` zu verwenden. Obwohl die Standardfähigkeiten von Elixir für viele Fälle ausreichen, kann `FileSystem` eine nuanciertere Kontrolle und Rückmeldung für komplexe Anwendungen bieten. Jedoch ist für das grundlegende Bedürfnis, zu überprüfen, ob ein Verzeichnis existiert, das Festhalten am nativen `File` Modul in der Regel empfohlen, da es sofort verfügbar ist und keine externen Abhängigkeiten erfordert.
