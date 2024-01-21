---
title:                "Interpolazione di una stringa"
date:                  2024-01-20T17:50:31.768803-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolazione di una stringa"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/elixir/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
L'interpolazione di stringhe permette di inserire valori variabili all'interno di una stringa. I programmatori la utilizzano per rendere il codice più leggibile e per comporre messaggi dinamicamente.

## How to:
Elixir rende l'interpolazione di stringhe semplice. Usi il carattere `#` seguito da `{}` per includere valori. Ecco come si fa:

```elixir
name = "Luca"
age = 25

message = "Ciao, mi chiamo #{name} e ho #{age} anni."
IO.puts(message)
```

Output:
```
Ciao, mi chiamo Luca e ho 25 anni.
```

Possiamo interpolare espressioni, non solo variabili:

```elixir
IO.puts("5 + 7 = #{5 + 7}")
```

Output:
```
5 + 7 = 12
```

## Deep Dive
L'interpolazione di stringhe in Elixir affonda le radici in linguaggi più antichi come Perl e Ruby. È superiore alla concatenazione di stringhe per efficienza e leggibilità.

Oltre a `#{}`, in altri linguaggi si usano simboli diversi per l'interpolazione. Per esempio in Python si usa `.format()` o le f-strings.

I dettagli di implementazione mostrano che quando interpoliamo una stringa, Elixir trasforma l'intera espressione in un'unico binario. Questo significa prestazioni migliori rispetto alla concatenazione di stringhe multiple.

## See Also
- [Elixir Interpolation: Elixir School](https://elixirschool.com/en/lessons/basics/strings/#interpolation)
- [Elixir's String module documentation](https://hexdocs.pm/elixir/String.html)
- [Elixir Forum for discussion and questions](https://elixirforum.com)