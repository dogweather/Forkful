---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:14.302404-07:00
description: "Scrivere su standard error (stderr) in Bash consiste nel dirigere messaggi\
  \ di errore o qualsiasi output diagnostico importante separatamente dall'output\u2026"
lastmod: '2024-03-13T22:44:43.616033-06:00'
model: gpt-4-0125-preview
summary: Scrivere su standard error (stderr) in Bash consiste nel dirigere messaggi
  di errore o qualsiasi output diagnostico importante separatamente dall'output standard
  (stdout).
title: Scrivere sull'errore standard
weight: 25
---

## Come fare:
In Bash, si usa `>&2` per reindirizzare l'output su stderr. Ecco un esempio basilare:

```bash
echo "Questo è un messaggio normale"
echo "Questo è un messaggio di errore" >&2
```

Eseguendo questo script verranno visualizzati entrambi i messaggi sulla console, ma se li reindirizzate, potete separare lo stdout dallo stderr. Ad esempio:

```bash
bash script.sh > output.txt 2> error.txt
```

`output.txt` conterrà `"Questo è un messaggio normale"`, mentre `error.txt` catturerà `"Questo è un messaggio di errore"`.

Per un caso d'uso pratico, considerate uno script che elabora file e segnala un errore se un file non esiste:

```bash
filename="example.txt"

if [ ! -f "$filename" ]; then
    echo "$filename non esiste!" >&2
    exit 1
else
    echo "Elaborazione di $filename"
fi
```

Output di esempio direttamente nella console quando `example.txt` non esiste:

```
example.txt non esiste!
```

Non esistono librerie di terze parti in Bash per la gestione dello stderr, poiché il reindirizzamento è nativamente supportato ed è generalmente sufficiente. Tuttavia, per applicazioni complesse, framework di logging o strumenti di logging esterni come `syslog` o `log4bash` possono essere incorporati per gestire sia lo stdout che lo stderr in modo più efficace.
