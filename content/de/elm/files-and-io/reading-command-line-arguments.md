---
title:                "Lesen von Kommandozeilenargumenten"
aliases:
- /de/elm/reading-command-line-arguments/
date:                  2024-01-20T17:55:47.164635-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lesen von Kommandozeilenargumenten"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## Was & Warum?

Kommandozeilenargumente lesen bedeutet, Parameter von der Shell ins Programm zu übertragen. Programmierer nutzen es, um Einstellungen zu steuern oder Eingaben zu verarbeiten, ohne das Programm interaktiv anzupassen.

## Wie geht das:

Elm ist primär für Webanwendungen gedacht, daher gibt es keine eingebaute Funktionalität für das Lesen von Kommandozeilenargumenten wie in Node.js oder Python. Stattdessen würde man auf Ports zurückgreifen, um mit JavaScript zu interagieren.

```Elm
port module Main exposing (..)

-- Definiere einen Port, um Kommandozeilenargumente zu empfangen
port cmdArgs : (String -> msg) -> Sub msg

-- Init-Funktion, die das Modell mit den Argumenten initialisiert
init : Flags -> ( Model, Cmd Msg )
init flags =
    ( { cmdLineArgs = flags.args }
    , Cmd.none
    )

-- Elm Flags für den Empfang der Startargumente
type alias Flags =
    { args : List String }

-- JavaScript Interop, um die Kommandozeilenargumente an Elm zu senden
// JavaScript Code
const app = Elm.Main.init({
  node: document.getElementById('elm'),
  flags: { args: process.argv.slice(2) }
});

app.ports.cmdArgs.subscribe(function(args) {
  // Handle the command line arguments from Elm
});
```

## Tiefgang:

Historisch gesehen ist Elm nicht für Skripting oder Kommandozeilenaufgaben entworfen worden, sondern für interaktive Webanwendungen mit einer starken Betonung auf Zuverlässigkeit und Sicherheit. Für Kommandozeilen-Aufgaben bietet sich eher Node.js an, welches das V8 JavaScript-Backend nutzt. Alternativ kann man Elm auch in Verbindung mit einer Hülle wie Electron verwenden, um mit dem Dateisystem zu interagieren.

Die Kommunikation zwischen Elm und JavaScript (für Aufgaben außerhalb des Kernbereichs von Elm) erfolgt über Ports, welche einen Weg bieten, Nachrichten sicher und zuverlässig auszutauschen. Obwohl dies zusätzliche Arbeit bedeutet, hält es die Elm-Architektur sauber und prädictable.

## Weiterführendes:

- Elm Ports Dokumentation: [https://guide.elm-lang.org/interop/ports.html](https://guide.elm-lang.org/interop/ports.html)
