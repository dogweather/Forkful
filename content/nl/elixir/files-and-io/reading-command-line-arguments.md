---
title:                "Commandoregelargumenten lezen"
date:                  2024-01-28T22:05:14.606008-07:00
model:                 gpt-4-0125-preview
simple_title:         "Commandoregelargumenten lezen"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/elixir/reading-command-line-arguments.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Commandoregelargumenten lezen stelt een programma in staat om direct vanuit de terminal gegevens te grijpen—dingen zoals instellingen of bestandsnamen. Programmeurs doen dit om het gedrag van een programma aan te passen zonder de code te veranderen.

## Hoe:

In Elixir is het grijpen van commandoregelargumenten een fluitje van een cent. Gebruik `System.argv()` en je zult ze als een lijst van strings bemachtigen.

```elixir
defmodule CliArgs do
  def main do
    args = System.argv()
    IO.inspect(args)
  end
end

CliArgs.main()
```

Draai dit door `elixir cli_args.exs foo bar baz` te zijn, en verwacht:

```
["foo", "bar", "baz"]
```

Je ziet de argumenten `foo`, `bar` en `baz` daar recht in een Elixir-lijst.

## Diepgaande Bespreking

Historisch gezien zijn commandoregelargumenten zo oud als de weg naar Rome, voortkomend uit vroege CLI-omgevingen. In Elixir is `System.argv()` je trouwe ros voor deze klus. Waarom? Omdat het ingebakken zit in de Erlang VM, waarop Elixir is gebouwd.

Alternatieven? Zeker, je hebt bibliotheken die argumenten voor je ontleden, met toevoeging van vlaggen en opties. Maar voor standaard Elixir is `System.argv()` de weg te gaan.

Wat betreft de implementatie, is het belangrijk te onthouden dat `System.argv()` je alle argumenten als strings geeft. Als je nummers of andere types nodig hebt, zul je ze handmatig moeten converteren. Ook de volgorde doet ertoe. Je eerste commandoregelargument is `List.first(System.argv())`, en zo voort.

## Zie Ook

Voor meer informatie, bekijk:
- [Documentatie van Elixir's System-module](https://hexdocs.pm/elixir/System.html) voor andere handige op het systeem gerelateerde functies.
- [Optparse](https://hexdocs.pm/elixir/OptionParser.html) in de standaardbibliotheek van Elixir, wat een beest is voor het ontleden van commandoregelopties.
- [Documentatie van Erlang's init](http://erlang.org/doc/man/init.html) als je nieuwsgierig bent naar de magie onder de motorkap van de VM die Elixir ondersteunt.
