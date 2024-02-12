---
title:                "Att påbörja ett nytt projekt"
aliases:
- /sv/haskell/starting-a-new-project/
date:                  2024-01-20T18:03:36.765293-07:00
model:                 gpt-4-1106-preview
simple_title:         "Att påbörja ett nytt projekt"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/haskell/starting-a-new-project.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Att starta ett nytt projekt innebär att sätta upp en ny kodbas från grunden. Programmerare gör det för att skapa unika lösningar eller utforska nya idéer.

## Så här gör du:
För att skapa nytt Haskell-projekt rekommenderar vi att använda Stack, ett kraftfullt verktyg som hanterar projektets bygge och beroenden.

```Haskell
-- Installera Stack
$ curl -sSL https://get.haskellstack.org/ | sh

-- Skapa ett nytt projekt
$ stack new myproject

-- Bygga projektet, detta skapar en exekverbar fil
$ cd myproject
$ stack build

-- Kör projektet
$ stack exec myproject-exe
```

Output när projektet skapas:

```
Downloading template "new-template" to create project "myproject" in myproject/ ...
The project 'myproject' has been created and is located at /path/to/myproject
```

## Djupdykning
Stack är utvecklat med syftet att göra det smidigt att arbeta med Haskell-projekt. Det kom som ett alternativ till det äldre systemet Cabal, som fortfarande används men anses av många som mer komplicerat. Stack använder sig av Stackage, en stor samling av Haskell-paket som är testade tillsammans för att säkerställa kompatibilitet. Detta betyder mindre beroendeproblem för utvecklaren. 

Att starta ett projekt i Haskell var förr en mer manuell process. Alternativ inkluderar att direkt använda GHC (Glasgow Haskell Compiler), men detta kräver mer konfiguration. Med Stack kan du skapa projekt som bygger på olika förkonfigurerade mallar, vilket hjälper dig att komma igång snabbt och med god ordning från början.

## Se även
- [Haskell Stack Documentation](https://docs.haskellstack.org/en/stable/README/)
- [Stackage Server](https://www.stackage.org/)
