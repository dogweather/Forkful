---
title:                "Drukowanie komunikatów debugowania"
date:                  2024-01-20T17:52:10.962410-07:00
model:                 gpt-4-1106-preview
simple_title:         "Drukowanie komunikatów debugowania"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/clojure/printing-debug-output.md"
---

{{< edit_this_page >}}

## What & Why? | Co i dlaczego?
W debugowaniu wypisywanie komunikatów to jak zostawianie sobie notatek po drodze - żeby wiedzieć, co się dzieje. Programiści używają tego, aby zobaczyć wewnętrzne działanie programu i znaleźć błędy.

## How to: | Jak to zrobić:

Clojure używa funkcji `println` do wypisania na standardowe wyjście. Możesz też użyć `prn` dla danych w formacie czytelnym dla Clojure, czy `printf` dla formatowania stringów.

```Clojure
;; Proste wypisywanie wiadomości
(println "Co się dzieje w programie")
;; => Co się dzieje w programie

;; Wypisanie zmiennej i jej wartości
(def x 42)
(println "Wartość x to:" x)
;; => Wartość x to: 42

;; Wypisanie danych w formacie Clojure
(prn {:a 1 :b 2 :c 3})
;; => {:a 1, :b 2, :c 3}

;; Użycie printf dla formatowania
(printf "Jest %d rodzajów ludzi: %s i %s.\n" 2 "ci, co rozumieją binarnie" "ci, co nie")
;; => Jest 2 rodzajów ludzi: ci, co rozumieją binarnie i ci, co nie.
```

## Deep Dive | W głębię tematu

W latach 90. w Lispie, jednym z przodków Clojure, wypisywanie debugowe było już praktyką. Clojure, funkcjonalny dialekt Lispa, idzie w jego ślady. Zamiast `println`, możesz używać narzędzi jak `tap>` i `add-tap` wprowadzone w Clojure 1.10, które oferują bardziej elastyczne podejście do debugowania.

Logowanie jest alternatywą do wypisywania debugowego. Zapisuje informacje do pliku, nie zaśmiecając terminala. Można używać np. biblioteki `timbre`.

W Clojure, w przeciwieństwie do niektórych innych języków, nie ma wbudowanego systemu do zarządzania poziomami logowania. Zamiast tego, zazwyczaj wybiera się zewnętrzne biblioteki jak wspomniane `timbre`.

## See Also | Zobacz też

- Oficjalna dokumentacja `println`: https://clojuredocs.org/clojure.core/println
- `tap>` i `add-tap` wprowadzenie: https://clojure.org/news/2018/12/21/tap
- Biblioteka `timbre` dla logowania: https://github.com/ptaoussanis/timbre