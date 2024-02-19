---
aliases:
- /de/bash/writing-to-standard-error/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:14.353142-07:00
description: "Das Schreiben auf den Standardfehler (stderr) in Bash bedeutet, Fehlermeldungen\
  \ oder jede wichtige diagnostische Ausgabe getrennt von der Standardausgabe\u2026"
lastmod: 2024-02-18 23:09:05.071794
model: gpt-4-0125-preview
summary: "Das Schreiben auf den Standardfehler (stderr) in Bash bedeutet, Fehlermeldungen\
  \ oder jede wichtige diagnostische Ausgabe getrennt von der Standardausgabe\u2026"
title: Schreiben auf Standardfehler
---

{{< edit_this_page >}}

## Was & Warum?
Das Schreiben auf den Standardfehler (stderr) in Bash bedeutet, Fehlermeldungen oder jede wichtige diagnostische Ausgabe getrennt von der Standardausgabe (stdout) zu leiten. Programmierer tun dies, um sicherzustellen, dass Fehlermeldungen leicht identifiziert, protokolliert oder sogar ignoriert werden können, was bei der Fehlersuche und den Protokollierungsprozessen hilft.

## Wie:
In Bash verwenden Sie `>&2`, um die Ausgabe auf stderr umzuleiten. Hier ein einfaches Beispiel:

```bash
echo "Das ist eine normale Nachricht"
echo "Das ist eine Fehlermeldung" >&2
```

Wenn Sie dieses Skript ausführen, werden beide Nachrichten auf der Konsole angezeigt, aber wenn Sie sie umleiten, können Sie die stdout von der stderr trennen. Zum Beispiel:

```bash
bash script.sh > output.txt 2> error.txt
```

`output.txt` wird `"Das ist eine normale Nachricht"` enthalten, während `error.txt` `"Das ist eine Fehlermeldung"` erfassen wird.

Für einen praktischen Anwendungsfall betrachten Sie ein Skript, das Dateien verarbeitet und einen Fehler meldet, wenn eine Datei nicht existiert:

```bash
filename="example.txt"

if [ ! -f "$filename" ]; then
    echo "$filename existiert nicht!" >&2
    exit 1
else
    echo "Verarbeite $filename"
fi
```

Beispiel für eine Ausgabe direkt in der Konsole, wenn `example.txt` nicht existiert:

```
example.txt existiert nicht!
```

Es gibt keine direkten Drittanbieter-Bibliotheken in Bash für die Behandlung von stderr, da die Umleitung nativ unterstützt wird und im Allgemeinen ausreichend ist. Für komplexe Anwendungen können jedoch Logging-Frameworks oder externe Protokollierungstools wie `syslog` oder `log4bash` integriert werden, um sowohl stdout als auch stderr effektiver zu verwalten.
