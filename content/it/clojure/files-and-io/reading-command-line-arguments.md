---
date: 2024-01-20 17:55:46.982449-07:00
description: "Leggere gli argomenti della riga di comando permette di passare informazioni\
  \ a un programma all'avvio. I programmatori lo fanno per rendere i loro script\u2026"
lastmod: '2024-03-13T22:44:43.057706-06:00'
model: gpt-4-1106-preview
summary: Leggere gli argomenti della riga di comando permette di passare informazioni
  a un programma all'avvio.
title: Lettura degli argomenti della riga di comando
weight: 23
---

## How to:
Clojure fornisce un modo semplice per accedere agli argomenti della riga di comando tramite la var `*command-line-args*`. Ecco un esempio:

```clojure
; Stampa gli argomenti della riga di comando
(defn print-args []
  (doseq [arg *command-line-args*]
    (println arg)))

(defn -main [& args]
  ; Opzionalmente, puoi passare args a print-args se necessario
  (print-args))
```

Esegui il script con alcuni argomenti:
```shell
$ clojure script.clj ciao mondo
ciao
mondo
```

## Deep Dive
In Clojure, `*command-line-args*` è una var globale impostata ai valori degli argomenti della riga di comando non consumati da Clojure stesso. Questo significa che quando esegui un programma in Clojure, tutto ciò che segue il nome dello script nella riga di comando viene raccolto in questa var.

Prima di Clojure 1.9, potevi utilizzare direttamente `*command-line-args*`, ma ora è consigliato passare gli argomenti usando `& args` nel metodo `-main` e trattarli localmente. Questa pratica migliora la leggibilità e la portabilità del codice.

Se cerchi alternative, puoi considerare librerie di terze parti come `tools.cli`, che offre funzionalità avanzate per l'analisi degli argomenti della riga di comando, inclusa la validazione e l'elaborazione di flag e opzioni.

## See Also
- Ufficiale [Clojure CLI tools guide](https://clojure.org/guides/deps_and_cli)
- Libreria [tools.cli](https://github.com/clojure/tools.cli) per funzionalità avanzate di gestione degli argomenti della command line
