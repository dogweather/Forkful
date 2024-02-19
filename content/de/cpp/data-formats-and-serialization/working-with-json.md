---
aliases:
- /de/cpp/working-with-json/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:43.250188-07:00
description: "JSON (JavaScript Object Notation) ist ein leichtgewichtiges Format zum\
  \ Speichern und Transportieren von Daten und damit ein hervorragendes Medium f\xFC\
  r den\u2026"
lastmod: 2024-02-18 23:09:05.211527
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) ist ein leichtgewichtiges Format zum Speichern\
  \ und Transportieren von Daten und damit ein hervorragendes Medium f\xFCr den\u2026"
title: Arbeiten mit JSON
---

{{< edit_this_page >}}

## Was & Warum?

JSON (JavaScript Object Notation) ist ein leichtgewichtiges Format zum Speichern und Transportieren von Daten und damit ein hervorragendes Medium für den Datenaustausch zwischen Servern und Webanwendungen. Programmierer nutzen JSON aufgrund seiner leichten Lesbarkeit für Menschen und der unkomplizierten Parsierbarkeit durch Maschinen, besonders wenn es um Anwendungen geht, die einen Datenaustausch über das Internet oder Konfigurationseinstellungen erfordern.

## Wie geht das:

In C++ gibt es keine native Unterstützung für JSON, aber Drittanbieter-Bibliotheken wie nlohmann/json machen es unkompliziert. So verwenden Sie es für grundlegende Aufgaben:

Zuerst stellen Sie sicher, dass Sie die Bibliothek installiert haben. Wenn Sie einen Paketmanager wie vcpkg oder Conan verwenden, können Sie `nlohmann/json` leicht zu Ihrem Projekt hinzufügen.

### JSON aus einem String parsen

```cpp
#include <iostream>
#include <nlohmann/json.hpp>

int main() {
    // JSON-Daten als String
    std::string jsonData = "{\"name\":\"John\", \"age\":30, \"city\":\"New York\"}";

    // JSON-String parsen
    auto jsonObject = nlohmann::json::parse(jsonData);

    // Auf Daten zugreifen
    std::cout << "Name: " << jsonObject["name"] << "\n"
              << "Alter: " << jsonObject["age"] << "\n"
              << "Stadt: " << jsonObject["city"] << std::endl;

    return 0;
}
```

**Beispielausgabe:**

```
Name: John
Alter: 30
Stadt: New York
```

### JSON erzeugen

JSON-Daten zu erstellen, ist genauso unkompliziert; man weist einfach Werte einem `nlohmann::json`-Objekt zu.

```cpp
#include <nlohmann/json.hpp>
#include <iostream>

int main() {
    // Ein JSON-Objekt erstellen
    nlohmann::json jsonObject;
    jsonObject["name"] = "Jane";
    jsonObject["age"] = 25;
    jsonObject["city"] = "Los Angeles";

    // JSON-Objekt in String konvertieren und ausgeben
    std::string jsonString = jsonObject.dump(4); // Argument 4 für hübsches Drucken
    std::cout << jsonString << std::endl;

    return 0;
}
```

**Beispielausgabe:**

```
{
    "name": "Jane",
    "age": 25,
    "stadt": "Los Angeles"
}
```

Diese Beispiele demonstrieren die Kernfunktionalitäten für die Arbeit mit JSON in C++ unter Verwendung der `nlohmann/json`-Bibliothek. Mit diesen Grundlagen können Sie JSON für verschiedene Anwendungen parsen und generieren, von Konfigurationsdateien bis hin zum Datenaustausch in vernetzten Anwendungen.
