---
title:                "Rozpoczynanie nowego projektu"
date:                  2024-01-20T18:04:35.245193-07:00
model:                 gpt-4-1106-preview
simple_title:         "Rozpoczynanie nowego projektu"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/haskell/starting-a-new-project.md"
---

{{< edit_this_page >}}

## What & Why? (Co i dlaczego?)
Zaczynanie nowego projektu w Haskellu to stworzenie struktury i plików startowych. Programiści robią to, by nakreślić fundamenty aplikacji i zorganizować kod od samego początku.

## How to: (Jak to zrobić:)
```Haskell
-- Instalacja programu Stack, który zarządza projektami w Haskellu:
-- Unix: `curl -sSL https://get.haskellstack.org/ | sh`
-- Windows: `wget -qO- https://get.haskellstack.org/ | sh`

-- Tworzenie nowego projektu Stack:
stack new mój_projekt

-- Struktura plików projektu:
-- mój_projekt/
--   ├── app/
--   ├── src/
--   ├── test/
--   ├── LICENSE
--   ├── Setup.hs
--   ├── mój_projekt.cabal
--   ├── stack.yaml
--   └── stack.yaml.lock

-- Uruchomienie projektu (navigacja do katalogu `mój_projekt`):
cd mój_projekt
stack setup
stack build
stack exec mój_projekt-exe

-- Przykładowe dane wyjściowe:
-- mój_projekt-exe: Hello, Haskell!
```

## Deep Dive (Dogłębna analiza):
Haskell, jako język funkcyjny, posiada wieloletnią historię z różnymi systemami zarządzania projektami, gdzie główną rolę pełni obecnie Stack. Stack został wprowadzony w 2014 roku w odpowiedzi na problemy z reprodykowalnością środowisk i zależności w innym popularnym narzędziu, czyli Cabal.

Alternatywą dla Stack jest wspomniane Cabal, które nadal jest używane i rozwijane. Stack i Cabal różnią się podejściem do zarządzania zależnościami oraz budowania projektów.

Stack zapewnia izolację środowiska, proste zarządzanie wieloma wersjami kompilatora GHC (Glasgow Haskell Compiler) i gładką integrację z systemem Stackage, co ułatwia pracę z zestawem pakietów znanych z dobrej kompatybilności.

Rozpoczynając nowy projekt, warto zwrócić uwagę na plik `.cabal`, który definiuje metadane projektu, zależności oraz sposób budowania aplikacji. Plik `stack.yaml` określa konfigurację dla Stack, w tym wybraną wersję customizowaną GHC i zestaw pakietów.

## See Also (Zobacz również):
- Oficjalna dokumentacja Stack: [docs.haskellstack.org](https://docs.haskellstack.org/en/stable/README/)
- Haskell Tool Stack - wprowadzenie: [www.youtube.com](https://www.youtube.com/watch?v=sRonIB8ZStw)
- Jak zacząć pracę z Cabal: [www.haskell.org/cabal/users-guide/](https://www.haskell.org/cabal/users-guide/)
