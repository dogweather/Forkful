---
aliases:
- /uk/clojure/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:20.746260-07:00
description: "YAML, \u0440\u0435\u043A\u0443\u0440\u0441\u0438\u0432\u043D\u0438\u0439\
  \ \u0430\u043A\u0440\u043E\u043D\u0456\u043C \"YAML Ain't Markup Language\" (YAML\
  \ - \u0446\u0435 \u043D\u0435 \u043C\u043E\u0432\u0430 \u0440\u043E\u0437\u043C\u0456\
  \u0442\u043A\u0438), \u0454 \u0444\u043E\u0440\u043C\u0430\u0442\u043E\u043C \u0441\
  \u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\u0456\u0457 \u0434\u0430\u043D\
  \u0438\u0445, \u0437\u0440\u043E\u0437\u0443\u043C\u0456\u043B\u0438\u043C \u0434\
  \u043B\u044F \u043B\u044E\u0434\u0438\u043D\u0438, \u044F\u043A\u0438\u0439\u2026"
lastmod: 2024-02-18 23:08:59.861129
model: gpt-4-0125-preview
summary: "YAML, \u0440\u0435\u043A\u0443\u0440\u0441\u0438\u0432\u043D\u0438\u0439\
  \ \u0430\u043A\u0440\u043E\u043D\u0456\u043C \"YAML Ain't Markup Language\" (YAML\
  \ - \u0446\u0435 \u043D\u0435 \u043C\u043E\u0432\u0430 \u0440\u043E\u0437\u043C\u0456\
  \u0442\u043A\u0438), \u0454 \u0444\u043E\u0440\u043C\u0430\u0442\u043E\u043C \u0441\
  \u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\u0456\u0457 \u0434\u0430\u043D\
  \u0438\u0445, \u0437\u0440\u043E\u0437\u0443\u043C\u0456\u043B\u0438\u043C \u0434\
  \u043B\u044F \u043B\u044E\u0434\u0438\u043D\u0438, \u044F\u043A\u0438\u0439\u2026"
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 YAML"
---

{{< edit_this_page >}}

## Що та Чому?

YAML, рекурсивний акронім "YAML Ain't Markup Language" (YAML - це не мова розмітки), є форматом серіалізації даних, зрозумілим для людини, який використовується для файлів конфігурації та обміну даними між мовами з різними структурами даних. Програмісти використовують YAML через його простоту та читабельність, що робить його ідеальним вибором для конфігурації додатків та сприяння обміну даними в поліглотних програмних середовищах.

## Як:

Clojure не має вбудованої підтримки для YAML, однак ви можете використовувати сторонні бібліотеки, такі як `clj-yaml` для аналізу та генерації даних YAML. Спочатку додайте бібліотеку до залежностей вашого проекту:

```clojure
;; Додайте це до залежностей вашого project.clj
[clj-yaml "0.7.0"]
```

Ось як ви можете використовувати `clj-yaml` для аналізу YAML та конвертації мап Clojure в YAML.

### Аналіз YAML:

```clojure
(require '[clj-yaml.core :as yaml])

;; Аналіз рядка YAML
(let [yaml-str "name: John Doe\nage: 30\nlanguages:\n  - Clojure\n  - Python"]
  (yaml/parse-string yaml-str))
;; Вивід:
;; => {"name" "John Doe", "age" 30, "languages" ["Clojure" "Python"]}
```

### Генерація YAML з Clojure:

```clojure
(require '[clj-yaml.core :as yaml])

;; Конвертація мапи Clojure в рядок YAML
(let [data-map {:name "Jane Doe" :age 28 :languages ["Java" "Ruby"]}]
  (yaml/generate-string data-map))
;; Вивід:
; "age: 28\nlanguages:\n- Java\n- Ruby\nname: Jane Doe\n"
```

Ці прості операції з `clj-yaml` можна інтегрувати в додатки Clojure для обробки файлів конфігурації або сприяння обміну даними з іншими сервісами чи компонентами, що використовують YAML.
