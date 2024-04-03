---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:18:00.323314-07:00
description: "Regul\xE6re uttrykk (regex) er m\xF8nstre som brukes til \xE5 finne\
  \ kombinasjoner av tegn i strenger. Programmerere benytter dem for s\xF8k, redigering\
  \ eller\u2026"
lastmod: '2024-03-13T22:44:40.351068-06:00'
model: gpt-4-0125-preview
summary: "Regul\xE6re uttrykk (regex) er m\xF8nstre som brukes til \xE5 finne kombinasjoner\
  \ av tegn i strenger."
title: "Bruke regul\xE6re uttrykk"
weight: 11
---

## Hvordan:
Å bruke regex i Python involverer `re`-modulen, som tilbyr et sett med funksjoner for å behandle tekst ved hjelp av regulære uttrykk.

### Grunnleggende mønstersøk
For å søke etter et mønster i en streng, bruk `re.search()`. Den returnerer et matchobjekt når mønsteret er funnet, ellers `None`.
```python
import re

tekst = "Lær Python programmering"
match = re.search("Python", tekst)
if match:
    print("Mønster funnet!")
else:
    print("Mønster ikke funnet.")
```
Output:
```
Mønster funnet!
```

### Kompilering av regulære uttrykk
For gjentatt bruk av samme mønster, kompiler det først med `re.compile()` for bedre ytelse.
```python
mønster = re.compile("Python")
match = mønster.search("Lær Python programmering")
if match:
    print("Kompilert mønster funnet!")
```
Output:
```
Kompilert mønster funnet!
```

### Splitting av strenger
For å dele opp en streng ved hvert treff av et regex-mønster, bruk `re.split()`.
```python
resultat = re.split("\s", "Python er gøy")
print(resultat)
```
Output:
```
['Python', 'er', 'gøy']
```

### Finne alle treff
For å finne alle ikke-overlappende forekomster av et mønster, bruk `re.findall()`.
```python
treff = re.findall("n", "Python programmering")
print(treff)
```
Output:
```
['n', 'n']
```

### Erstatte tekst
Bruk `re.sub()` for å erstatte forekomster av et mønster med en ny streng.
```python
erstattet_tekst = re.sub("gøy", "fantastisk", "Python er gøy")
print(erstattet_tekst)
```
Output:
```
Python er fantastisk
```

### Tredjepartsbiblioteker
Selv om Pythons innebygde `re`-modul er kraftig, tilbyr tredjepartsbiblioteker som `regex` flere funksjoner og forbedret ytelse. For å bruke `regex`, installer den via pip (`pip install regex`) og importer den i koden din.

```python
import regex

tekst = "Lærer Python 3.8"
match = regex.search(r"Python\s(\d+\.\d+)", tekst)
if match:
    print(f"Fant versjon: {match.group(1)}")
```
Output:
```
Fant versjon: 3.8
```
