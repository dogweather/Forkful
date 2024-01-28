---
title:                "Koodin järjestäminen funktioihin"
date:                  2024-01-26T01:11:40.929688-07:00
model:                 gpt-4-1106-preview
simple_title:         "Koodin järjestäminen funktioihin"
programming_language: "Python"
category:             "Python"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/python/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Koodin järjestäminen funktioihin tarkoittaa koodin jakamista uudelleenkäytettäviin kokonaisuuksiin tiettyä tarkoitusta varten. Teemme näin, jotta koodista tulisi siistimpää, helpompaa lukea, debugata ja päivittää.

## Kuinka:
Kuvitellaan, että kirjoitat skriptiä laskemaan luvun neliön ja kuution. Ilman funktioita se on toiston sekasotku:

```Python
num = 4
square = num * num
cube = num * num * num
print(f"Neliö: {square}, Kuutio: {cube}")

num = 5
square = num * num
cube = num * num * num
print(f"Neliö: {square}, Kuutio: {cube}")
```
Tulostus:
```
Neliö: 16, Kuutio: 64
Neliö: 25, Kuutio: 125
```

Funktioiden kanssa se on siistimpää:

```Python
def square(n):
    return n * n

def cube(n):
    return n ** 3

num = 4
print(f"Neliö: {square(num)}, Kuutio: {cube(num)}")

num = 5
print(f"Neliö: {square(num)}, Kuutio: {cube(num)}")
```
Tulostus:
```
Neliö: 16, Kuutio: 64
Neliö: 25, Kuutio: 125
```

## Syvemmälle
Aikoinaan, kun ohjelmat olivat yksinkertaisia, saatoit selvitä kirjoittamalla vain listan ohjeita. Mutta kun ohjelmistot monimutkaistuivat, kehittäjät huomasivat kirjoittavansa samaa koodia yhä uudelleen ja uudelleen. Hei, funktiot—uudelleenkäytettäviä koodilohkoja, jotka suorittavat yksittäisen toiminnon.

Vaihtoehtoja funktioille ovat luokat (jotka yhdistävät funktiot niihin käyttämiinsä tietoihin) ja sisäinen koodi (älykkyys juuri siellä, missä sitä tarvitaan, mutta riskialtis kompleksisissa tehtävissä). Toteutuksen kannalta temppu ei ole vain luoda funktioita, vaan tehdä niistä yksi asia hyvin—ajattele yksivastuuperiaatetta. Funktioiden tulisi myös ihanteellisesti olla tilattomia, mikä tarkoittaa, että ei ole yllätyksiä tulevien tai menevien tietojen kanssa.

## Katso myös
- Viralliset Python-oppaat funktioista: https://docs.python.org/3/tutorial/controlflow.html#defining-functions
- 'Clean Code' kirjoittanut Robert C. Martin, periaatteista, kuinka kirjoittaa siistiä koodia funktioille.
- 'Refactoring: Improving the Design of Existing Code' kirjoittanut Martin Fowler, joka sisältää esimerkkejä koodin järjestämisestä.
