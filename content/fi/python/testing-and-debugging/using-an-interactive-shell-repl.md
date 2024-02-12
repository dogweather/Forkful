---
title:                "Interaktiivisen komentotulkin (REPL) käyttö"
aliases:
- /fi/python/using-an-interactive-shell-repl/
date:                  2024-01-26T04:17:08.792030-07:00
model:                 gpt-4-0125-preview
simple_title:         "Interaktiivisen komentotulkin (REPL) käyttö"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/python/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
REPL, eli Read-Eval-Print -silmukka, on ohjelmointiympäristö, joka ottaa vastaan yksittäisiä käyttäjän syötteitä, suorittaa ne ja palauttaa tuloksen käyttäjälle. Ohjelmoijat käyttävät sitä nopeisiin testeihin, oppimiseen, vianetsintään tai laskelmien tekemiseen lennossa.

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
