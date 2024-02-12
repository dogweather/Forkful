---
title:                "Beräkna ett datum i framtiden eller förflutenheten"
aliases:
- /sv/elixir/calculating-a-date-in-the-future-or-past/
date:                  2024-01-20T17:30:40.559247-07:00
model:                 gpt-4-1106-preview
simple_title:         "Beräkna ett datum i framtiden eller förflutenheten"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/elixir/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Att beräkna ett datum i framtiden eller förflutet innebär att man adderar eller subtraherar tid från ett specifikt datum. Programmerare gör detta för att hantera bokningar, deadlines, påminnelser och tidsbaserade funktioner i appar och system.

## Hur gör man:
```elixir
# Lägger till dagar till dagens datum
{:ok, today} = Date.new(2023, 4, 1)
future_date = Date.add(today, 10)
IO.puts(Date.to_string(future_date))
# "2023-04-11"

# Tar bort dagar från dagens datum
past_date = Date.add(today, -5)
IO.puts(Date.to_string(past_date))
# "2023-03-27"
```

## Djupdykning:
I Elixir kan du hantera datum med inbyggda moduler som `Date` och `DateTime`. Förmågan att manipulera datum är viktig sedan början av datorprogrammering – för att hålla koll på händelser över tid. Alternativ till Elixirs inbyggda moduler inkluderar externa bibliotek som `Timex`, som erbjuder ännu fler funktioner för datum- och tidshantering.

När du arbetar med datum är det viktigt att tänka på tidszoner och hur de påverkar beräkningen. Elixirs `DateTime` kan hantera detta, medan `Date` används för datum utan tid och tidszon. I det allra första exemplet adderar vi 10 dagar till dagens datum. Det andra exemplet visar hur vi kan gå tillbaka i tiden genom att subtrahera dagar.

## Se även:
- Elixir officiella dokumentation för `Date` module: [https://hexdocs.pm/elixir/Date.html](https://hexdocs.pm/elixir/Date.html)
- Timex, ett populärt tredjepartsbibliotek för datum- och tidshantering: [https://hex.pm/packages/timex](https://hex.pm/packages/timex)
- Elixir School, en primer om datum och tid i Elixir: [https://elixirschool.com/en/lessons/basics/date_time/](https://elixirschool.com/en/lessons/basics/date_time/)
