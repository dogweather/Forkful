---
aliases:
- /it/c-sharp/using-an-interactive-shell-repl/
date: 2024-01-26 04:12:07.190629-07:00
description: "Un REPL, o Ciclo Leggi-Valuta-Stampa, ti permette di digitare codice\
  \ C# ed eseguirlo interattivamente. I programmatori lo utilizzano per esperimenti\u2026"
lastmod: 2024-02-18 23:08:55.889409
model: gpt-4-0125-preview
summary: "Un REPL, o Ciclo Leggi-Valuta-Stampa, ti permette di digitare codice C#\
  \ ed eseguirlo interattivamente. I programmatori lo utilizzano per esperimenti\u2026"
title: Utilizzo di un interprete interattivo (REPL)
---

{{< edit_this_page >}}

## Cosa & Perché?
Un REPL, o Ciclo Leggi-Valuta-Stampa, ti permette di digitare codice C# ed eseguirlo interattivamente. I programmatori lo utilizzano per esperimenti rapidi, debugging o per imparare C#, senza l'onere di configurare interi progetti.

## Come fare:
Avvia un REPL nel tuo ambiente C# utilizzando la finestra Interattiva C# o esegui `dotnet-script` nel tuo terminale. Ecco un assaggio di come usarlo:

```csharp
> var saluto = "Ciao, REPL!";
> Console.WriteLine(saluto);
Ciao, REPL!
>
```

Ricevi feedback immediati. Nessun passaggio di compilazione ed esecuzione. Solo codificare e vedere.

## Approfondimento
REPL è passato da Lisp ai linguaggi moderni, prosperando in quelli dinamici come Python. Con C#, Roslyn ha avvicinato il REPL agli sviluppatori. `csi` per Roslyn e `dotnet-script` per .NET Core, sono opzioni solide. Un taglio più profondo: valutano il codice riga per riga, non tutto insieme, un modello di esecuzione diverso rispetto alle tipiche applicazioni C#. Questo incide sulla persistenza dello stato attraverso le esecuzioni e l'ambito delle variabili.

La finestra C# Interattiva di Visual Studio è un REPL alimentato da Roslyn. Ha Intellisense, molteplici riferimenti e supporto ai pacchetti NuGet. Un bel passo avanti rispetto ai primi esperimenti da linea di comando.

Per lingue alternative, Python utilizza `IDLE`, JavaScript ha il REPL di Node.js, e F# viene fornito con `F# Interactive`. Ognuno favorisce cicli di feedback istantanei, inestimabili per testare piccoli snippet di codice o comprendere le funzionalità del linguaggio.

## Vedi Anche
- [REPL `dotnet-script` di .NET Core](https://github.com/filipw/dotnet-script)
