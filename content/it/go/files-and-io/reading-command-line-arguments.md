---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:06:12.760859-07:00
description: "Leggere gli argomenti da linea di comando in Go implica l'estrazione\
  \ degli argomenti forniti a un programma durante la sua invocazione dal terminale\
  \ o dal\u2026"
lastmod: '2024-03-13T22:44:42.924842-06:00'
model: gpt-4-0125-preview
summary: Leggere gli argomenti da linea di comando in Go implica l'estrazione degli
  argomenti forniti a un programma durante la sua invocazione dal terminale o dal
  prompt dei comandi.
title: Lettura degli argomenti da linea di comando
weight: 23
---

## Come fare:
Go offre un accesso diretto agli argomenti della linea di comando tramite il pacchetto `os`, in particolare usando `os.Args`, un array di stringhe. Ecco un semplice esempio per iniziare:

```go
package main

import (
    "fmt"
    "os"
)

func main() {
    // os.Args offre accesso agli argomenti raw della linea di comando
    fmt.Println("Argomenti della linea di comando:", os.Args)

    if len(os.Args) > 1 {
        // Ciclo attraverso gli argomenti, saltando il primo (nome del programma)
        for i, arg := range os.Args[1:] {
            fmt.Printf("Argomento %d: %s\n", i+1, arg)
        }
    } else {
        fmt.Println("Nessun argomento da linea di comando fornito.")
    }
}
```

Un esempio di output quando eseguito con `go run yourprogram.go arg1 arg2` potrebbe sembrare:

```
Argomenti della linea di comando: [/tmp/go-build123456789/b001/exe/yourprogram arg1 arg2]
Argomento 1: arg1
Argomento 2: arg2
```

Questo stampa tutti gli argomenti inclusi il nome del programma (spesso all'indice 0), poi itera su ogni argomento fornito, stampandoli. Per un parsing degli argomenti più controllato, potresti considerare il pacchetto `flag` per l'analisi delle opzioni della linea di comando.

## Approfondimento
Storicamente, l'accesso agli argomenti della linea di comando è una pratica vecchia quanto la programmazione in C, dove `argc` e `argv[]` servono a uno scopo simile. In Go, `os.Args` rende il processo diretto ma deliberatamente rudimentale. Per scenari più complessi, come la gestione di flag o opzioni, Go offre il pacchetto `flag` che fornisce solide capacità di parsing. Questo potrebbe essere visto come un'alternativa "migliore" quando la tua applicazione richiede più che semplici argomenti posizionali.

A differenza di alcuni linguaggi di scripting che offrono il parsing incorporato degli argomenti della linea di comando in array associativi o oggetti, l'approccio di Go richiede che i programmatori gestiscano manualmente il parsing usando `os.Args` per le esigenze di base o per sfruttare il pacchetto `flag` per scenari più avanzati. Questo design riflette la filosofia di Go di mantenere il linguaggio core semplice fornendo allo stesso tempo potenti librerie standard per compiti comuni. Mentre può introdurre una leggera curva di apprendimento per coloro che sono abituati al parsing incorporato, offre maggiore flessibilità e incoraggia una più profonda comprensione della gestione degli argomenti da linea di comando.
