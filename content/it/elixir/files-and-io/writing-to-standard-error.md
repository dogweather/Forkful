---
title:                "Scrivere sull'errore standard"
aliases:
- /it/elixir/writing-to-standard-error/
date:                  2024-02-03T19:32:58.527585-07:00
model:                 gpt-4-0125-preview
simple_title:         "Scrivere sull'errore standard"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/elixir/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa & Perché?

Scrivere su standard error (stderr) in Elixir è un metodo per indirizzare messaggi di errore e diagnostica separatamente dall'output principale (stdout). I programmatori usano stderr per effettuare il debug e gestire gli errori senza ingombrare l'output principale del programma, rendendo più facile identificare e affrontare i problemi.

## Come fare:

In Elixir, puoi utilizzare funzioni del modulo `IO` come `IO.puts/2` e `IO.warn/2` per scrivere messaggi su standard error:

```elixir
# Scrittura di un semplice messaggio su stderr
IO.puts(:stderr, "Errore: Qualcosa è andato storto!")

# Utilizzando IO.warn, che è più semantico per avvisi/errori
IO.warn("Avviso: Stai per superare il limite!")
```

Output di esempio nel terminale per `IO.puts/2`:
```
Errore: Qualcosa è andato storto!
```

Per `IO.warn/2`, l'output sarebbe simile, ma `IO.warn/2` è specificamente progettato per avvisi e potrebbe includere una formattazione o un comportamento aggiuntivi nelle future versioni di Elixir.

**Utilizzo di Librerie di Terze Parti**

Sebbene la libreria standard di Elixir sia solitamente sufficiente per gestire l'output di errore standard, potresti trovare utili librerie come `Logger` per applicazioni più complesse o per configurare diversi livelli di log e output.

Esempio utilizzando `Logger` per output di un messaggio di errore:

```elixir
require Logger

# Configurazione di Logger per output su stderr
Logger.configure_backend(:console, device: :stderr)

# Scrittura di un messaggio di errore
Logger.error("Errore: Impossibile connettersi al database.")
```

Questa configurazione indirizza specificamente l'output di `Logger` su stderr, il che è utile per separare la registrazione degli errori dai messaggi di log standard.
