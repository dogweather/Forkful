---
title:                "Umformung eines Strings in Kleinbuchstaben"
date:                  2024-01-20T17:38:03.144323-07:00
model:                 gpt-4-1106-preview
simple_title:         "Umformung eines Strings in Kleinbuchstaben"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/clojure/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Umwandeln eines Strings in Kleinbuchstaben bedeutet, alle Buchstaben in einem Text in ihre entsprechende kleine Form zu übertragen. Programmierer nutzen dies, um Einheitlichkeit zu gewährleisten, beispielsweise bei der Validierung von E-Mail-Adressen oder beim Vergleich von Nutzereingaben.

## Wie geht das:
In Clojure kannst du Strings mit der `clojure.string/lower-case` Funktion in Kleinbuchstaben umwandeln. Hier ist, wie du es machst:

```Clojure
(require '[clojure.string :as str])

;; Einen String in Kleinbuchstaben umwandeln
(str/lower-case "Das ist Großartig!")
;; => "das ist großartig!"
```

Die Funktion behandelt Standardfälle. Guck dir jedoch `clojure.string/lower-case` an, wenn du lokalisiertere Anpassungen brauchst.

## Tiefgang:
In der Geschichte der Programmierung war die Fallumwandlung schon immer ein Thema, besonders wenn es um die Verarbeitung von Nutzereingaben oder Daten ging. Die Umwandlung in Kleinbuchstaben ist eine einfache Methode, um sicherzustellen, dass Texteingaben einheitlich behandelt werden, irrelevant von der Nutzereingabe.

In Clojure ist `clojure.string/lower-case` die Standardmethode für die Umwandlung. Aber nicht alle Sprachen und Systeme bieten solch eingebaute Methoden; manchmal muss man es selbst implementieren. In solchen Fällen ist es wichtig, auf potenzielle Fallen wie Lokalisierung und spezielle Schriftzeichen zu achten. Ein 'ß' in Deutsch bleibt zum Beispiel auch in Kleinbuchstaben ein 'ß'.

Clojure übernimmt intern die Java-Methode `String.toLowerCase()`, welche Unicode-konform ist und dementsprechend die meisten Fälle korrekt behandelt. Dennoch, wenn du es mit spezifischem Text zu tun hast, der nicht durch Unicode abgedeckt ist, könntest du auf maßgeschneiderte Lösungen zurückgreifen müssen.

Alternativen zur `clojure.string/lower-case` Funktion sind nicht weit verbreitet in Clojure, da die Funktion effektiv und weitgehend ausreichend für den Bedarf der meisten Anwendungen ist.

## Siehe auch:
- Clojure Docs for `clojure.string/lower-case`: [Official Documentation](https://clojuredocs.org/clojure.string/lower-case)
- Unicode Consortium für tiefergehende Informationen über Unicode: [Unicode Standard](https://unicode.org/standard/standard.html)
- Java `String.toLowerCase()` Methoden-Dokumentation, für die Basis von Clojure's String Verarbeitung: [Java Documentation](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html#toLowerCase())
