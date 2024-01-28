---
title:                "Einsatz eines Debuggers"
date:                  2024-01-26T03:48:19.903448-07:00
model:                 gpt-4-0125-preview
simple_title:         "Einsatz eines Debuggers"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elixir/using-a-debugger.md"
---

{{< edit_this_page >}}

## Was & Warum?
Ein Debugger in Elixir zu verwenden, bedeutet, durch Ihren Code zu gehen, Variablen zu inspizieren und Flüsse zu verfolgen, um Fehler zu beseitigen. Programmierer machen das, um das Unerwartete zu verstehen und sicherzustellen, dass ihre Anwendungen wie vorgesehen funktionieren.

## Wie geht das:
Elixir wird mit einem integrierten grafischen Debugger namens `:debugger` geliefert. Um ihn zu nutzen, müssen Sie ihn starten und sich an Ihren laufenden Prozess anhängen.

Zuerst stellen Sie sicher, dass `:debugger` in einer `iex`-Sitzung gestartet ist:
```elixir
iex> :debugger.start()
{:ok, #PID<0.108.0>}
```

Jetzt interpretieren Sie das Code-Modul, das Sie debuggen möchten:
```elixir
iex> :int.ni(MyApp.MyModule)
{:module, MyApp.MyModule}
```

Sie können einen Haltepunkt setzen:
```elixir
iex> :int.break(MyApp.MyModule, Zeilennummer)
:ok
```

Und dann führen Sie Ihre Funktion aus, um den Haltepunkt zu erreichen und durch Ihren Code zu gehen:
```elixir
iex> MyApp.MyModule.meine_funktion(arg1, arg2)
# Debugger wird die Ausführung an der Zeile mit dem Haltepunkt pausieren
```

## Vertiefung
Vor Elixirs `:debugger` bot Erlang den Debugger, den Elixir nutzt; er ist robust und sehr gut im Umgang mit parallelen Prozessen geeignet, eine Stärke der Erlang VM (BEAM). Im Gegensatz zu einigen anderen Debuggern erlaubt `:debugger` keine Modifikation von Variablen im laufenden Betrieb, aufgrund der unveränderlichen Natur von Daten in Elixir. Als Alternativen gibt es `IEx.pry`, das es Ihnen erlaubt, die Ausführung zu pausieren und an jedem Punkt in Ihrem Code in eine REPL zu springen, was sehr praktisch sein kann.

Während `:debugger` gut für eine grafische Oberfläche ist, bevorzugen einige vielleicht das eingebaute Werkzeug `:observer`, das auch Prozessinspektion und Systemmetriken bietet, allerdings nicht speziell darauf ausgerichtet ist, durch den Code zu gehen. Die Elixir-Community trägt außerdem Werkzeuge wie `visualixir` und `rexbug` bei, die das Ökosystem der Debugging-Tools über die Standardauswahl hinaus erweitern.

## Siehe auch
- Offizielles Elixir Einsteigerhandbuch zum Debugging: https://elixir-lang.org/getting-started/debugging.html
- Erlangs `:debugger` Dokumentation: http://erlang.org/doc/apps/debugger/debugger_chapter.html
- Elixir Forum Diskussionen über Debugging-Techniken: https://elixirforum.com/c/elixir-questions/elixir-questions-questions-help/15
