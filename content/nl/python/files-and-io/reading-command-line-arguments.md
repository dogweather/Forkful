---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:05:23.193443-07:00
description: "Command line argumenten lezen stelt je Python script in staat om netjes\
  \ om te gaan met gebruikersinvoer vanuit de terminal. Waarom? Wel, omdat\u2026"
lastmod: '2024-03-13T22:44:50.391908-06:00'
model: gpt-4-0125-preview
summary: Command line argumenten lezen stelt je Python script in staat om netjes om
  te gaan met gebruikersinvoer vanuit de terminal.
title: Commandoregelargumenten lezen
weight: 23
---

## Hoe:
Door gebruik te maken van Python's `sys` module, kun je die command line argumenten gemakkelijk binnenhalen. Hier is hoe je ze in je script kunt benaderen:

```python
import sys

# Eerste argument is altijd de scriptnaam, dus die slaan we over
argumenten = sys.argv[1:]

# Doe iets met de argumenten
print("Je hebt ingevoerd:", argumenten)
```

Voer je script zo uit:

```bash
python jouw_script.py deze zijn jouw argumenten
```

Voorbeelduitvoer:

```
Je hebt ingevoerd: ['deze', 'zijn', 'jouw', 'argumenten']
```

## Diepgaande Duik
Lang geleden interacteerden mensen met computers via command lines. Daarom hebben de meeste talen, inclusief Python, een manier om command line argumenten te lezen. Zo werden scripts bestuurd voordat GUI's langs kwamen.

Python's `sys.argv` is handig, maar voor de chiquere commando-analyse dans, is er `argparse`. `argparse` is een module voor wanneer je meer nodig hebt dan de basis - zoals wanneer je argumenten namen, types, of standaardwaarden nodig hebben.

Nu, `sys.argv` is gewoon een lijst. Alles wat je doorgeeft is een string, wat het ook is. Er is geen magie; als je getallen wilt, zul je ze zelf moeten converteren met iets als `int()` of `float()`.

## Zie Ook
Voor meer over `sys.argv` en `argparse`, bekijk de Python documenten:

- `sys.argv`: https://docs.python.org/3/library/sys.html#sys.argv
- `argparse` tutorial: https://docs.python.org/3/howto/argparse.html 

En als je echt diep in command line interfaces wilt duiken:

- Click: https://click.palletsprojects.com/en/7.x/
- docopt: http://docopt.org/ 

Happy coding!
