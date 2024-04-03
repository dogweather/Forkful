---
date: 2024-01-26 04:14:57.385625-07:00
description: "Interaktiivinen kuori eli REPL (Read-Eval-Print Loop) Haskellissa antaa\
  \ sinun suorittaa koodinp\xE4tki\xE4 reaaliajassa. Se on leikkikentt\xE4 nopeaa\
  \ palautetta,\u2026"
lastmod: '2024-03-13T22:44:56.616794-06:00'
model: gpt-4-0125-preview
summary: "Interaktiivinen kuori eli REPL (Read-Eval-Print Loop) Haskellissa antaa\
  \ sinun suorittaa koodinp\xE4tki\xE4 reaaliajassa."
title: "Interaktiivisen komentotulkin (REPL) k\xE4ytt\xF6"
weight: 34
---

## Kuinka:
Aloittaaksesi GHCi:n (Glasgow Haskell Compilerin interaktiivisen ympäristön), kirjoita yksinkertaisesti `ghci` terminaaliisi. Näin sitä käytetään:

```Haskell
Prelude> let x = 5
Prelude> x * 2
10
Prelude> :t x
x :: Num a => a
```

Esimerkkitulostus selittää, että `x` on numeerinen muuttuja ja osoittaa, että sen kaksinkertaistaminen tuottaa 10.

## Syväsukellus:
Haskellin GHCi on tullut pitkän matkan alkuajoistaan. Se tarjoaa rikkaan joukon ominaisuuksia, kuten välilehden täyttö, monirivinen syöte ja pakettien lataaminen. Vaihtoehdot, kuten Hugs, ovat pääosin historiaa nyt, GHCi:n ollessa standardi. GHCi kääntää koodin reaaliajassa joka kerta, kun syötät lausekkeen, tarjoten sinulle tehokkaan tavan testata Haskell-koodiasi.

## Katso myös:
- [The GHC User's Guide – GHCi](https://downloads.haskell.org/ghc/latest/docs/html/users_guide/ghci.html) (GHC:n käyttäjän opas – GHCi)
- [Learn You a Haskell for Great Good! – Starting Out](http://learnyouahaskell.com/starting-out#hello-world) (Opi Haskellia Mainiosti! – Alkuun)
- [Haskell Wiki – GHC/GHCi](https://wiki.haskell.org/GHC/GHCi)
