---
aliases:
- /de/python/using-an-interactive-shell-repl/
date: 2024-01-26 04:17:24.177905-07:00
description: "Ein REPL, oder Read-Eval-Print-Lopp, ist eine Programmierumgebung, die\
  \ einzelne Benutzereingaben nimmt, sie ausf\xFChrt und das Ergebnis an den Benutzer\u2026"
lastmod: 2024-02-18 23:09:04.463748
model: gpt-4-0125-preview
summary: "Ein REPL, oder Read-Eval-Print-Lopp, ist eine Programmierumgebung, die einzelne\
  \ Benutzereingaben nimmt, sie ausf\xFChrt und das Ergebnis an den Benutzer\u2026"
title: Nutzung einer interaktiven Shell (REPL)
---

{{< edit_this_page >}}

## Was & Warum?
Ein REPL, oder Read-Eval-Print-Lopp, ist eine Programmierumgebung, die einzelne Benutzereingaben nimmt, sie ausführt und das Ergebnis an den Benutzer zurückgibt. Programmierer nutzen es für schnelle Tests, zum Lernen, Debuggen oder für Berechnungen "on-the-fly".

## Wie geht das:
Spring direkt in Pythons REPL, indem du `python` in deine Kommandozeile eingibst. Sobald du dort bist, teste einfache Operationen oder mehrzeiligen Code:

```Python
>>> 1 + 1
2
>>> for i in range(3):
...     print(i)
... 
0
1
2
```

Experimentiere mit Funktionen und sofortigem Feedback:

```Python
>>> def greet(name):
...     return "Hallo, " + name + "!"
... 
>>> greet("Alice")
'Hallo, Alice!'
```

Spiel mit Bibliotheken und erkunde ihre Eigenschaften in Echtzeit:

```Python
>>> import math
>>> math.sqrt(16)
4.0
```

Verlasse das REPL schnell mit `exit()` oder `Strg+D` (manchmal `Strg+Z` unter Windows).

## Tiefer eintauchen
Das Konzept eines REPL ist nicht einzigartig für Python; es ist so alt wie Lisp. Viele Sprachen bieten diese unmittelbare, interaktive Umgebung für einen praktischen Ansatz zum Programmieren. Alternativen zur nativen Python-Shell umfassen IPython und Jupyter Notebook, welche verbesserte Interaktivität, mehr Funktionen und eine bessere Integration mit anderen Tools bieten. Pythons standardmäßiges REPL ist einfach, aber es birgt die volle Kraft von Python, handhabt komplexe Objekte und Programme mit mehreren Threads, obwohl es Funktionen wie Auto-Vervollständigung und Syntaxhervorhebung vermissen lässt, die in fortgeschritteneren Tools vorhanden sind.

## Siehe auch
- [Pythons offizielle Dokumentation zum Interpreter](https://docs.python.org/3/tutorial/interpreter.html)
- [IPython: Eine fortgeschrittene Python-Shell](https://ipython.org/)
- [Jupyter-Projekt](https://jupyter.org/)
