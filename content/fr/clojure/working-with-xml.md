---
title:                "Travailler avec XML"
date:                  2024-01-26T04:29:03.622343-07:00
model:                 gpt-4-0125-preview
simple_title:         "Travailler avec XML"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/clojure/working-with-xml.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
XML est un langage de balisage pour encoder des documents d'une manière qui est à la fois lisible par l'homme et par la machine. Il est clé dans les services web, les fichiers de configuration et l'échange de données car il transporte des données dans un format structuré et hiérarchique.

## Comment faire :
Clojure propose la bibliothèque `clojure.data.xml` pour l'analyse et l'émission de XML. Tout d'abord, analysons un peu de XML :

```clojure
(require '[clojure.data.xml :as xml])

(let [contenu "<root><foo>bar</foo><foo>baz</foo></root>"
      analysé (xml/parse-str contenu)] ; Analyse de la chaîne XML
  (println analysé))
```
Sortie :
```
Element{:tag :root, :attrs {}, :content (Element{:tag :foo, :attrs {}, :content ("bar")} Element{:tag :foo, :attrs {}, :content ("baz")})}
```

Pour émettre du XML à partir de structures Clojure :

```clojure
(def mon-xml (xml/element :root {}
                          (xml/element :foo {} "bar")
                          (xml/element :foo {} "baz")))

(println (xml/emit-str mon-xml))
```
Sortie :
```
<root><foo>bar</foo><foo>baz</foo></root>
```

## Plongée Profonde
XML est dans le circuit depuis les années 90, démarrant comme un sous-ensemble simplifié de SGML, destiné aux données web. Son utilisation a explosé avec des technologies comme SOAP et XHTML, mais il a eu un peu de concurrence avec JSON, qui est préféré pour sa légèreté et sa simplicité.

L'approche de Clojure vis-à-vis du XML le maintient fonctionnel et axé sur les données, restant fidèle à l'éthos du langage. `clojure.data.xml` est seulement une option ; vous avez `clojure.xml` pour les besoins basiques, et pour l'interopérabilité Java, vous pouvez jouer avec des poids lourds comme JAXB ou DOM4J.

Gardez à l'esprit que les performances et la surcharge de mémoire lors du traitement de documents XML très grands peuvent être lourdes. Les parseurs en streaming comme StAX peuvent aider, mais vous devrez passer en Java-land pour les utiliser.

## Voir Aussi
- [clojure.data.xml GitHub](https://github.com/clojure/data.xml)
- [API Java pour le Traitement XML (JAXP)](https://docs.oracle.com/javase/tutorial/jaxp/index.html)
- [StAX](https://docs.oracle.com/javase/tutorial/jaxp/stax/index.html)
