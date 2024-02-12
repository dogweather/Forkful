---
title:                "Koodin refaktorointi"
aliases:
- /fi/clojure/refactoring/
date:                  2024-01-26T01:17:35.514927-07:00
model:                 gpt-4-0125-preview
simple_title:         "Koodin refaktorointi"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/clojure/refactoring.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?

Refaktorointi on prosessi, jossa olemassa olevaa tietokonekoodia uudelleenjärjestetään muuttamatta sen ulkoista käyttäytymistä, tarkoituksena parantaa toiminnallisia ominaisuuksia. Ohjelmoijat refaktoroivat tehdäkseen koodistaan puhtaampaa, tehokkaampaa ja helpommin ylläpidettävää, tehden ohjelmistostaan helpommin luettavaa ja vähentäen sen monimutkaisuutta.

## Kuinka:

Refaktorointi Clojuressa—kiitos sen selkeän syntaksin ja funktionaalisen paradigman—voi olla erittäin suoraviivaista. Käsitellään yleistä skenaariota: kokoelmien iterointi. Saatat aloittaa `for`-silmukalla, näin:

```clojure
(defn calculate-sum [numbers]
  (reduce + 0 numbers))

(defn old-way []
  (let [nums (range 1 11)]
    (calculate-sum nums)))
```

Kun kutsutaan `(old-way)`, saamme 55, summan 1:stä 10:een. Mutta, hei, voimme refaktoroida tämän olemaan enemmän Clojure-mielinen:

```clojure
(defn new-way []
  (->> (range 1 11)
       (reduce +)))
```

Tämä refaktoroitu `(new-way)` funktio käyttää säikeistysmakroja välittämään rangen suoraan `reduce`-funktioon, karsien ylimääräistä rasvaa.

## Syväsukellus

Refaktoroinnin taito juontaa juurensa ohjelmistokehityksen alkuaikoihin, mutta se todella saavutti suosiota Martin Fowlerin merkittävän kirjan "Refaktorointi: Olemassa olevan koodin suunnittelun parantaminen" myötä, joka julkaistiin vuonna 1999. Clojuressa refaktorointi nojaa usein funktionaalisen ohjelmoinnin periaatteisiin, suosien puhtaita funktioita ja muuttumattomia tietorakenteita.

Manuaalisen refaktoroinnin vaihtoehtoihin Clojuressa voisi kuulua työkalujen, kuten Cursive, käyttö, joka on suosittu IntelliJ IDEA -laajennus, tarjoten automatisoituja refaktorointeja erityisesti Clojurelle. On myös clj-refactor, Emacs-paketti Clojurelle, joka tarjoaa joukon refaktorointifunktioita.

Erityisen haasteen Clojuressa refaktorointiin tuo tilan ja sivuvaikutusten käsittely pääosin muuttumattomassa ja sivuvaikutuksettoman paradigman puitteissa. Atomien, viitteiden, agenttien ja väliaikaisten tietorakenteiden huolellinen käyttö on keskeistä suorituskyvyn ja oikeellisuuden ylläpitämiseksi refaktoroidessa.

## Katso Myös

- Martin Fowlerin "Refaktorointi: Olemassa olevan koodin suunnittelun parantaminen" peruskäsitteille.
- [Clojure Docs](https://clojuredocs.org/) erityisille esimerkeille idiomaattisesta Clojure-koodista.
- [clj-refactor](https://github.com/clojure-emacs/clj-refactor.el) refaktoroinnin automatisaatiosta Emacsissa.
- [Cursive](https://cursive-ide.com/) IntelliJ-käyttäjille, jotka etsivät automatisoitua refaktorointiapua.
- [Refaktorointi Rich Hickeyn kanssa](https://www.infoq.com/presentations/Simple-Made-Easy/) - Puhe Clojuren luojalta, joka, vaikka ei sinänsä käsittelekään refaktorointia, tarjoaa näkemyksiä Clojure-filosofiaan, joka voi ohjata tehokkaita refaktorointipäätöksiä.
