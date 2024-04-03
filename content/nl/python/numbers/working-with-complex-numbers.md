---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:35.460269-07:00
description: "Complexe getallen zijn een set van getallen in de vorm `a + bi`, waar\
  \ `a` en `b` re\xEBle getallen zijn, en `i` de imaginaire eenheid is (`i^2 = -1`).\
  \ In\u2026"
lastmod: '2024-03-13T22:44:50.370366-06:00'
model: gpt-4-0125-preview
summary: "Complexe getallen zijn een set van getallen in de vorm `a + bi`, waar `a`\
  \ en `b` re\xEBle getallen zijn, en `i` de imaginaire eenheid is (`i^2 = -1`)."
title: Werken met complexe getallen
weight: 14
---

## Hoe te:
Python heeft ingebouwde ondersteuning voor complexe getallen. Hier is hoe je ermee kunt spelen:

```Python
# Creëren van complexe getallen
z = 4 + 5j
print(z)  # Uitvoer: (4+5j)

# Toegang tot reële en imaginaire delen
print(z.real)  # Uitvoer: 4.0
print(z.imag)  # Uitvoer: 5.0

# Complexe rekenkunde
w = 1 - 2j
print(z + w)  # Uitvoer: (5+3j)
print(z - w)  # Uitvoer: (3+7j)
print(z * w)  # Uitvoer: (14+2j)
print(z / w)  # Uitvoer: (-3.6+1.2j)

# Modulus (absolute waarde)
print(abs(z))  # Uitvoer: 6.4031242374328485

# Conjugaat van een complex getal
print(z.conjugate())  # Uitvoer: (4-5j)
```

## Diepere Verkenning
Complexe getallen werden voor het eerst geconceptualiseerd door Gerolamo Cardano in de 16e eeuw. Python, onder andere programmeertalen, behandelt complexe getallen als eersteklas burgers. Dit betekent dat ze in de taal zijn ingebouwd, met gemakkelijk te gebruiken functies, en dat het niet nodig is om externe bibliotheken te importeren voor basisbewerkingen.

Echter, voor zware numerieke berekeningen heeft Python een bibliotheek genaamd `cmath`, die specifiek voor complexe getallen is. Het heeft extra functies zoals `exp`, `log`, en trigonometrische operaties.

Wanneer Python niet voldoende is, kun je je wenden tot bibliotheken zoals NumPy, vooral voor arraybewerkingen met complexe getallen. NumPy biedt geoptimaliseerde en gevectoriseerde operaties die cruciaal zijn voor prestaties in numerieke computing.

## Zie Ook
Bekijk deze bronnen om meer te leren:

- De officiële documentatie van Python over complexe getallen: https://docs.python.org/3/library/stdtypes.html#typesnumeric
- De documentatie van de `cmath` module: https://docs.python.org/3/library/cmath.html
- NumPy voor het omgaan met arrays van complexe getallen: https://numpy.org/doc/stable/user/absolute_beginners.html#the-basics
