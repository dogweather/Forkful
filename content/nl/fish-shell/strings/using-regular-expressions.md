---
title:                "Reguliere expressies gebruiken"
aliases:
- nl/fish-shell/using-regular-expressions.md
date:                  2024-01-28T22:09:44.202521-07:00
model:                 gpt-4-0125-preview
simple_title:         "Reguliere expressies gebruiken"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/fish-shell/using-regular-expressions.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Reguliere expressies, of regex, zijn patronen die reeksen van strings beschrijven. Programmeurs gebruiken ze om tekst te zoeken, overeen te komen en te manipuleren - super handig voor het vinden van naalden in data hooibergen.

## Hoe te gebruiken:
De Fish Shell heeft ingebouwde regex-ondersteuning in commando's zoals `string`. Laten we eens duiken in enkele voorbeelden:

**Basiszoekopdracht:**

Vind of "fish" in de string staat:

```fish
echo "I love to fish for fish in my fish tank" | string match -r "fish"
```

Uitvoer:

```
fish
fish
fish
```

**Vanggroepen:**

Extraheer overeenkomende groepen met behulp van haakjes:

```fish
echo "Color: Blue, Code: #0000FF" | string match -r "Color: (\w+)"
```

Uitvoer:

```
Color: Blue
Blue
```

**Tekst Vervangen:**

Vervang "fish" door "shark":

```fish
echo "One fish, two fish, red fish, blue fish" | string replace -ar "fish" "shark"
```

Uitvoer:

```
One shark, two shark, red shark, blue shark
```

## Diep Duiken:
Reguliere expressies komen uit de theoretische informatica, bedacht in de jaren '50. Alternatieven? Zeker, je hebt eenvoudige string zoekopdrachten of parsers voor meer structuur, maar regex is zoet voor snelle en vuile taken. De Fish Shell gebruikt PCRE (Perl Compatible Regular Expressions) onder de motorkap, wat zorgt voor een robuuste set van functies voor patroonmatching.

## Zie Ook:
- Officiële documentatie van Fish Shell: [Het string commando](https://fishshell.com/docs/current/cmds/string.html)
- Regex tutorial voor beginners: [Regular Expressions 101](https://regex101.com/)
- Diepgaand begrip: [Mastering Regular Expressions van Jeffrey Friedl](http://shop.oreilly.com/product/9780596528126.do)
