---
aliases:
- /de/haskell/using-regular-expressions/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:50.079146-07:00
description: "Regul\xE4re Ausdr\xFCcke in der Programmierung sind Zeichenfolgen, die\
  \ ein Suchmuster definieren und typischerweise f\xFCr die Suche und Manipulation\
  \ von\u2026"
lastmod: 2024-02-18 23:09:04.906042
model: gpt-4-0125-preview
summary: "Regul\xE4re Ausdr\xFCcke in der Programmierung sind Zeichenfolgen, die ein\
  \ Suchmuster definieren und typischerweise f\xFCr die Suche und Manipulation von\u2026"
title: "Regul\xE4re Ausdr\xFCcke verwenden"
---

{{< edit_this_page >}}

## Was & Warum?
Reguläre Ausdrücke in der Programmierung sind Zeichenfolgen, die ein Suchmuster definieren und typischerweise für die Suche und Manipulation von Zeichenketten verwendet werden. Haskell-Programmierer nutzen reguläre Ausdrücke für Aufgaben, die von der einfachen Zeichenkettenübereinstimmung bis zur komplexen Textverarbeitung reichen, und profitieren dabei von ihrer Effizienz und Vielseitigkeit im Umgang mit Textdaten.

## Wie:
In Haskell sind Regex-Funktionalitäten nicht Teil der Standardbibliothek, was die Verwendung von Drittanbieterpaketen wie `regex-base` zusammen mit einem kompatiblen Backend wie `regex-posix` (für POSIX-Regex-Unterstützung), `regex-pcre` (für Perl-kompatible Regex) usw. erforderlich macht. So können Sie diese Pakete verwenden, um mit regulären Ausdrücken zu arbeiten.

Stellen Sie zunächst sicher, dass Sie die Pakete installiert haben, indem Sie `regex-posix` oder `regex-pcre` zur `.cabal`-Datei Ihres Projekts hinzufügen oder direkt über cabal installieren:

```bash
cabal install regex-posix
```
oder
```bash
cabal install regex-pcre
```

### Verwendung von `regex-posix`:

```haskell
import Text.Regex.Posix ((=~))

-- Überprüfen, ob eine Zeichenkette einem Muster entspricht
isMatch :: String -> String -> Bool
isMatch text pattern = text =~ pattern :: Bool

-- Finde die erste Übereinstimmung
findFirst :: String -> String -> String
findFirst text pattern = text =~ pattern :: String

main :: IO ()
main = do
    print $ isMatch "hallo welt" "wo"
    -- Ausgabe: True
    print $ findFirst "guten Morgen, gute Nacht" "gut"
    -- Ausgabe: "gut"
```

### Verwendung von `regex-pcre`:

```haskell
import Text.Regex.PCRE ((=~))

-- Finde alle Übereinstimmungen
findAll :: String -> String -> [String]
findAll text pattern = text =~ pattern :: [String]

main :: IO ()
main = do
    print $ findAll "test1 test2 test3" "\\btest[0-9]\\b"
    -- Ausgabe: ["test1","test2","test3"]
```

Jede Bibliothek hat ihre Besonderheiten, aber die allgemeine Methodik, `=~` zu verwenden, um das Regex anzuwenden, bleibt konsistent, ob es nun darum geht, auf eine Übereinstimmung zu überprüfen oder Unterzeichenketten zu extrahieren. Die Wahl zwischen `regex-posix` oder `regex-pcre` hängt weitgehend von den Bedürfnissen Ihres Projekts und den spezifischen erforderlichen Regex-Fähigkeiten ab.
