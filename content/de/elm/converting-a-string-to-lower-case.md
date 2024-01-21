---
title:                "Umformung eines Strings in Kleinbuchstaben"
date:                  2024-01-20T17:38:08.077721-07:00
model:                 gpt-4-1106-preview
simple_title:         "Umformung eines Strings in Kleinbuchstaben"
programming_language: "Elm"
category:             "Elm"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Ein String in Kleinbuchstaben umzuwandeln bedeutet, alle Zeichen des Strings in ihre Kleinbuchstaben-Äquivalente zu transformieren. Programmierer nutzen dies, um die Groß- und Kleinschreibung zu vereinheitlichen, oft beim Vergleichen von Text oder bei der Standardisierung von Nutzereingaben.

## How to:
In Elm kannst du den `String.toLower`-Funktion nutzen, um einen String in Kleinbuchstaben umzuwandeln. So geht's:

```Elm
import String

lowercaseString : String -> String
lowercaseString str =
    String.toLower str

-- Beispiel-Nutzung
main =
    lowercaseString "Hallo, Welt!"  --> "hallo, welt!"
```

Der Aufruf `lowercaseString "Hallo, Welt!"` gibt dir `"hallo, welt!"` zurück.

## Deep Dive
Die Umwandlung zu Kleinbuchstaben ist ein klassisches Problem und ein Standardfeature in vielen Programmiersprachen. Historisch gesehen folgt Elm hier anderen funktionalen Sprachen wie Haskell oder ML. Elm vereinfacht dies im Vergleich zu JavaScript, wo unterschiedliche Browser unterschiedlich auf `String.toLowerCase()`-Aufrufe reagieren könnten.

Es gibt Alternativen, wie zum Beispiel die manuelle Umwandlung jedes Zeichens durch eine eigens definierte Funktion, was aber meist unnötig komplex ist. Die Implementierung von `String.toLower` nutzt die Unicode-Standardisierung, um zuverlässige Ergebnisse zu garantieren, egal für welche Sprache oder welches Zeichensystem.

## See Also
Zum Vertiefen empfehle ich folgende Ressourcen:

- Elm's offizielle `String`-Dokumentation: [package.elm-lang.org/packages/elm/core/latest/String#toLower](https://package.elm-lang.org/packages/elm/core/latest/String#toLower)
- Unicode-Standard: [unicode.org/reports/tr21/tr21-5.html](https://unicode.org/reports/tr21/tr21-5.html)