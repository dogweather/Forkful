---
aliases:
- /it/fish-shell/searching-and-replacing-text/
date: 2024-01-20 17:57:37.809121-07:00
description: "La ricerca e sostituzione di testo permette di trovare specifiche stringhe\
  \ e cambiarle con altre. Programmatore lo fa per correggere errori, aggiornare\u2026"
lastmod: 2024-02-18 23:08:56.279449
model: gpt-4-1106-preview
summary: "La ricerca e sostituzione di testo permette di trovare specifiche stringhe\
  \ e cambiarle con altre. Programmatore lo fa per correggere errori, aggiornare\u2026"
title: Ricerca e sostituzione del testo
---

{{< edit_this_page >}}

## What & Why?
La ricerca e sostituzione di testo permette di trovare specifiche stringhe e cambiarle con altre. Programmatore lo fa per correggere errori, aggiornare dati o refactoring del codice—insomma, per risparmiare tempo.

## How to:
Ecco alcuni esempi su come cercare e sostituire del testo nella Fish Shell:

Cerca `vecchio` e sostituisci con `nuovo` in un file:

```Fish Shell
sed 's/vecchio/nuovo/g' file.txt > file_modificato.txt
```

Ricerca ricorsiva nel directory `code` e sostituzione in-place:

```Fish Shell
grep -rl 'vecchio' code/ | xargs sed -i 's/vecchio/nuovo/g'
```

Output:
```
code/file1.txt: vecchio → nuovo
code/subdir/file2.txt: vecchio → nuovo
```

## Deep Dive
La sostituzione di testo in Fish si appoggia spesso a sed e grep, comandi UNIX risalenti agli anni '70. Alternative includono strumenti come awk e perl, ma sed è il tradizionale and-to per la sua semplicità. Fish non complica troppo—bastano pochi comandi per lavori potenti.

## See Also
- La pagina man di `sed`: https://www.gnu.org/software/sed/manual/sed.html
- Fish Shell documentazione: https://fishshell.com/docs/current/index.html
- Tutorial di `grep`: https://www.gnu.org/software/grep/manual/grep.html
- Introduzione a `awk`: https://www.gnu.org/software/gawk/manual/gawk.html
