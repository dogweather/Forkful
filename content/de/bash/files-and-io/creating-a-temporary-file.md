---
title:                "Erstellung einer temporären Datei"
aliases:
- de/bash/creating-a-temporary-file.md
date:                  2024-01-20T17:39:36.332785-07:00
model:                 gpt-4-1106-preview
simple_title:         "Erstellung einer temporären Datei"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/bash/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Was & Warum?
Temporäre Dateien sind kurzlebige Dateien, die während der Laufzeit eines Programms erstellt werden. Programmierer nutzen sie für Datenverarbeitung, Zwischenspeicherung und um auf Festplatte basierte Locks zu implementieren. 

## Anleitung:
Erstellen einer temporären Datei mit `mktemp`:

```Bash
tempfile=$(mktemp)
echo "Temporäre Datei angelegt: $tempfile"
```

Ausgabe:
```
Temporäre Datei angelegt: /tmp/tmp.IkXMlvM7ck
```

Eine temporäre Datei in einem bestimmten Verzeichnis:

```Bash
tempfile=$(mktemp /mein/tempdir/XXXXXX)
echo "Temporäre Datei im benutzerdefinierten Verzeichnis: $tempfile"
```

Ausgabe:
```
Temporäre Datei im benutzerdefinierten Verzeichnis: /mein/tempdir/nmJf6H
```

Sicherer Aufräummechanismus mit `trap`:

```Bash
tempfile=$(mktemp)
trap "rm -f $tempfile" EXIT
echo "Arbeite mit temporärer Datei: $tempfile"
# Hier deine Skript-Operationen
```

Das Skript löscht die temporäre Datei automatisch beim Beenden, selbst bei Fehlern.

## Hintergrundinfos:
Die `mktemp`-Utility kam als sichere Alternative zur manuellen Dateinamensgenerierung auf, um Race Conditions und Sicherheitsprobleme zu vermeiden. Alternativ können ältere Methoden wie das Anhängen von `$$` (die PID des Skripts) an Dateinamen genutzt werden, sind aber unsicher.

Ein Blick unter die Haube zeigt, dass `mktemp` eine einzigartige Zeichenkette generiert, oft durch Kombination von Zufallszahlen und Zeitstempeln, um Kollisionen zu vermeiden.

Sollen nur temporäre Daten im Speicher vorgehalten werden, kann stattdessen `tmpfs` verwendet werden, ein temporäres Filesystem im Arbeitsspeicher.

## Weiterführende Links:
- GNU Coreutils Dokumentation zu `mktemp`: https://www.gnu.org/software/coreutils/manual/html_node/mktemp-invocation.html
- `trap`-Befehl: https://www.gnu.org/software/bash/manual/html_node/Bourne-Shell-Builtins.html#index-trap
