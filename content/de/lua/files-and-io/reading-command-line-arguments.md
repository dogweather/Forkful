---
date: 2024-01-20 17:56:24.504819-07:00
description: "Kommandozeilenargumente sind Parameter, die ein Programm beim Start\
  \ \xFCber die Konsole erh\xE4lt. Sie erm\xF6glichen es dem Benutzer, das Verhalten\
  \ des Programms\u2026"
lastmod: '2024-03-13T22:44:54.030461-06:00'
model: gpt-4-1106-preview
summary: "Kommandozeilenargumente sind Parameter, die ein Programm beim Start \xFC\
  ber die Konsole erh\xE4lt."
title: Lesen von Kommandozeilenargumenten
weight: 23
---

## How to:
Command-line arguments in Lua are pretty straightforward to handle. Here’s how you nab them:

```lua
-- speichere alle Argumente in einer Tabelle namens arg
for i = 1, #arg do
  print("Argument " .. i .. ": " .. arg[i])
end
```

Ausführung und Ausgabe, wenn das Skript `hello.lua` heißt und mit `lua hello.lua Hallo Welt` gestartet wird:

```lua
Argument 1: Hallo
Argument 2: Welt
```

## Deep Dive
Lua behandelt Kommandozeilenargumente ziemlich unkompliziert. Das `arg`-Array ist deine Schatztruhe, die alle Argumente ab Index 1 speichert. Doch hier ist ein wenig historischer Kontext: In früheren Versionen hattest du `arg[0]`, das den Skriptnamen beinhaltete; ab Lua 5.1 bekommst du das über `arg[-1]`. Es gibt Alternativen wie das `os.getenv()` für Umgebungsvariablen oder eigene Parser für komplexere Szenarien. Beachte jedoch, dass die einfache `arg`-Tabelle in den meisten Fällen genügt.

## See Also
Für weiterführende Informationen, hier ein paar Links:

- Offizielle Lua-Programmierhandbuch: http://www.lua.org/manual/5.4/manual.html#6.1
- Eine Sammlung nützlicher Lua-Skripte und -Tools: https://luarocks.org/
- Lua Users Wiki, eine Ressource für Lua-Codesnippets und -bibliotheken: http://lua-users.org/wiki/ CommandLineArguments
