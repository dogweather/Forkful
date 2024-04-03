---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:13.669953-07:00
description: "Complexe getallen hebben een re\xEBel deel en een imaginair deel (zoals\
  \ `3 + 4i`). Ze worden gebruikt in de techniek, fysica, en bepaalde computerproblemen.\u2026"
lastmod: '2024-03-13T22:44:50.455962-06:00'
model: gpt-4-0125-preview
summary: "Complexe getallen hebben een re\xEBel deel en een imaginair deel (zoals\
  \ `3 + 4i`)."
title: Werken met complexe getallen
weight: 14
---

## Hoe te:
Elixir heeft geen ingebouwde complexe getallen, dus we maken onze eigen of gebruiken een bibliotheek, zoals `ComplexNum`. Hier is een snel voorbeeld met een bib:

```elixir
# Uitgaande van het feit dat je ComplexNum hebt geïnstalleerd
defmodule ComplexMath do
  import ComplexNum

  def add(a, b) do
    ComplexNum.add(a, b)
  end
end

# Maak complexe getallen en tel ze op
c1 = {3, 4}   # vertegenwoordigt 3 + 4i
c2 = {2, -3}  # vertegenwoordigt 2 - 3i
resultaat = ComplexMath.add(c1, c2)
IO.puts "Het resultaat is: #{inspect(resultaat)}"
```

Dit zou uitvoeren:
```
Het resultaat is: {5, 1}
```

Het betekent dat de som van `3 + 4i` en `2 - 3i` `5 + 1i` is.

## Dieper Duiken
Complexe getallen doken op in de geschiedenis omdat gewone oude getallen geen wortels van negatieven konden aanpakken. Pas in de 17e eeuw werden ze serieus genomen, dankzij wiskundigen zoals René Descartes en Gerolamo Cardano.

In Elixir gebruik je vaak tuples zoals `{3, 4}` voor complexe getallen, of gebruik je een speciale bibliotheek om het wiel niet opnieuw uit te vinden. Bibliotheken zijn meestal beter - ze behandelen het ingewikkelde zoals vermenigvuldiging en deling, die lastig worden vanwege de imaginaire eenheid 'i' (ter info: `i` in het kwadraat is gelijk aan `-1`).

## Zie Ook
Bekijk deze bronnen:
- [ComplexNum Bibliotheek](https://hex.pm/packages/complex_num) voor Elixir's pakketbeheer, Hex.
- [Elixir School](https://elixirschool.com/en/), voor geavanceerde Elixir onderwerpen en oefeningen.
- [Erlang -- wiskundemodule](http://erlang.org/doc/man/math.html), die Elixir onder de motorkap gebruikt, voor andere wiskundige behoeften.
