---
aliases:
- /de/lua/refactoring/
date: 2024-01-26 01:46:05.847630-07:00
description: "Refactoring ist die Kunst, bestehenden Code so zu \xFCberarbeiten, dass\
  \ seine Struktur, Lesbarkeit und Effizienz verbessert werden, ohne dass sich sein\u2026"
lastmod: 2024-02-18 23:09:05.015982
model: gpt-4-0125-preview
summary: "Refactoring ist die Kunst, bestehenden Code so zu \xFCberarbeiten, dass\
  \ seine Struktur, Lesbarkeit und Effizienz verbessert werden, ohne dass sich sein\u2026"
title: Refactoring
---

{{< edit_this_page >}}

## Was & Warum?
Refactoring ist die Kunst, bestehenden Code so zu überarbeiten, dass seine Struktur, Lesbarkeit und Effizienz verbessert werden, ohne dass sich sein äußeres Verhalten ändert. Programmierer tun dies, um ihren Code wartbarer zu machen, Komplexität zu reduzieren und oft als vorbereitenden Schritt, bevor neue Funktionen hinzugefügt oder Fehler behoben werden.

## Wie:
Nehmen wir eine einfache Lua-Funktion und refaktorisieren sie. Wir beginnen mit einer Funktion, die die Summe der Zahlen in einer Liste berechnet, die aber ohne viel Gedanken an Effizienz oder Klarheit geschrieben wurde:

```Lua
function sumList(numbers)
    local result = 0
    for i=1, #numbers do
        for j=1, #numbers do
            if i == j then
                result = result + numbers[i]
            end
        end
    end
    return result
end

print(sumList({1, 2, 3, 4})) -- Gibt aus: 10
```

Refaktorisierung zu einer effizienteren und lesbareren Version:
```Lua
function sumListRefactored(numbers)
    local result = 0
    for _, value in ipairs(numbers) do
        result = result + value
    end
    return result
end

print(sumListRefactored({1, 2, 3, 4})) -- Gibt immer noch aus: 10
```

Die überarbeitete Version entfernt die überflüssige innere Schleife und verwendet `ipairs`, um sauber durch die Liste zu iterieren.

## Tiefergehend
Historisch gesehen kommt Refactoring aus der Smalltalk-Programmiergemeinschaft Ende der 80er Jahre und wurde durch Martin Fowlers Buch 'Refactoring: Improving the Design of Existing Code' popularisiert. Bei Lua beinhaltet Refactoring oft das Vereinfachen komplexer Bedingungen, das Aufteilen großer Funktionen in kleinere und das Optimieren der Tabellennutzung, um die Leistung zu verbessern.

Refactoring in Lua hat seine Tücken; Luas dynamische Natur und flexible Typisierung können bestimmte Refactorings, wie das Umbenennen von Variablen oder das Ändern von Funktionssignaturen, riskant machen, wenn sie nicht vorsichtig durchgeführt werden. Werkzeuge für die statische Codeanalyse (wie `luacheck`) können solche Risiken mindern. Alternativen umfassen testgetriebene Entwicklung (TDD), bei der der Code kontinuierlich als integraler Bestandteil des Entwicklungsprozesses refaktorisiert wird, im Gegensatz zu einer separaten Refactoring-Phase.

## Siehe auch
- "Programming in Lua" von Roberto Ierusalimschy für bewährte Praktiken und Beispiele.
- "Refactoring: Improving the Design of Existing Code" von Martin Fowler für Prinzipien, die sprachübergreifend anwendbar sind.
- LuaRocks-Verzeichnis (https://luarocks.org/) für Werkzeuge und Module, die auf die Wartung und das Refactoring von Lua-Code abzielen.
