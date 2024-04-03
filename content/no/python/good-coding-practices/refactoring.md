---
date: 2024-01-26 03:37:02.562291-07:00
description: "Refaktorering er prosessen med \xE5 restrukturere eksisterende dataprogramkode\u2014\
  endre faktoriseringen\u2014uten \xE5 endre dens eksterne oppf\xF8rsel. Programmerere\
  \ gj\xF8r\u2026"
lastmod: '2024-03-13T22:44:40.369738-06:00'
model: gpt-4-0125-preview
summary: "Refaktorering er prosessen med \xE5 restrukturere eksisterende dataprogramkode\u2014\
  endre faktoriseringen\u2014uten \xE5 endre dens eksterne oppf\xF8rsel."
title: Refaktorering
weight: 19
---

## Hvordan:
Anta at du har en bit kode som beregner og skriver ut arealet og omkretsen av et rektangel gitt lengden og bredden. Det gjør jobben, men det er repeterende og litt rotete.

```python
# Original versjon
lengde = 4
bredde = 3

# Beregn areal og omkrets
areal = lengde * bredde
omkrets = 2 * (lengde + bredde)

print("Areal:", areal)
print("Omkrets:", omkrets)
```

Vi kan refaktorere dette ved å kapsle inn funksjonaliteten i funksjoner, noe som gjør koden mer organisert og gjenbrukbar:

```python
# Refaktorert versjon

def beregn_areal(lengde, bredde):
    return lengde * bredde

def beregn_omkrets(lengde, bredde):
    return 2 * (lengde + bredde)

# bruk
lengde = 4
bredde = 3

print("Areal:", beregn_areal(lengde, bredde))
print("Omkrets:", beregn_omkrets(lengde, bredde))
```

Begge kodestykkene gir samme resultat:
```
Areal: 12
Omkrets: 14
```

Men den refaktorerte versjonen er renere og skiller bekymringer, noe som gjør det lettere å oppdatere en beregning uten å påvirke den andre.

## Dypdykk
Refaktorering har sine røtter i de tidlige dagene av programvareutvikling når programmerere innså at kode kunne—og bør—forbedres selv om den allerede "fungerer". Martin Fowlers banebrytende bok "Refaktorering: Forbedring av design av eksisterende kode" artikulerte mange grunnleggende prinsipper og teknikker. Han sa berømt, "Enhver idiot kan skrive kode som en datamaskin kan forstå. Gode programmerere skriver kode som mennesker kan forstå."

Alternativer til refaktorering kan inkludere å skrive kode på nytt fra bunnen av eller å gjøre mindre justeringer uten systematisk forbedring. Imidlertid er refaktorering vanligvis mer kostnadseffektivt enn en omskriving og mindre risikabelt enn ad-hoc-modifikasjoner. Implementeringsdetaljer kan være spesifikke for hvert programmeringsparadigme; imidlertid er objektorientert programmering spesielt godt egnet for refaktorering, spesielt med teknikker som ekstrahering av metoder (som våre `beregn_areal` og `beregn_omkrets` funksjoner), innlining, flytting av funksjoner mellom objekter, og omdøping av metoder eller variabler for klarhet.

Refaktorering i Python bruker ofte verktøy som `PyCharm`, som har innebygde refaktoreringsegenskaper, eller `rope`, et Python-bibliotek spesielt designet for refaktorering. Forsiktig bruk av versjonskontroll, som `git`, under refaktorering anbefales sterkt for å holde oversikt over endringer inkrementelt.

## Se også
For de som er sultne på mer, dykk inn i følgende ressurser:
- Martin Fowlers bok: [Refaktorering: Forbedring av design av eksisterende kode](http://www.refactoring.com/)
- Python refaktorering med `rope`: [GitHub - rope](https://github.com/python-rope/rope)
- PyCharm refaktorering dokumentasjon: [Jetbrains PyCharm Refaktorering av kildekode](https://www.jetbrains.com/help/pycharm/refactoring-source-code.html)
- Refactoring.guru: [Refaktorering og designmønstre](https://refactoring.guru/refactoring)
- Clean Code forelesninger av Uncle Bob (Robert C. Martin): [Clean Code - Uncle Bob / Leksjon 1](https://www.youtube.com/watch?v=7EmboKQH8lM)
