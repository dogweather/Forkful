---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:07:11.307118-07:00
description: "Tekst zoeken en vervangen stelt je in staat specifieke reeksen in een\
  \ tekst te vinden en deze te vervangen door iets anders. Programmeurs doen dit voor\u2026"
lastmod: '2024-03-13T22:44:50.403565-06:00'
model: gpt-4-0125-preview
summary: Tekst zoeken en vervangen stelt je in staat specifieke reeksen in een tekst
  te vinden en deze te vervangen door iets anders.
title: Tekst zoeken en vervangen
weight: 10
---

## Hoe:
In Clojure gebruiken we de functie `clojure.string/replace` om tekst te zoeken en te vervangen. Laten we meteen ter zake komen met wat code:

```clojure
(require '[clojure.string :as str])

;; Basisvervanging
(str/replace "I like apples" "apples" "oranges")
;; => "I like oranges"

;; Het gebruik van een reguliere expressie om alle klinkers te vervangen
(str/replace "Hello, World!" "[AEIOUaeiou]" "*")
;; => "H*ll*, W*rld!"

;; Vervanging met een functie voor dynamische veranderingen
(str/replace "I have 2 apples and 5 bananas"
             #"\d+"
             (fn [match] (str (inc (Integer/parseInt match)))))
;; => "I have 3 apples and 6 bananas"
```

Zo simpel is het. Draai het, en je ziet de transformaties direct in je REPL.

## Diepere Duik
Tekst zoeken en vervangen is niet nieuw. Het is al oud in de informatica. We hebben het van vroege editors zoals `sed` in Unix. Sindsdien zijn we een lange weg gekomen.

Clojure, dat op de JVM draait, betekent dat je de kracht van Java's reguliere expressies onder de motorkap hebt. Wat prestaties betreft, is het handig voor snelle scripts, maar onthoud dat overmatig gebruik bij grootschalige tekstverwerking de prestaties kan schaden.

Wat betreft alternatieven, naast `clojure.string/replace`, zijn er op regex-gebaseerde bibliotheken of zelfs het schrijven van je eigen functie als je avontuurlijk aangelegd bent. Denk aan `replace-first` als je slechts een eenmalige wijziging nodig hebt.

Functioneel gezien betekent Clojure's benadering van onveranderlijkheid dat elke vervanging resulteert in een nieuwe string. Geen veranderlijke strings betekent minder bugs en verrassingen.

## Zie Ook
Om dieper in te duiken, bekijk deze bronnen:

- Clojure's `clojure.string` [API documentatie](https://clojuredocs.org/clojure.string/replace)
- Over reguliere expressies, Java's [Pattern klasse](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)
