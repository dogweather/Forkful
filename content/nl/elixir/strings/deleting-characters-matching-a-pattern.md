---
title:                "Karakters verwijderen die overeenkomen met een patroon"
aliases:
- nl/elixir/deleting-characters-matching-a-pattern.md
date:                  2024-01-28T21:58:33.659824-07:00
model:                 gpt-4-0125-preview
simple_title:         "Karakters verwijderen die overeenkomen met een patroon"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/elixir/deleting-characters-matching-a-pattern.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Het verwijderen van karakters die overeenkomen met een patroon gaat helemaal om het vinden van specifieke reeksen van karakters en het verwijderen ervan. Programmeurs doen dit om data te saneren, inhoud te formatteren, of strings te manipuleren op een manier die overeenkomt met hun specifieke behoeften.

## Hoe te:

In Elixir, gebruik de `String.replace/4` functie om karakters te verwijderen die overeenkomen met een patroon. Bekijk deze voorbeelden:

```elixir
# Verwijder cijfers uit een string
original_string = "Elixir2023Rocks!"
clean_string = String.replace(original_string, ~r/\d/, "")
IO.puts(clean_string) # Uitvoer: "ElixirRocks!"

# Verwijder leestekens
punctuationless_string = String.replace(original_string, ~r/[[:punct:]]/, "")
IO.puts(punctuationless_string) # Uitvoer: "Elixir2023Rocks"

# Verwijder witruimte
no_whitespace_string = String.replace(original_string, ~r/\s/, "")
IO.puts(no_whitespace_string) # Uitvoer: "Elixir2023Rocks!"
```

## Diepgaande duik

Het gebruik van patroonmatching om karakters in strings te verwijderen is niet uniek voor Elixir; het is een algemeen kenmerk in bijna alle programmeertalen, ontwikkeld uit de mogelijkheden van reguliere expressies (regex) in vroege Unix-tools zoals `sed` en `grep`. Alternatieven voor `String.replace/4` kunnen zijn het gebruik van patroonmatching en recursie om handmatig door een string te gaan en deze aan te passen, maar deze methode is over het algemeen uitgebreider en complexer, waardoor ingebouwde regex-functies een voor de hand liggende keuze zijn. Intern maakt `String.replace/4` gebruik van de Erlang-erfenis van Elixir, door de krachtige patroonmatching en stringmanipulatie-mogelijkheden van de BEAM-virtuele machine te benutten.

## Zie ook:

- Elixir `String` module documentatie: [https://hexdocs.pm/elixir/String.html](https://hexdocs.pm/elixir/String.html)
- Regex in Elixir: [https://hexdocs.pm/elixir/Regex.html](https://hexdocs.pm/elixir/Regex.html)
- 'Leer Reguliere Expressies': [https://www.regular-expressions.info/tutorial.html](https://www.regular-expressions.info/tutorial.html)
- Elixir School's kijk op strings en patroonmatching: [https://elixirschool.com/en/lessons/basics/strings/](https://elixirschool.com/en/lessons/basics/strings/)
