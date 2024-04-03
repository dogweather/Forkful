---
date: 2024-01-20 17:40:10.029389-07:00
description: "Tworzenie tymczasowego pliku to proces generowania pliku, kt\xF3ry zostanie\
  \ u\u017Cyty kr\xF3tkotrwale, a potem usuni\u0119ty. Programi\u015Bci tworz\u0105\
  \ je do przechowywania\u2026"
lastmod: '2024-03-13T22:44:35.016532-06:00'
model: gpt-4-1106-preview
summary: "Tworzenie tymczasowego pliku to proces generowania pliku, kt\xF3ry zostanie\
  \ u\u017Cyty kr\xF3tkotrwale, a potem usuni\u0119ty."
title: Tworzenie pliku tymczasowego
weight: 21
---

## Jak to zrobić:
```clojure
(require '[clojure.java.io :as io])

(defn create-temp-file [prefix suffix]
  (.createTempFile (io/file (System/getProperty "java.io.tmpdir")) prefix suffix))

;; Użycie:
(def temp-file (create-temp-file "example" ".tmp"))

;; Sprawdzenie:
(println "Tymczasowy plik został stworzony: " (.getPath temp-file))

;; Kiedy skończysz, usuń plik:
(.delete temp-file)
```
Przykładowe wyjście:
```
Tymczasowy plik został stworzony: /tmp/example4353434467984643904.tmp
```

## Wgłębienie się
W starszych wersjach języków programowania, tworzenie pliku tymczasowego było mniej bezpośrednie, wymagając manualnego zarządzania ścieżkami i uprawnieniami. Clojure, korzystając z Java Interop, pozwala na prostsze tworzenie tymczasowych plików dzięki wbudowanym funkcjom Javy. Alternatywy to tworzenie plików w określonym katalogu, ale pamiętaj - zarządzanie tymczasowymi plikami jest ważne, by uniknąć wycieków zasobów. Implementacja Clojure załatwia wiele problemów, włączając automatyczne generowanie unikalnych nazw plików i opcję usunięcia pliku po wyłączeniu JVM (Java Virtual Machine), jeśli korzystasz z `deleteOnExit`.

## Zobacz także:
- Dokumentacja Clojure `java.io`: [https://clojure.github.io/clojure/clojure.java.io-api.html](https://clojure.github.io/clojure/clojure.java.io-api.html)
- Dokumentacja klasy `java.io.File`: [https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/File.html](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/io/File.html)
