---
aliases:
- /nl/haskell/using-a-debugger/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:09:35.008459-07:00
description: "Een debugger gebruiken betekent diep duiken in je code met hulpmiddelen\
  \ die zijn ontworpen om te inspecteren, te pauzeren en een programma tijdens de\u2026"
lastmod: 2024-02-18 23:09:01.903855
model: gpt-4-0125-preview
summary: "Een debugger gebruiken betekent diep duiken in je code met hulpmiddelen\
  \ die zijn ontworpen om te inspecteren, te pauzeren en een programma tijdens de\u2026"
title: Een debugger gebruiken
---

{{< edit_this_page >}}

## Wat & Waarom?
Een debugger gebruiken betekent diep duiken in je code met hulpmiddelen die zijn ontworpen om te inspecteren, te pauzeren en een programma tijdens de uitvoering te manipuleren. Programmeurs doen dit om fouten op te sporen, de programmastroom te begrijpen en ervoor te zorgen dat hun code precies doet wat ze verwachten.

## Hoe:
Laten we een wandeling maken met GHCi, Haskell's interactieve omgeving die kan dienen als een basale debugger. Je start het op met je Haskell-code en begint rond te neuzen. Hier is een voorbeeld:

```Haskell
main :: IO ()
main = do
    putStrLn "Hé, hoe heet je?"
    naam <- getLine
    putStrLn $ "Hallo, " ++ naam ++ "! Laten we debuggen."
    let resultaat = buggyFunctie 5
    print resultaat

buggyFunctie :: Int -> Int
buggyFunctie n = n * 2 -- Doe alsof hier een bug zit
```

Om te beginnen met debuggen met GHCi:

```bash
$ ghci YourHaskellFile.hs
```

Stel een breekpunt in bij `buggyFunctie`:

```Haskell
Prelude> :break buggyFunctie
```

Voer je programma uit:

```Haskell
Prelude> :main
Hé, hoe heet je?
```

Je programma pauzeert bij `buggyFunctie`. Nu kun je variabelen inspecteren, door de code stappen en expressies evalueren.

## Diepgaand:
Historisch gezien heeft Haskell's reputatie voor pure functies en sterke typebinding geleid tot het geloof dat debugging-tools minder cruciaal waren. De realiteit is anders—complexe programma's profiteren altijd van goede debugging-tools. GHCi biedt basale debugging-commando's. Echter, voor een meer visuele ervaring of toepassingen op grotere schaal, wil je misschien IDE's met geïntegreerde debuggers verkennen, zoals Visual Studio Code met Haskell-extensies of IntelliJ's Haskell-plugin.

Alternatieven voor de debugger omvatten het gebruik van print statements, bekend als "printf debugging", of het benutten van Haskell's sterke type systeem om incorrecte staten onrepresenteerbaar te maken. Toch vervangt soms niets het doorlopen van de code.

Wat implementatiedetails betreft, werkt Haskell's debugger met het runtime systeem. Het kan breakpoints aan, uitvoering stappen en variabele inspectie toestaan. Echter, aangezien Haskell lui geëvalueerd wordt, kunnen dingen een beetje niet-intuïtief worden. Het debuggen van een Haskell-programma betekent vaak opletten wanneer en hoe expressies worden geëvalueerd.

## Zie Ook:
- [GHC Gebruikersgids - Debugger](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html)
- [IntelliJ Haskell Plugin](https://plugins.jetbrains.com/plugin/8258-intellij-haskell)
