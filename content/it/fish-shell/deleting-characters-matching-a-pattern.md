---
title:                "Eliminazione di caratteri che corrispondono a un pattern"
date:                  2024-01-20T17:42:16.753444-07:00
model:                 gpt-4-1106-preview
simple_title:         "Eliminazione di caratteri che corrispondono a un pattern"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/fish-shell/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## Che Cos'è & Perché?
Rimuovere caratteri che corrispondono a un modello significa filtrare il testo per eliminare specifici caratteri o sequenze di caratteri. Lo facciamo per pulire dati, modificare testo o per preparazione prima dell'elaborazione.

## Come Fare:
Ecco alcuni esempi pratici per rimuovere caratteri usando Fish:

```Fish Shell
# Rimuovere tutte le istanze della lettera 'a' dalla stringa
echo "banana" | string replace -a "a" ""
# Output: bnn

# Rimuovere caratteri che non sono cifre da una stringa
echo "anno 2023" | string match -r "[0-9]+"
# Output: 2023
```

## Approfondimento:
Prima della nascita di Fish, la rimozione di caratteri era dominata da strumenti come `sed` e `awk`. Fish semplifica questo tipo di operazioni con il comando `string`, introdotto nella versione 2.3.0. A differenza di `sed` o `awk`, il comando `string` è integrato direttamente nella shell e non richiede piping complesso o espressioni regolari intricate per funzioni di base.

Gli strumenti alternativi come `grep`, `cut`, o i linguaggi di scripting come Python, offrono anche la rimozione di caratteri tramite espressioni regolari o funzioni di stringa, ma `string` di Fish è la via più diretta per gli utenti della shell.

Al suo interno, la rimozione dei caratteri avviene attraverso il processo di pattern matching, dove la shell confronta il testo con un dato modello e elimina le corrispondenze trovate.

## Vedi Anche:
- Documentazione ufficiale di Fish sul comando `string`: [fishshell.com/docs/current/cmds/string.html](https://fishshell.com/docs/current/cmds/string.html)
- Una guida a `sed` e `awk`: [gnu.org/software/sed/manual/sed.html](https://www.gnu.org/software/sed/manual/sed.html) e [gnu.org/software/gawk/manual/gawk.html](https://www.gnu.org/software/gawk/manual/gawk.html)
- Espressioni regolari (regex) in generale: [regular-expressions.info](https://www.regular-expressions.info/)
