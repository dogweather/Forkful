---
aliases:
- /fi/python/handling-errors/
date: 2024-01-26 00:56:22.955289-07:00
description: "Virheenk\xE4sittely Pythonissa (tai miss\xE4 tahansa ohjelmointikieless\xE4\
  ) on odottamatonta odottamista \u2013 se on taitoa hallita tilanteita sulavasti,\
  \ kun asiat\u2026"
lastmod: 2024-02-18 23:09:07.191599
model: gpt-4-1106-preview
summary: "Virheenk\xE4sittely Pythonissa (tai miss\xE4 tahansa ohjelmointikieless\xE4\
  ) on odottamatonta odottamista \u2013 se on taitoa hallita tilanteita sulavasti,\
  \ kun asiat\u2026"
title: "Virheiden k\xE4sittely"
---

{{< edit_this_page >}}

## Mikä & Miksi?

Virheenkäsittely Pythonissa (tai missä tahansa ohjelmointikielessä) on odottamatonta odottamista – se on taitoa hallita tilanteita sulavasti, kun asiat menevät pieleen koodissasi. Teemme sitä estääksemme kaatumiset, opastaaksemme käyttäjiä ja tehdäksemme ohjelmistamme kestäviä ja luotettavia.

## Kuinka toimia:

``` Python
# Perus try-except -lohko
try:
    # riskialtis koodi
    luku = int(input("Anna numero: "))
except ValueError:
    # käsittele virhe
    print("Ei ole numero!")

# Määritetään useita poikkeuksia
try:
    # koodi, joka voi aiheuttaa erilaisia poikkeuksia
    tulos = 10 / int(input("Anna jakaja: "))
except ZeroDivisionError:
    print("Hups! Nollalla ei voi jakaa.")
except ValueError:
    print("Tarvitsen numeron, kaveri.")

# Käyttäen else- ja finally-lauseita
try:
    luku = int(input("Anna numero neliöitäväksi: "))
except ValueError:
    print("Sanoin numero!")
else:
    # ei virheitä tapahtunut
    print("Numerosi neliönä on:", luku**2)
finally:
    # suoritetaan aina
    print("Kiitos kun kokeilit tätä!")
```

Esimerkkitulostus, kun annetaan virheellinen numero ensimmäisessä lohkossa:
```
Anna numero: hei
Ei ole numero!
```

## Syväsukellus

Ohjelmoinnin sarastuksesta lähtien virheenkäsittely on ollut keskeistä. Aikaisemmat lähestymistavat olivat alkeellisia, kuten ehtojen tarkistaminen ennen jokaista riskialtista toimintoa. Pythonin `try-except` -syntaksi on peräisin vanhempien kielten, kuten C++ ja Java, poikkeuksien käsittelyn perinnöstä, yksinkertaistaen prosessia.

Kun yrität (`try`) suorittaa koodilohkoa, Python seuraa kaikkia poikkeuksia. Jos virhe ilmenee, `except` -lohko ottaa sen kiinni. Voit olla tarkka siitä, mitä poikkeuksia pyydystät tai pyydystää kaikki paljaalla `except`:lla. Kuitenkin, tarkka ensin -lähestymistapa on parempi – se on tarkka, ei "kaikki käy" -verkko.

`else` ja `finally` ovat lisäominaisuuksia tässä käsitteessä. `else` -lohko ajetaan, jos try-lohkossa ei ole virheitä. `finally` on luotettava kaveri, joka suoritetaan joka tapauksessa – ajattele puhdistustoimintoja.

Vaihtoehtoja? Niitä toki on. Jotkut kielet käyttävät paluukoodeja poikkeusten sijaan. Saatat myös kohdata `with`-lauseita resurssien käsittelyyn tai `assertioita`, jotka tarkistavat ehtoja kehityksen aikana. Mutta kun puhumme vankasta virheenkäsittelystrategiasta, try-catch -malli erottuu luettavuutensa ja rakenteensa ansiosta.

## Katso myös

Tässä on joitakin hyviä lisäresursseja syvällisempään perehtymiseen:

- Pythonin virallinen dokumentaatio virheistä ja poikkeuksista: [Python Docs – Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)
- Real Pythonin opas aiheeseen: [Real Python - The try/except/else/finally block](https://realpython.com/python-exceptions/)
- Huolellinen keskustelu parhaista virheenkäsittelykäytännöistä: [Stack Overflow – How do I properly ignore exceptions?](https://stackoverflow.com/questions/4990718/about-catching-any-exception)
