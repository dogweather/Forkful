---
title:                "Ricerca e sostituzione del testo"
date:                  2024-01-20T17:57:40.968656-07:00
model:                 gpt-4-1106-preview
simple_title:         "Ricerca e sostituzione del testo"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/elixir/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why?
Cercare e sostituire testo è fondamentale per manipolare stringhe e automatizzare l'editing. I programmatori lo fanno per correggere errori, aggiornare codici o dati, e semplificare la refactoring.

## How to:
Elixir rende semplice la ricerca e sostituzione con la funzione `String.replace/4`. Vediamo qualche esempio:

```elixir
original = "Ciao, mondo! Programming in Elixir è divertente."
# Sostituzione semplice
updated = String.replace(original, "divertente", "fantastico")
IO.puts updated
# Output: Ciao, mondo! Programming in Elixir è fantastico.

# Sostituzione con espressioni regolari
regex_updated = String.replace(original, ~r/mondo!/, "amici!")
IO.puts regex_updated
# Output: Ciao, amici! Programming in Elixir è divertente.

# Sostituzione di tutte le occorrenze
all_updated = String.replace(original, "i", "o", global: true)
IO.puts all_updated
# Output: Cao, mondo! Programmong on Eloxor è dovertente.
```

## Deep Dive:
La ricerca e sostituzione nel testo in Elixir usa le espressioni regolari di Erlang, ereditate da PERL, un linguaggio noto per il suo potente maneggio delle stringhe. Altre opzioni includono la creazione di funzioni ricorsive su liste di caratteri o l'uso di librerie come `Regex`.

L'implementazione di Elixir sfrutta le caratteristiche funzionali e di concorrenza di Erlang VM per performare anche su grandi quantità di testo. Malgrado ciò, per lavori di editing molto pesanti o specifici, potrebbero esserci strumenti dedicati più efficienti.

## See Also:
- [Elixir String Docs](https://hexdocs.pm/elixir/String.html)
- [Elixir Regex Docs](https://hexdocs.pm/elixir/Regex.html)
- [Programming Elixir](https://pragprog.com/titles/elixir16/programming-elixir-1-6/) - libro per approfondire Elixir
