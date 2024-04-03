---
date: 2024-01-26 01:18:09.227740-07:00
description: "Refaktorointi on prosessi, jossa olemassa olevaa koodia uudelleenj\xE4\
  rjestet\xE4\xE4n muuttamatta sen ulkoista k\xE4ytt\xE4ytymist\xE4. Tavoitteena on\
  \ parantaa ei-\u2026"
lastmod: '2024-03-13T22:44:56.235350-06:00'
model: gpt-4-0125-preview
summary: "Refaktorointi on prosessi, jossa olemassa olevaa koodia uudelleenj\xE4rjestet\xE4\
  \xE4n muuttamatta sen ulkoista k\xE4ytt\xE4ytymist\xE4."
title: Koodin refaktorointi
weight: 19
---

## Kuinka:
Siistitään yleinen Elixir-malli. Refaktoroimme `calculate_stats` funktion, joka tekee enemmän kuin sen pitäisi, jakamalla sen pienempiin, uudelleenkäytettäviin osiin.

```elixir
defmodule Stats do
  # Alkuperäinen, refaktoimaton koodi
  def calculate_stats(data) do
    total = Enum.sum(data)
    count = Enum.count(data)
    mean = total / count
    {mean, total}
  end
  
  # Refaktoitu koodi
  def calculate_mean(data), do: Enum.sum(data) / Enum.count(data)
  
  def calculate_total(data), do: Enum.sum(data)
  
  def calculate_stats_refactored(data) do
    mean = calculate_mean(data)
    total = calculate_total(data)
    {mean, total}
  end
end

# Esimerkkituloste
# Ennen refaktorointia
Stats.calculate_stats([1, 2, 3])
# => {2.0, 6}

# Refaktoroinnin jälkeen
Stats.calculate_stats_refactored([1, 2, 3])
# => {2.0, 6}
```
Kuten näet, tulos pysyy samana, mutta nyt meillä on modulaarisia funktioita, joita voidaan käyttää uudelleen ja testata itsenäisesti.

## Syväsukellus
Refaktorointi ei ole uusi konsepti; se on ollut olennainen osa ohjelmointia ohjelmistokehityksen alkuaikoina. Merkittävät teokset, kuten Martin Fowlerin "Refactoring: Improving the Design of Existing Code", tarjoavat perustavanlaatuisia käytäntöjä refaktorointiin, oivalluksia siitä, milloin ja miten niitä tulisi soveltaa.

Vaihtoehtoja manuaaliselle refaktoroinnille sisältävät automatisoidut koodianalyysityökalut, jotka voivat ehdottaa tai jopa suorittaa refaktorointeja. Automatisoidut työkalut eivät kuitenkaan aina ymmärrä koodin koko kontekstia ja saattavat ohittaa hienovaraisuuksia, jotka ihmisarvioija huomaisi.

Toteutuksen yksityiskohdat Elixirissa sisältävät funktionaalisen paradigman ymmärtämisen ja kuvion sovittamisen, vartijalauseiden sekä putkioperaattorin hyödyntämisen selkeän ja tiiviin koodin kirjoittamiseen. Esimerkiksi refaktorointiin kuuluu usein monimutkaisten imperatiivityylisten funktioiden muuntaminen pienemmiksi, yhdistettäviksi funktioiksi, jotka noudattavat Elixiriin kohdistuvaa muuttumattomuuden ja sivuvaikutuksettomien operaatioiden suosimista.

## Katso myös
Lisää tietoa Elixiriin erityisesti liittyvistä refaktorointitekniikoista:

- [Elixiriin viralliset oppaat](https://elixir-lang.org/getting-started/)
- ["Refactoring: Improving the Design of Existing Code" Martin Fowlerilta](https://martinfowler.com/books/refactoring.html), yleisperiaatteista, joita voidaan soveltaa Elixiriin.
- [Credo, staattinen koodianalyysityökalu Elixirille](https://github.com/rrrene/credo), joka kannustaa parhaisiin käytäntöihin.
- [Exercism Elixir Track](https://exercism.org/tracks/elixir), käytännön harjoituksiin, jotka usein sisältävät refaktorointia.
