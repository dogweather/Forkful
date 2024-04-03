---
date: 2024-01-26 04:17:08.792030-07:00
description: "REPL, eli Read-Eval-Print -silmukka, on ohjelmointiymp\xE4rist\xF6,\
  \ joka ottaa vastaan yksitt\xE4isi\xE4 k\xE4ytt\xE4j\xE4n sy\xF6tteit\xE4, suorittaa\
  \ ne ja palauttaa tuloksen\u2026"
lastmod: '2024-03-13T22:44:56.145291-06:00'
model: gpt-4-0125-preview
summary: "REPL, eli Read-Eval-Print -silmukka, on ohjelmointiymp\xE4rist\xF6, joka\
  \ ottaa vastaan yksitt\xE4isi\xE4 k\xE4ytt\xE4j\xE4n sy\xF6tteit\xE4, suorittaa\
  \ ne ja palauttaa tuloksen k\xE4ytt\xE4j\xE4lle."
title: "Interaktiivisen komentotulkin (REPL) k\xE4ytt\xF6"
weight: 34
---

## Kuinka:
Siirry suoraan Pythonin REPL-iin kirjoittamalla `python` komentoriville. Siellä voit testata yksinkertaisia toimintoja tai monirivikoodia:

```Python
>>> 1 + 1
2
>>> for i in range(3):
...     print(i)
... 
0
1
2
```

Kokeile funktioita ja välitöntä palautetta:

```Python
>>> def greet(name):
...     return "Hei, " + name + "!"
... 
>>> greet("Alice")
'Hei, Alice!'
```

Leiki kirjastoilla ja tutki niiden ominaisuuksia reaaliajassa:

```Python
>>> import math
>>> math.sqrt(16)
4.0
```

Poistu nopeasti komennolla `exit()` tai `Ctrl+D` (joskus Windowsissa `Ctrl+Z`).

## Syväsukellus
REPL:n konsepti ei ole ainutlaatuinen Pythonille; se on yhtä vanha kuin Lisp. Monet kielet tarjoavat tämän välittömän, interaktiivisen ympäristön käsillä pidettävään koodaamiseen. Vaihtoehtoja natiiville Python-kuorelle ovat IPython ja Jupyter Notebook, jotka tarjoavat parannettua interaktiivisuutta, lisää ominaisuuksia ja paremman integraation muiden työkalujen kanssa. Pythonin standardi REPL on yksinkertainen, mutta se sisältää Pythonin täyden voiman, käsitellen monimutkaisia objekteja ja monisäikeisiä ohjelmia, vaikkakin sekaan puuttuvat edistyneemmissä työkaluissa esiintyvät ominaisuudet, kuten automaattinen täydennys ja syntaksin korostus.

## Katso Myös
- [Pythonin virallinen dokumentaatio tulkista](https://docs.python.org/3/tutorial/interpreter.html)
- [IPython: Edistynyt Python-kuori](https://ipython.org/)
- [Jupyter-projekti](https://jupyter.org/)
