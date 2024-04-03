---
date: 2024-01-20 17:40:32.770787-07:00
description: "Tempor\xE4re Dateien sind kurzlebige Dateien f\xFCr Daten, die w\xE4\
  hrend der Laufzeit eines Programms ben\xF6tigt, aber nicht dauerhaft gespeichert\
  \ werden sollen.\u2026"
lastmod: '2024-03-13T22:44:53.950178-06:00'
model: gpt-4-1106-preview
summary: "Tempor\xE4re Dateien sind kurzlebige Dateien f\xFCr Daten, die w\xE4hrend\
  \ der Laufzeit eines Programms ben\xF6tigt, aber nicht dauerhaft gespeichert werden\
  \ sollen."
title: "Erstellung einer tempor\xE4ren Datei"
weight: 21
---

## So geht's:
Mit der Haskell-Bibliothek `temporary` kann man leicht temporäre Dateien erstellen und verwalten. Hier ein Beispiel:

```haskell
import System.IO.Temp (withSystemTempFile)
import System.IO (hPutStrLn, hGetContents)

main :: IO ()
main = withSystemTempFile "meineTempDatei.txt" $ \tempFile hFile -> do
  -- Schreibe etwas in die temporäre Datei
  hPutStrLn hFile "Das ist ein Test."

  -- Lies den Inhalt der temporären Datei
  hSeek hFile AbsoluteSeek 0  -- Zurück zum Anfang der Datei
  content <- hGetContents hFile
  putStrLn $ "Die temporäre Datei enthält: " ++ content

-- Ausgabe: "Die temporäre Datei enthält: Das ist ein Test."
```

## Tiefgang:
Historisch gesehen wurden temporäre Dateien oft manuell mit spezifischen Dateinamen erstellt, was zu Sicherheitsrisiken führte. Moderne Ansätze, wie die `temporary`-Bibliothek, vermeiden diese Probleme indem sie automatisch eindeutige Namen generieren. Alternativ zur temporären Datei kann man auch In-Memory-Strukturen nutzen, wenn die Performance kritisch ist. Bei der Implementation ist wichtig, dass das Betriebssystem die Datei löscht, auch wenn das Programm unerwartet beendet wird.

## Siehe auch:
- Haskell `temporary` Dokumentation: https://hackage.haskell.org/package/temporary
- Haskell bytestring für effiziente Datei-Operationen: https://hackage.haskell.org/package/bytestring
- Haskell System.IO Dokumentation: https://hackage.haskell.org/package/base/docs/System-IO.html
