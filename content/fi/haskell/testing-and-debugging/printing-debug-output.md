---
date: 2024-01-20 17:52:44.270186-07:00
description: "Mik\xE4 & Miksi? Ohjelmoinnissa debug-tulostus tarkoittaa tilap\xE4\
  isten viestien tulostamista koodin suorituksen seuraamiseksi. K\xE4yt\xE4mme t\xE4\
  t\xE4 selvitt\xE4\xE4ksemme\u2026"
lastmod: '2024-03-13T22:44:56.617685-06:00'
model: gpt-4-1106-preview
summary: "Mik\xE4 & Miksi."
title: "Virheenj\xE4ljitystulosteiden tulostaminen"
weight: 33
---

## How to:
Miten:
```Haskell
main :: IO ()
main = do
  putStrLn "Aloitetaan debuggaus"
  printDebugInfo "Tässä on muuttujan arvo" 42
  putStrLn "Debuggaus päättyy"

printDebugInfo :: Show a => String -> a -> IO ()
printDebugInfo msg value = putStrLn $ msg ++ ": " ++ show value
```

Esimerkin tulostus:
```
Aloitetaan debuggaus
Tässä on muuttujan arvo: 42
Debuggaus päättyy
```

## Deep Dive
Syväsukellus
Haskellissa `print` on kätevä funktio virheenetsintätietojen tulostamiseen. Se on lyhenne `putStrLn . show`:lle ja tulostaa `Show`-tyypin luokkaan kuuluvan arvon. Historiallisesti ohjelmoijat ovat tulostaneet tietoa konsoliin ymmärtääkseen mitä ohjelmassaan tapahtuu. Vaihtoehtoisia työkaluja debuggaukseen ovat muun muassa lokeja kirjaavat kirjastot tai interaktiivinen debuggaus GHCi:n kautta. Implementaation yksityiskohtia miettiessä käytettävyys ja suorituskyky ovat tärkeitä seikkoja; debug-viestien tulisi olla informatiivisia mutta eivät hidastaa ohjelmaa liikaa.

## See Also
Katso Myös
- [Haskell Debugging](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html) - virallinen GHC:n käyttöopas debuggaukseen.
- [Hoogle](https://hoogle.haskell.org/) - voit hakea Haskell-funktioita ja kirjastoja.
- [Haskell Wiki on Debugging](https://wiki.haskell.org/Debugging) - lisätietoja erilaisista debuggaustyökaluista Haskeleille.
