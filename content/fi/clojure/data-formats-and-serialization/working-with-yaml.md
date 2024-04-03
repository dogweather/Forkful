---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:56.378953-07:00
description: "YAML, rekursiivinen lyhenne sanoista \"YAML Ain't Markup Language\"\
  , on ihmisen luettavissa oleva datan sarjallistamisformaatti, jota k\xE4ytet\xE4\
  \xE4n\u2026"
lastmod: '2024-03-13T22:44:56.204527-06:00'
model: gpt-4-0125-preview
summary: "YAML, rekursiivinen lyhenne sanoista \"YAML Ain't Markup Language\", on\
  \ ihmisen luettavissa oleva datan sarjallistamisformaatti, jota k\xE4ytet\xE4\xE4\
  n m\xE4\xE4ritystiedostoissa ja datan vaihdossa eri tietorakenteita k\xE4ytt\xE4\
  vien kielten v\xE4lill\xE4."
title: "Ty\xF6skentely YAML:n kanssa"
weight: 41
---

## Kuinka:
Clojure ei sisällä sisäänrakennettua tukea YAMLille, mutta voit käyttää kolmannen osapuolen kirjastoja, kuten `clj-yaml`, YAML-datan jäsentämiseen ja luomiseen. Ensiksi, lisää kirjasto projektisi riippuvuuksiin:

```clojure
;; Lisää tämä projektisi project.clj riippuvuuksiin
[clj-yaml "0.7.0"]
```

Tässä on miten voit käyttää `clj-yaml`ia YAMLin jäsentämiseen ja Clojure map:ien muuntamiseen YAMLiksi.

### YAMLin jäsentäminen:
```clojure
(require '[clj-yaml.core :as yaml])

;; YAML-merkkijonon jäsentäminen
(let [yaml-str "name: John Doe\nage: 30\nlanguages:\n  - Clojure\n  - Python"]
  (yaml/parse-string yaml-str))
;; Tuloste:
;; => {"name" "John Doe", "age" 30, "languages" ["Clojure" "Python"]}
```

### YAMLin luominen Clojuresta:
```clojure
(require '[clj-yaml.core :as yaml])

;; Clojure map:in muuntaminen YAML-merkkijonoksi
(let [data-map {:name "Jane Doe" :age 28 :languages ["Java" "Ruby"]}]
  (yaml/generate-string data-map))
;; Tuloste:
; "age: 28\nlanguages:\n- Java\n- Ruby\nname: Jane Doe\n"
```

Nämä yksinkertaiset toiminnot `clj-yaml`in avulla voidaan integroida Clojure-sovelluksiin käsittelemään määritystiedostoja tai helpottamaan datan vaihtoa muiden palveluiden tai komponenttien kanssa, jotka käyttävät YAMLia.
