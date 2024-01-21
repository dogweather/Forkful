---
title:                "Löschen von Zeichen, die einem Muster entsprechen"
date:                  2024-01-20T17:42:00.967776-07:00
model:                 gpt-4-1106-preview
simple_title:         "Löschen von Zeichen, die einem Muster entsprechen"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/clojure/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Löschen von Zeichen, die einem Muster entsprechen, bezeichnet man, wenn man bestimmte Zeichen aus Strings entfernt, die auf ein gegebenes Muster passen. Programmierer nutzen dies, um Daten zu bereinigen, Eingaben zu validieren oder Informationen zu formatieren.

## How to:
```Clojure
(defn delete-matching-chars [pattern string]
  (clojure.string/replace string (re-pattern pattern) ""))

;; Beispiel: Entferne alle Ziffern aus dem String
(println (delete-matching-chars "\\d+" "Heute ist der 4. April 2023"))
;; Ausgabe: Heute ist der . April 

;; Beispiel: Entferne alle nicht-alphanumerischen Zeichen
(println (delete-matching-chars "[^\\w]" "Clojure 1.10! Fantastisch, oder?"))
;; Ausgabe: Clojure 110 Fantastisch oder
```

## Deep Dive
Das Löschen von Zeichen nach einem Muster hat in der Programmierung eine lange Geschichte. Ursprünglich in den 1950ern in Zusammenhang mit dem Text-Editor ed komputiert, ist es jetzt ein Grundbaustein in den meisten modernen Programmiersprachen. In Clojure, einer modernen Lisp-Dialekt, nutzt man `clojure.string/replace` zusammen mit regulären Ausdrücken, um diese Funktionalität umzusetzen. Die Java-Virtual-Maschine (JVM), auf der Clojure läuft, bietet robuste Unterstützung für reguläre Ausdrücke, was Clojure-Entwickler stark von profitieren können. Alternativ könnte man auch `filter`-Funktionen verwenden, aber für einfache Zeichenersetzungen sind reguläre Ausdrücke oft effizienter und lesbarer.

## See Also
- [ClojureDocs: clojure.string/replace](https://clojuredocs.org/clojure.string/replace)
- [Clojure from the ground up: regular expressions](https://aphyr.com/posts/305-clojure-from-the-ground-up-regular-expressions)
- [Java Platform SE 8 - Pattern](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)