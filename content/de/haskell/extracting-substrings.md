---
title:                "Teilstrings extrahieren"
date:                  2024-01-20T17:46:02.169662-07:00
model:                 gpt-4-1106-preview
simple_title:         "Teilstrings extrahieren"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/haskell/extracting-substrings.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Extrahieren von Teilstrings bezieht sich darauf, spezifische Segmente eines Strings in Haskell herauszuschneiden. Programmierer nutzen es, um relevante Daten zu manipulieren, Text zu analysieren oder Benutzereingaben zu verarbeiten.

## So geht's:
Haskell bietet verschiedene Wege, um Teile eines Strings zu extrahieren. Hier sind ein paar schnelle Beispiele:

```haskell
import Data.List (isPrefixOf)

-- Take-Funktion gibt die ersten n Zeichen zurück
-- "Hello World!" => "Hello"
takeExample :: String -> String
takeExample = take 5

-- Drop-Funktion entfernt die ersten n Zeichen
-- "Hello World!" => "World!"
dropExample :: String -> String
dropExample = drop 6

-- Fokussierung auf Substring 'Wo' mit Hilfe von filter und isPrefixOf
-- "Hello World!" => "World!"
substringExample :: String -> String
substringExample = unwords . filter ("Wo" `isPrefixOf`) . words

-- Ausgabe der Beispiele
main :: IO ()
main = do
    putStrLn (takeExample "Hello World!")
    putStrLn (dropExample "Hello World!")
    putStrLn (substringExample "Hello World!")
```

Beispielausgabe:
```
Hello
World!
World!
```

## Deep Dive
Die extraktion von Substrings in Haskell kann mit Funktionen aus dem `Data.List` Modul oder mit eigenen Funktionen erreicht werden. Historisch gesehen hat Haskell nicht immer die robusteste Standardbibliothek für String-Manipulation geboten, aber durch externe Bibliotheken wie `text` und `bytestring` wurden diese Lücken gefüllt. Alternativen zur Extraktion könnten Regex-Bibliotheken sein oder das Zerlegen in Listen von Chars und anschließende Rekonstruktion. Implementationsdetails hängen stark von der Spezifikation der extrahierten Daten ab – und natürlich von der gewünschten Performanz, wenn man mit großen Textmengen arbeitet.

## See Also
Hilfreiche Links und weiterführende Quellen für tiefere Einsichten:

- [Haskell Data.List Documentation](https://hackage.haskell.org/package/base-4.16.1.0/docs/Data-List.html)
- [Hackage: Text Library](https://hackage.haskell.org/package/text)
- [Learn You a Haskell for Great Good!](http://learnyouahaskell.com/)
- [School of Haskell: Working with Strings](https://www.schoolofhaskell.com/)
