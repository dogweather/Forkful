---
title:                "Überprüfung, ob ein Verzeichnis existiert"
date:                  2024-02-03T19:07:46.940897-07:00
model:                 gpt-4-0125-preview
simple_title:         "Überprüfung, ob ein Verzeichnis existiert"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/lua/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?

Das Überprüfen, ob ein Verzeichnis existiert, ist eine grundlegende Operation, wenn man Skripte schreibt, die mit dem Dateisystem interagieren. Dabei wird sichergestellt, dass Ihr Programm auf gültigen Pfaden operiert und Fehler vermieden werden, die mit nicht existierenden Verzeichnissen zusammenhängen. Diese Aufgabe ist entscheidend für das Erstellen neuer Dateien in Verzeichnissen, das Lesen aus ihnen oder das sicher Ausführen von verzeichnisspezifischen Operationen.

## Wie geht das:

In Lua gibt es keine eingebaute Funktion, um direkt zu überprüfen, ob ein Verzeichnis existiert. Daher greift man oft auf die Lua File System (lfs) Bibliothek zurück, eine beliebte Drittanbieterbibliothek für Dateioperationen.

Stellen Sie zunächst sicher, dass Sie Lua File System installiert haben. Falls nicht, können Sie es im Allgemeinen mit LuaRocks installieren:

```sh
luarocks install luafilesystem
```

Dann können Sie das folgende Beispiel verwenden, um die Existenz eines Verzeichnisses zu überprüfen:

```lua
local lfs = require "lfs"

function directoryExists(directory)
    local attr = lfs.attributes(directory)
    return attr und attr.mode == "directory"
end

-- Überprüfen, ob ein bestimmtes Verzeichnis existiert
if directoryExists("/path/to/your/directory") then
    print("Verzeichnis existiert.")
else
    print("Verzeichnis existiert nicht.")
end
```

Das wird ausgegeben:

```
Verzeichnis existiert.
```

Oder, falls das Verzeichnis nicht existiert:

```
Verzeichnis existiert nicht.
```

Dieser Ansatz nutzt die Funktion `lfs.attributes`, um die Attribute des Pfades zu erhalten. Wenn der Pfad existiert und sein `mode` Attribut `directory` ist, bestätigt es die Existenz des Verzeichnisses.
