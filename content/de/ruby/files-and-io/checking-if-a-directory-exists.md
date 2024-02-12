---
title:                "Überprüfung, ob ein Verzeichnis existiert"
aliases:
- de/ruby/checking-if-a-directory-exists.md
date:                  2024-02-03T19:08:13.542914-07:00
model:                 gpt-4-0125-preview
simple_title:         "Überprüfung, ob ein Verzeichnis existiert"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/ruby/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Das Überprüfen, ob ein Verzeichnis in Ruby existiert, ermöglicht es Programmierern, die Präsenz eines Verzeichnisses zu verifizieren, bevor sie Operationen wie das Lesen von Dateien oder das Erstellen neuer Verzeichnisse durchführen. Dies ist entscheidend, um Fehler bei der Dateibehandlung zu vermeiden und die Zuverlässigkeit von Dateisystem-Manipulationen zu gewährleisten.

## Wie:
Die Standardbibliothek von Ruby bietet einfache Methoden, um die Existenz eines Verzeichnisses zu überprüfen. So machen Sie das mit reinem Ruby, ohne dass Sie Drittbibliotheken benötigen:

```ruby
require 'fileutils'

# Überprüfen, ob ein Verzeichnis existiert
if Dir.exist?('/pfad/zum/verzeichnis')
  puts 'Verzeichnis existiert.'
else
  puts 'Verzeichnis existiert nicht.'
end
```
Beispiel-Ausgabe:
```
Verzeichnis existiert.
```
Oder:
```
Verzeichnis existiert nicht.
```

Zusätzlich zur Verwendung von `Dir.exist?` können Sie auch die Methode `File.directory?` nutzen, die `true` zurückgibt, wenn der angegebene Pfad ein Verzeichnis ist:

```ruby
if File.directory?('/pfad/zum/verzeichnis')
  puts 'Verzeichnis existiert.'
else
  puts 'Verzeichnis existiert nicht.'
end
```
Sowohl `Dir.exist?` als auch `File.directory?` sind Teil der Standardbibliothek von Ruby und erfordern keine externen Gems, was sie zu bequemen und effizienten Optionen für die Überprüfung von Verzeichnissen macht.
