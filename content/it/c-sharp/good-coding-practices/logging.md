---
date: 2024-01-26 01:01:04.480318-07:00
description: "Il logging \xE8 il processo di registrazione degli eventi dell'applicazione\
  \ e dei dati in output durante l'esecuzione. I programmatori effettuano il logging\u2026"
lastmod: '2024-03-13T22:44:43.440080-06:00'
model: gpt-4-1106-preview
summary: "Il logging \xE8 il processo di registrazione degli eventi dell'applicazione\
  \ e dei dati in output durante l'esecuzione."
title: Registrazione Eventi (Logging)
weight: 17
---

## Come fare:
In C#, puoi usare il namespace integrato `System.Diagnostics` o librerie di terze parti come NLog o log4net. Ecco un esempio rapido che utilizza l'interfaccia `ILogger` disponibile in .NET Core:

```C#
using Microsoft.Extensions.Logging;
using System;

public class Program
{
    public static void Main()
    {
        using var loggerFactory = LoggerFactory.Create(builder => {
            builder.AddConsole();
        });

        ILogger logger = loggerFactory.CreateLogger<Program>();

        logger.LogInformation("Questo è un messaggio informativo.");
        logger.LogWarning("Questo è un messaggio di avvertimento.");
        logger.LogError("Questo è un messaggio di errore.");
    }
}
```

Output di esempio:
```
info: Program[0]
      Questo è un messaggio informativo.
warn: Program[0]
      Questo è un messaggio di avvertimento.
fail: Program[0]
      Questo è un messaggio di errore.
```

## Approfondimento
La storia del logging nello sviluppo del software è quasi vecchia quanto la programmazione stessa; si è evoluta da semplici dichiarazioni di stampa a sistemi sofisticati e configurabili. Originariamente, il logging veniva effetuato scrivendo su file o sulla console, ma questo si è ampliato per includere strutture più complesse come i sistemi di aggregazione dei log e le piattaforme di tracciamento distribuito (come lo stack ELK o Jaeger).

Alternative al logging integrato in .NET includono librerie di terze parti:
- **NLog**: versatile e facile da configurare, con molte funzionalità per l'instradamento, la formattazione e il filtraggio dei log.
- **log4net**: ispirato dalla libreria Java log4j, è altamente configurabile tramite XML e supporta una varietà di repository di log.

Quando si tratta di dettagli implementativi, la scelta dell'astrazione di logging (come Microsoft.Extensions.Logging) e del provider di logging sottostante può influenzare significativamente le prestazioni e l'affidabilità della tua applicazione. È cruciale configurare adeguatamente i livelli di logging e assicurarsi che la scrittura dei log non diventi un collo di bottiglia.

Inoltre, il logging strutturato - dove si registrano non solo stringhe ma coppie chiave-valore o oggetti - permette di ottenere log più precisi e utili, che sono più facili da interrogare e analizzare.

## Vedi Anche
- [Documentazione Microsoft.Extensions.Logging](https://docs.microsoft.com/it-it/aspnet/core/fundamentals/logging/)
- [Documentazione NLog](https://nlog-project.org/documentation/)
- [Documentazione log4net](https://logging.apache.org/log4net/)
- [Documentazione Serilog](https://serilog.net/) (per un esempio di logging strutturato)
