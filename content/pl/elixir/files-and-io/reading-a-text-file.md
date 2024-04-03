---
date: 2024-01-20 17:54:07.059783-07:00
description: "Czytanie pliku tekstowego to po prostu wczytywanie danych z pliku na\
  \ dysku. Programi\u015Bci to robi\u0105, by przetwarza\u0107, analizowa\u0107 dane\
  \ i integrowa\u0107 systemy."
lastmod: '2024-03-13T22:44:35.062026-06:00'
model: gpt-4-1106-preview
summary: Czytanie pliku tekstowego to po prostu wczytywanie danych z pliku na dysku.
title: Odczytywanie pliku tekstowego
weight: 22
---

## How to:
```elixir
# Otwieramy i czytamy plik linia po linii
File.stream!("plik.txt") 
|> Enum.each(fn line -> IO.puts(line) end)

# Wynik:
# Pierwsza linia pliku.
# Druga linia pliku.
```

```elixir
# Wczytujemy całą zawartość pliku na raz
{ok, content} = File.read("plik.txt")
IO.puts(content)

# Wynik:
# Cała zawartość pliku wypisana jednym ciągiem.
```

## Deep Dive
Elixir korzysta z beamowego (wirtualna maszyna Erlanga) modelu obsługi plików. To pochodna erlangowego sposobu czytania plików – niezawodnego i wydajnego. Alternatywą jest otwarcie pliku za pomocą `File.open/2` i ręczne iterowanie. W przypadku dużych plików lepiej użyć `File.stream!/3`, by operować na strumieniach i zmniejszyć zużycie pamięci.

## See Also
- Dokumentacja do `File` modułu Elixir: https://hexdocs.pm/elixir/File.html
- Przewodnik do strumieni i leniwego przetwarzania w Elixirze: https://elixirschool.com/pl/lessons/basics/streams/
