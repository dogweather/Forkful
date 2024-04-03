---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:30:48.734497-07:00
description: "Scrivere test in Fish Shell comporta la creazione di script che eseguono\
  \ automaticamente il tuo codice per validarne il comportamento rispetto ai\u2026"
lastmod: '2024-03-13T22:44:43.862668-06:00'
model: gpt-4-0125-preview
summary: Scrivere test in Fish Shell comporta la creazione di script che eseguono
  automaticamente il tuo codice per validarne il comportamento rispetto ai risultati
  attesi.
title: Scrivere test
weight: 36
---

## Come fare:
Fish non dispone di un framework di testing integrato come alcuni altri ambienti di programmazione. Tuttavia, puoi scrivere semplici script di test che utilizzano affermazioni per verificare il comportamento delle tue funzioni. Inoltre, puoi sfruttare strumenti di terze parti come `fishtape` per una suite di testing più completa.

### Esempio 1: Script di Test Base
Cominciamo con una funzione base in Fish che calcola la somma di due numeri:

```fish
function add --description 'Add two numbers'
    set -l sum (math $argv[1] + $argv[2])
    echo $sum
end
```

Puoi scrivere uno script di test di base per questa funzione così:

```fish
function test_add
    set -l result (add 3 4)
    if test $result -eq 7
        echo "test_add passed"
    else
        echo "test_add failed"
    end
end

test_add
```

Eseguendo questo script produrrebbe:

```
test_add passed
```

### Esempio 2: Utilizzo di Fishtape
Per una soluzione di test più robusta, puoi utilizzare `fishtape`, un test runner per Fish che produce output TAP.

Prima, installa `fishtape` se non lo hai già fatto:

```fish
fisher install jorgebucaran/fishtape
```

Successivamente, crea un file di test per la tua funzione `add`, ad esempio, `add_test.fish`:

```fish
test "Sommando 3 e 4 si ottiene 7"
    set result (add 3 4)
    echo "$result" | fishtape
end
```

Per eseguire il test, utilizza il seguente comando:

```fish
fishtape add_test.fish
```

Un esempio di output potrebbe essere:

```
TAP version 13
# Sommando 3 e 4 si ottiene 7
ok 1 - test_add passed
```

Questo ti informa che il test è stato superato con successo. `fishtape` permette di strutturare test più dettagliati e fornisce output informativi, facilitando il debugging e garantendo una copertura di test completa per i tuoi script in Fish.
