---
title:                "Umgang mit komplexen Zahlen"
date:                  2024-01-26T04:43:12.435150-07:00
model:                 gpt-4-0125-preview
simple_title:         "Umgang mit komplexen Zahlen"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/lua/working-with-complex-numbers.md"
---

{{< edit_this_page >}}

## Was & Warum?
Komplexe Zahlen erweitern die Idee der eindimensionalen Zahlengerade in die zweidimensionale Ebene, indem eine senkrechte imaginäre Achse miteinbezogen wird. Programmierer arbeiten in Feldern wie der Signalverarbeitung, der Fluidmechanik und der Elektrotechnik mit ihnen, wo sie für die Darstellung von Schwingungen und anderen Phänomenen unerlässlich sind.

## Wie geht das:
In Lua können Sie komplexe Zahlen mit Tabellen darstellen. Die grundlegenden Operationen umfassen das Hinzufügen, Subtrahieren, Multiplizieren und Dividieren dieser Tabellen. Hier ist wie:

```lua
-- Definieren von zwei komplexen Zahlen als Tabellen
local complex_a = { real = 3, imag = 5 }
local complex_b = { real = 2, imag = -4 }

-- Funktion, um zwei komplexe Zahlen zu addieren
local function add_complex(a, b)
  return { real = a.real + b.real, imag = a.imag + b.imag }
end

-- Beispiel Ausgabe
print(add_complex(complex_a, complex_b))  -- { real = 5, imag = 1 }
```

## Vertiefung
Komplexe Zahlen gibt es seit dem 16. Jahrhundert, sie helfen dabei, Gleichungen zu lösen, die mit reinen reellen Zahlen nicht zu knacken sind. Lua selbst hat keinen eingebauten komplexen Zahlentyp. Das ist jedoch kein großes Problem – Sie können Ihre eigenen Manipulationen komplexer Zahlen mit Tabellen und Funktionen erstellen, wie oben gezeigt. Oder, wenn Ihre Bedürfnisse tiefer gehen, greifen Sie zu einer Bibliothek wie LuaComplex. Dies ist eine gute Wahl, da sie speziell für Lua entwickelt wurde und die manuelle Arbeit abnimmt. Bibliotheken wie diese optimieren oft auch Operationen unter der Haube, sodass sie schneller sind als eigene Entwicklungen.

## Siehe auch
Für detailliertere Beispiele und fortgeschrittene Operationen, schauen Sie sich diese an:

- LuaComplex Bibliothek: https://github.com/davidm/lua-complex
- Buch "Programming in Lua", für die Erstellung benutzerdefinierter Datentypen: https://www.lua.org/pil/11.1.html
- Wikipedia über den Einsatz von komplexen Zahlen in verschiedenen Bereichen: https://en.wikipedia.org/wiki/Complex_number#Applications
