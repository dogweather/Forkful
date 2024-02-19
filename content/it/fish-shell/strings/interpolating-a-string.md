---
aliases:
- /it/fish-shell/interpolating-a-string/
date: 2024-01-20 17:51:13.626791-07:00
description: "L'interpolazione di stringhe permette di inserire variabili o espressioni\
  \ all'interno di una stringa di testo. Lo facciamo per costruire dinamicamente\u2026"
lastmod: 2024-02-18 23:08:56.280346
model: gpt-4-1106-preview
summary: "L'interpolazione di stringhe permette di inserire variabili o espressioni\
  \ all'interno di una stringa di testo. Lo facciamo per costruire dinamicamente\u2026"
title: Interpolazione di una stringa
---

{{< edit_this_page >}}

## What & Why? (Cosa & Perché?)
L'interpolazione di stringhe permette di inserire variabili o espressioni all'interno di una stringa di testo. Lo facciamo per costruire dinamicamente stringhe, facilitando l'output personalizzato e la manipolazione dei dati.

## How to: (Come fare:)
Ecco come interpolare una stringa in Fish Shell.

```Fish Shell
set nome "Mondo"
echo "Ciao, $nome!"
```

Output:
```
Ciao, Mondo!
```

Più complesso:
```Fish Shell
set prezzo 100
echo "Il costo totale è $(math $prezzo * 1.22) euro, IVA inclusa."
```

Output:
```
Il costo totale è 122 euro, IVA inclusa.
```

## Deep Dive (Approfondimento)
L'interpolazione di stringhe risale ai giorni del telegrafo. Il principio dietro rimane: sostituire un segnaposto con un valore specifico. In Fish Shell, usi il simbolo `$` seguito dal nome della variabile. È diretto e meno prolisso di altri linguaggi che richiedono funzioni o metodi aggiuntivi.

Alcune shell alternative, come Bash o Zsh, hanno approcci leggermente diversi per l'interpolazione di stringhe, che possono comprendere notazioni come `"${var}"` o manipolazioni più complesse. Fish è stato progettato per essere più leggibile e semplice, mirando a evitare errori comuni e rendere lo script più pulito.

Fish implementa l'interpolazione di stringhe nel suo parsing della linea di comando. Quando Fish incontra il carattere `$`, cerca di espandere ciò che segue come variabile. Se esiste, sostituisce il segnaposto con il suo valore.

## See Also (Vedi Anche)
- La documentazione ufficiale di Fish per le stringhe: [Fish Shell String Docs](https://fishshell.com/docs/current/index.html#variables-string)
- Una guida alla sintassi di scripting in Fish: [Fish Scripting Tutorial](https://fishshell.com/docs/current/tutorial.html)
- Confronto tra shell e pratiche comuni: [Awesome Fish](https://github.com/jorgebucaran/awesome-fish)
