---
title:                "Debug-Ausgaben drucken"
aliases:
- de/elm/printing-debug-output.md
date:                  2024-01-20T17:52:20.334430-07:00
model:                 gpt-4-1106-preview
simple_title:         "Debug-Ausgaben drucken"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/printing-debug-output.md"
---

{{< edit_this_page >}}

## Was & Warum?
Debug-Ausgaben zu drucken, bedeutet, Informationen zum Codeablauf in der Entwicklungskonsole anzuzeigen, um zu verstehen, was das Programm macht. Es hilft Entwicklern, Fehler zu finden und die inne liegende Magie des Codes zu entwirren.

## How to:
In Elm kannst du `Debug.log` nutzen, um Werte in die Konsole zu schreiben. Sei dir bewusst, dass diese Funktion in Produktion entfernt sein sollte.

```elm
import Html

main =
  Html.text (Debug.log "MyValue" "Hello, Elm!")
```

Ausgabe in der Konsole:

```
MyValue: "Hello, Elm!"
```

## Deep Dive
`Debug.log` wurde in Elm entwickelt, um beim Debugging zu helfen, ohne deinen Elm-Code zu stören. Es ist nicht für die Produktion gedacht und hat bewusst keine komplexe Funktionalität. Alternativen wie `elm-debug-transformer` erweitern die Möglichkeiten für Debugging in Elm, indem sie ein schöneres Format für die Anzeige von Debug-Informationen im Browser bieten. Wichtig ist, dass `Debug.log` als reiner Seiteneffekt funktioniert; es verändert die Programmausführung nicht.

## See Also
- Elm's `Debug` module documentation: [Elm `Debug` Docs](https://package.elm-lang.org/packages/elm/core/latest/Debug)
- `elm-debug-transformer`: [GitHub Repository](https://github.com/kraklin/elm-debug-transformer)
