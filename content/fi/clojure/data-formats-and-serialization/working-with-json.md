---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:22:13.790096-07:00
description: "JSONin (JavaScript Object Notation) k\xE4sittely Clojuressa sis\xE4\
  lt\xE4\xE4 JSON-merkkijonojen j\xE4sent\xE4misen Clojure-tietorakenteiksi (hajautustaulut,\
  \ vektorit) ja\u2026"
lastmod: '2024-03-13T22:44:56.205567-06:00'
model: gpt-4-0125-preview
summary: "JSONin (JavaScript Object Notation) k\xE4sittely Clojuressa sis\xE4lt\xE4\
  \xE4 JSON-merkkijonojen j\xE4sent\xE4misen Clojure-tietorakenteiksi (hajautustaulut,\
  \ vektorit) ja p\xE4invastoin."
title: "Ty\xF6skentely JSON:n kanssa"
weight: 38
---

## Kuinka:
Clojure ei sisällä sisäänrakennettuja funktioita työskentelyyn JSONin kanssa, joten yleensä käytetään kolmannen osapuolen kirjastoja. `cheshire` ja `jsonista` ovat suosittuja valintoja niiden käytön helppouden ja suorituskyvyn vuoksi.

### Cheshiren käyttö
Lisää ensin Cheshire projektisi riippuvuuksiin `project.clj` tiedostossa:
```clj
[com.fasterxml.jackson.core/jackson-core "2.12.0"]
[cheshire "5.10.1"]
```

JSON-merkkijonon jäsentämiseksi Clojure-hajautustauluksi ja hajautustaulun muuntamiseksi JSON-merkkijonoksi:

```clj
(require '[cheshire.core :as json])

;; Jäsennä JSON-merkkijono Clojure-hajautustauluksi
(let [json-input "{\"name\":\"John\", \"age\":30}"]
  (json/parse-string json-input true)) ; => {"name" "John", "age" 30}

;; Muunna Clojure-hajautustaulu JSON-merkkijonoksi
(let [clj-map {"name" "John", "age" 30}]
  (json/generate-string clj-map)) ; => "{\"name\":\"John\",\"age\":30}"
```

### Jsonistan käyttö
Lisää Jsonista projektiisi `project.clj`:
```clj
[jsonista "0.3.2"]
```

Vastaavat toiminnot Jsonistalla:

```clj
(require '[jsonista.core :as j])

;; Jäsennä JSON-merkkijono Clojureen
(let [json-input "{\"name\":\"Emily\", \"age\":25}"]
  (j/read-value json-input)) ; => {"name" "Emily", "age" 25}

;; Muunna Clojure-hajautustaulu JSON-merkkijonoksi
(let [clj-map {"name" "Emily", "age" 25}]
  (j/write-value-as-string clj-map)) ; => "{\"name\":\"Emily\",\"age\":25}"
```

Molemmissa kirjastoissa on mahdollisuus koodata ja dekoodata monimutkaisempia tietorakenteita, ja käytössä on lisätoimintoja ja parametreja, jotka mahdollistavat sarjoittamisen ja deserialisoinnin prosessien mukauttamisen. Useimmissa sovelluksissa esitelty toiminnallisuus tarjoaa vankan perustan työskentelylle JSONin kanssa Clojure-sovelluksissa.
