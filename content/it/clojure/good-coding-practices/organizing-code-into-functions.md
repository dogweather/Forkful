---
date: 2024-01-26 01:09:26.778631-07:00
description: "Organizzare il codice in funzioni significa impacchettare blocchi di\
  \ codice che compiono compiti specifici. Fare ci\xF2 rende il tuo codice pulito,\
  \ pi\xF9\u2026"
lastmod: '2024-03-13T22:44:43.047694-06:00'
model: gpt-4-1106-preview
summary: Organizzare il codice in funzioni significa impacchettare blocchi di codice
  che compiono compiti specifici.
title: Organizzazione del codice in funzioni
weight: 18
---

## Come fare:
Le funzioni in Clojure sono definite con `defn`, seguito da un nome, parametri e corpo. Ecco un esempio veloce.

```Clojure
(defn saluta [nome]
  (str "Ciao, " nome "!"))

(saluta "Alex") ; => "Ciao, Alex!"
```

Ora, diciamo che vogliamo calcolare l'area di un rettangolo. Invece di accatastare tutto insieme, lo separiamo in due funzioni:

```Clojure
(defn area [lunghezza larghezza]
  (* lunghezza larghezza))

(defn stampa-area [lunghezza larghezza]
  (println "L'area è:" (area lunghezza larghezza)))

(stampa-area 3 4) ; => L'area è: 12
```

## Analisi Approfondita
Tempo fa, i programmatori tendevano a concentrare tutta la loro logica in un unico blocco. Era brutto. Poi è arrivata la programmazione strutturata, e le funzioni sono diventate importanti. In Clojure, ogni funzione è di prima classe—puoi manipolarle come qualsiasi altro valore.

Alternative? Alcuni potrebbero smanettare con metodi multipli o funzioni di ordine superiore, ma quelli sono solo spezie nel brodo delle funzioni.

Tutti i dettagli di una funzione: sono immutabili in Clojure, rendendo meno probabile il disordine causato da effetti collaterali. Si basano molto sulla ricorsione invece dei cicli tipici, il che si integra bene con i paradigmi funzionali del linguaggio.

## Vedi Anche
- La guida di Clojure: https://clojure.org/guides/learn/functions
- Fondamenti di Programmazione Funzionale: https://www.braveclojure.com/core-functions-in-depth/
- I discorsi di Rich Hickey: https://changelog.com/posts/rich-hickeys-greatest-hits - per intuizioni sulla filosofia di Clojure.
