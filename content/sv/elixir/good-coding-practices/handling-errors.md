---
date: 2024-01-26 00:51:10.385167-07:00
description: "Att hantera fel inneb\xE4r att skriva kod som kan hantera n\xE4r saker\
  \ g\xE5r snett. Programmerare g\xF6r det f\xF6r att undvika krascher och f\xF6r\
  \ att f\xF6rs\xE4kra sig om att\u2026"
lastmod: '2024-03-13T22:44:37.574850-06:00'
model: gpt-4-1106-preview
summary: "Att hantera fel inneb\xE4r att skriva kod som kan hantera n\xE4r saker g\xE5\
  r snett."
title: Hantering av fel
weight: 16
---

## Hur man gör:
I Elixir använder vi ofta mönstermatchning och `case`-satsen för att hantera olika utfall, inklusive fel.

```elixir
defmodule Exempel do
  def dela(a, b) do
    case b do
      0 -> {:error, "Kan inte dela med noll."}
      _ -> {:ok, a / b}
    end
  end
end

# Lyckad division
{:ok, resultat} = Exempel.dela(10, 2)
IO.puts("10 / 2 är #{resultat}")

# Försök att dela med noll
{:error, orsak} = Exempel.dela(10, 0)
IO.puts("Fel: #{orsak}")
```

Exempel på utmatning:
```
10 / 2 är 5.0
Fel: Kan inte dela med noll.
```

När du kör denna Elixir-kod kommer du antingen få en lyckad division eller ett felmeddelande, beroende på din inmatning. Inga krascher här!

## Fördjupning
Förr, handlade felhantering ofta om att kontrollera returvärden. Med Elixirs funktionella rötter har vi dock mönstermatchning och taggade tupler, som `{:ok, värde}` eller `{:error, anledning}`, som är mer eleganta.

Det finns andra sätt att hantera fel i Elixir:

- **Elixirs `try` och `rescue`** som liknar den traditionella `try-catch` i imperativa språk men används mer sällan på grund av Elixirs preferens för explicitthet.
- **Supervisorer och GenServers**, som är en del av Elixirs OTP-ramverk, handlar mer om felfördröjande. De övervakar din kods process, redo att starta om den om något går fel.

När det gäller implementering bygger Elixir på Erlangs robusthet. Det behandlar fel som bara ännu en typ av meddelande som ska hanteras med all mönstermatchning och funktionell finess.

## Se även
För vidare läsning om felhantering i Elixir, kolla in:

- Elixirs officiella guide om [felhantering](https://elixir-lang.org/getting-started/try-catch-and-rescue.html).
- Läs mer om [processer och OTP](https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html).
- Elixir Forum är alltid en bra plats att ställa frågor på: [https://elixirforum.com](https://elixirforum.com).
