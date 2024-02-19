---
aliases:
- /fi/fish-shell/using-an-interactive-shell-repl/
date: 2024-01-26 04:14:19.111952-07:00
description: "REPL eli Read-Eval-Print Loop on interaktiivinen ohjelmointiymp\xE4\
  rist\xF6, joka ottaa vastaan yksitt\xE4isi\xE4 k\xE4ytt\xE4j\xE4n sy\xF6tteit\xE4\
  , suorittaa ne ja palauttaa\u2026"
lastmod: 2024-02-18 23:09:08.085918
model: gpt-4-0125-preview
summary: "REPL eli Read-Eval-Print Loop on interaktiivinen ohjelmointiymp\xE4rist\xF6\
  , joka ottaa vastaan yksitt\xE4isi\xE4 k\xE4ytt\xE4j\xE4n sy\xF6tteit\xE4, suorittaa\
  \ ne ja palauttaa\u2026"
title: "Interaktiivisen komentotulkin (REPL) k\xE4ytt\xF6"
---

{{< edit_this_page >}}

## Mikä ja Miksi?
REPL eli Read-Eval-Print Loop on interaktiivinen ohjelmointiympäristö, joka ottaa vastaan yksittäisiä käyttäjän syötteitä, suorittaa ne ja palauttaa tuloksen. Ohjelmoijat käyttävät sitä saadakseen välitöntä palautetta, debuggaamiseen ja nopeatahtiseen kokeiluun koodauskonseptien kanssa ilman, että tarvitsee kääntää ja ajaa koko ohjelmaa.

## Kuinka:
Fishissä interaktiivinen kuori on oletustila, kun käynnistät sen. Tältä se näyttää toiminnassa:

```Fish Shell
> set color blue
> echo "Taivas on $color"
Taivas on sininen
```

Voit myös ajaa sisäänrakennettuja funktioita ja leikkiä komentosubstituutioiden kanssa:

```Fish Shell
> function cheer
      echo "Go Fish $argv!"
  end
> cheer Koodaajat
Go Fish Koodaajat!
```

Ei vain funktioiden määrittelyä, voit suorittaa koodinpätkiä lennosta ja nähdä tuloksen välittömästi:

```Fish Shell
> math "40 / 2"
20
```

## Syväsukellus
REPLien konsepti juontaa juurensa aina 1960-luvun Lisp-ohjelmointikieleen. Tämä vuorovaikutteisen ohjelmoinnin muoto loi mittapuun ympäristöille kuten Pythonin `ipython` ja Rubyn `irb`. Fish jatkaa trendiä keskittyen käyttäjäystävällisyyteen ja vuorovaikutteiseen käyttöön.

Fish eroaa muista kuorista, kuten Bashista, siinä, että se on suunniteltu interaktiivisuutta silmällä pitäen alusta alkaen. Se tarjoaa syntaksikorostuksen, automaattiset ehdotukset ja välilehdellä täydennykset, jotka tekevät sen käytöstä tehokasta REPL-tyylisessä työnkulussa. Parempi vielä, komentosi muistetaan ja ovat haettavissa, mikä tekee toistuvasta testauksesta tuulen nopeaa.

Fishin REPLin vaihtoehtoja voisivat olla `bash` tai `zsh`, kun ne yhdistetään laajennuksiin kuten `bash-completion` tai `oh-my-zsh`, mutta Fish tarjoaa yleensä rikkaamman kokemuksen suoraan laatikosta.

## Katso Myös:
- Fish Documentation: https://fishshell.com/docs/current/index.html
- Mielenkiintoinen vertailu Fishin ja muiden kuorien välillä: https://www.slant.co/versus/2209/3686/~fish_vs_bash
- Syväsukellus REPL:eihin: https://en.wikipedia.org/wiki/Read–eval–print_loop
- Vuorovaikutteinen ohjelmointi Lispissä, historiallinen katsaus: http://www.paulgraham.com/ilisp.html
