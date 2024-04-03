---
date: 2024-01-20 17:57:03.302317-07:00
description: "Leggere gli argomenti della linea di comando significa accedere ai dati\
  \ che gli utenti inseriscono quando avviano il tuo programma da terminale. I\u2026"
lastmod: '2024-03-13T22:44:44.066211-06:00'
model: gpt-4-1106-preview
summary: Leggere gli argomenti della linea di comando significa accedere ai dati che
  gli utenti inseriscono quando avviano il tuo programma da terminale.
title: Lettura degli argomenti della riga di comando
weight: 23
---

## How to: (Come fare)
In Ruby, gli argomenti della linea di comando sono accessibili attraverso l'array `ARGV`. Ecco un esempio di base:

```Ruby
# read_arguments.rb
puts "Hai passato #{ARGV.length} argomenti:"
puts ARGV
```

Output esemplificativo dopo aver salvato e eseguito il file come: `ruby read_arguments.rb arg1 arg2 arg3`

```
Hai passato 3 argomenti:
arg1
arg2
arg3
```

Per accedere ad un singolo argomento, usi l'indice:

```Ruby
# first_argument.rb
puts "Il primo argomento è: #{ARGV[0]}"
```

Esegui con: `ruby first_argument.rb pizza`

```
Il primo argomento è: pizza
```

## Deep Dive (Approfondimento)
Leggere gli argomenti della linea di comando è comune nei primi linguaggi di scripting come Perl e Python e Ruby non fa eccezione. Da un punto di vista storico, questo ha permesso agli script di sostituire o integrarsi con i comandi shell. Le alternative includono l'uso di gemme come `OptionParser` o `Thor` per gestire argomenti più complessi e le opzioni con maggiore flessibilità. I dettagli di implementazione sono semplici: `ARGV` è semplicemente un array global e predefinito. Tuttavia, ricorda di non modificarlo direttamente se vuoi preservare i dati inseriti dall'utente per riferimenti futuri nel tuo script.

## See Also (Vedi anche)
- [La documentazione ufficiale di Ruby per ARGV](https://ruby-doc.org/core-2.7.0/ARGF.html)
- [Una guida su come usare OptionParser in Ruby](https://www.rubyguides.com/2018/12/ruby-argv/)
- [Documentazione sulla gemma Thor](http://whatisthor.com/)

Ogni risorsa ti porterà a una migliore comprensione del modo in cui Ruby gestisce gli input da linea di comando e come puoi sfruttarlo per costruire applicazioni più interattive e personalizzabili.
