---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:02:10.673998-07:00
description: "Een string interpoleren betekent variabelen of expressies in een string\
  \ invoegen. Het bespaart tijd en verbetert de leesbaarheid door dynamische inhoud\u2026"
lastmod: '2024-03-13T22:44:51.231258-06:00'
model: gpt-4-0125-preview
summary: Een string interpoleren betekent variabelen of expressies in een string invoegen.
title: Een string interpoleren
weight: 8
---

## Hoe doe je dat:
In Fish gebruik je dubbele aanhalingstekens en plaats je de variabele of het commando dat je wilt interpoleren met een dollarteken `$` rechtstreeks in de string.

```fish
set name "world"
echo "Hallo, $name!"
```

Uitvoer:
```
Hallo, wereld!
```

Om de uitvoer van een commando binnen een string op te nemen:

```fish
echo "Ik heb (count (ls)) bestanden in deze map."
```

De uitvoer kan zijn:
```
Ik heb 9 bestanden in deze map.
```

Variabelen en commando's worden beoordeeld en netjes op hun plaats gezet.

## Diepere duik
Vóór Fish en andere moderne shells zou je vaak een onhandige combinatie van aanhalingstekens en concatenatie gebruiken—of vertrouwen op externe tools—om variabelen in strings te krijgen.

In bash zou het er bijvoorbeeld zo uitzien:

```bash
name="world"
echo "Hallo, "$name"!"
```

Niet zo soepel, toch?

Fish maakt dit proces niet alleen gestroomlijnder, maar gaat ook sierlijker om met fouten. Als een variabele niet bestaat, zal Fish een lege string invoegen, waardoor de kans op een crash door slecht beheerde interpolaties vermindert.

Alternatieven voor directe interpolatie zijn het gebruik van het `printf` commando:

```fish
set animal "narwal"
printf "De %s is een geweldig wezen!" $animal
```

Uitvoer:
```
De narwal is een geweldig wezen!
```

In dit geval is `%s` een plaatsvervanger voor de stringvariabele `$animal` die door `printf` wordt vervangen.

Wat de implementatie betreft, wanneer Fish de commandoregel verwerkt, analyseert het de dubbele aanhalingstekens strings en vervangt het de variabelen door hun waarden on the fly. Het is elegant en bootst de variabele interpolatie na die te vinden is in hogere programmeertalen zoals Ruby of PHP.

## Zie ook
Voor meer over Fish stringmanipulatie en scripting, check deze:

- [Fish Shell Documentatie: Quotes](https://fishshell.com/docs/current/index.html#quotes)
- [Fish Shell Tutorial](https://fishshell.com/docs/current/tutorial.html)
- [Stack Overflow: Hoe gebruik je variabelen in een commando in Fish](https://stackoverflow.com/questions/2763006/how-to-use-variables-in-a-command-in-fish)
