---
title:                "Estrazione di sottostringhe"
aliases:
- /it/fish-shell/extracting-substrings/
date:                  2024-01-20T17:45:42.750012-07:00
model:                 gpt-4-1106-preview
simple_title:         "Estrazione di sottostringhe"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/fish-shell/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why?
Estrarre sottosequenze significa prendere pezzi di stringa, un po' come tagliare una fetta di torta. I programmatori lo fanno per isolare informazioni utili, come dati o comandi specifici.

## How to:
Utilizziamo il comando `string` di Fish per lavorare con le stringhe. Ecco un esempio semplice.

```Fish Shell
set frase "Amo programmare in Fish Shell"
echo $frase | string sub -s 5 -l 11
```
Output:
```
programmare
```

Un altro esempio? Volentieri. Prendiamo solo la prima parola.

```Fish Shell
set frase "Amo programmare in Fish Shell"
echo $frase | string split " " | head -n 1
```
Output:
```
Amo
```

## Deep Dive
Fish, il Friendly Interactive SHell, non ha la stessa storia lunga di bash o zsh, ma dal 2005 ha conquistato molti per la sua facilità d'uso. Parlare di `string`, non è stato sempre così diretto in altri shell. In bash, per esempio, si deve giocare con le parentesi e indici vari. Un esempio bash di estrazione di sottostringa?
```bash
${stringa:posizione:lungezza}
```
In Fish, `string sub` è più intuitivo. Cosa fa? Taglia la stringa, e basta. Il comando `string` fornisce anche altri tool per manipolare stringhe: cerca, rimpiazza, e altro ancora.

## See Also
Dai occhiata a queste risorse per approfondire:
- Documentazione ufficiale di Fish: [fishshell.com/docs/current/index.html](https://fishshell.com/docs/current/index.html)
- Tutorial su stringhe in Fish: [fishshell.com/docs/current/commands.html#string](https://fishshell.com/docs/current/commands.html#string)
- Confronto tra Fish e altri shell: [github.com/jorgebucaran/fisher/wiki/Shell-Comparison](https://github.com/jorgebucaran/fisher/wiki/Shell-Comparison)
