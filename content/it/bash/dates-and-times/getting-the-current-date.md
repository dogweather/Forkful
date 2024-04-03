---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:50.831419-07:00
description: "Il recupero della data corrente in Bash comporta l'utilizzo di comandi\
  \ integrati per visualizzare la data e l'ora in vari formati. I programmatori\u2026"
lastmod: '2024-03-13T22:44:43.610208-06:00'
model: gpt-4-0125-preview
summary: Il recupero della data corrente in Bash comporta l'utilizzo di comandi integrati
  per visualizzare la data e l'ora in vari formati.
title: Ottenere la data corrente
weight: 29
---

## Come fare:
In Bash, il comando `date` è il tuo strumento principale per ottenere la data e l'ora correnti. Ecco alcuni esempi di come usarlo:

1. **Ottenere la data e l'ora correnti nel formato predefinito:**

```bash
date
```

*Output di esempio:*
```
Mer Apr 5 14:22:04 PDT 2023
```

2. **Personalizzare il formato dell'output:** Puoi specificare il formato dell'output utilizzando i formati specificatori `+%`. Per esempio, per visualizzare la data nel formato AAAA-MM-GG:

```bash
date "+%Y-%m-%d"
```

*Output di esempio:*
```
2023-04-05
```

3. **Ottenere il timestamp UNIX corrente:** Il timestamp UNIX è il numero di secondi dal Epoch Unix (1 Gennaio 1970). Questo è utile per gli script che eseguono calcoli basati sulle differenze temporali.

```bash
date "+%s"
```

*Output di esempio:*
```
1672877344
```

Nessuna libreria di terze parti popolare è tipicamente utilizzata per questa operazione basilare in Bash poiché il comando `date` integrato fornisce una funzionalità completa. Tuttavia, per manipolazioni di date e orari più avanzate, i programmatori potrebbero utilizzare altri linguaggi di programmazione o strumenti che offrono librerie per l'aritmetica e l'analisi della data, come il modulo `datetime` di Python.
