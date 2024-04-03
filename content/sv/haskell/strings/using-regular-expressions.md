---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:57.965311-07:00
description: "Regulj\xE4ra uttryck i programmering \xE4r sekvenser av tecken som definierar\
  \ ett s\xF6km\xF6nster, typiskt anv\xE4nda f\xF6r att s\xF6ka och manipulera str\xE4\
  ngar. Haskell-\u2026"
lastmod: '2024-03-13T22:44:37.945451-06:00'
model: gpt-4-0125-preview
summary: "Regulj\xE4ra uttryck i programmering \xE4r sekvenser av tecken som definierar\
  \ ett s\xF6km\xF6nster, typiskt anv\xE4nda f\xF6r att s\xF6ka och manipulera str\xE4\
  ngar."
title: "Att anv\xE4nda regulj\xE4ra uttryck"
weight: 11
---

## Hur:
I Haskell är regex-funktionalitet inte en del av standardbiblioteket, vilket kräver användning av tredjeparts paket såsom `regex-base` tillsammans med ett kompatibelt backend som `regex-posix` (för POSIX regex-stöd), `regex-pcre` (för Perl-kompatibelt regex), osv. Så här kan du använda dessa paket för att arbeta med reguljära uttryck.

Först, se till att du har paketen installerade genom att lägga till `regex-posix` eller `regex-pcre` i ditt projekts `.cabal`-fil eller installera via cabal direkt:

```bash
cabal install regex-posix
```
eller
```bash
cabal install regex-pcre
```

### Använda `regex-posix`:
```haskell
import Text.Regex.Posix ((=~))

-- Kontrollera om en sträng matchar ett mönster
isMatch :: String -> String -> Bool
isMatch text mönster = text =~ mönster :: Bool

-- Hitta första matchen
findFirst :: String -> String -> String
findFirst text mönster = text =~ mönster :: String

main :: IO ()
main = do
    print $ isMatch "hello world" "wo"
    -- Utdata: True
    print $ findFirst "good morning, good night" "good"
    -- Utdata: "good"
```

### Använda `regex-pcre`:
```haskell
import Text.Regex.PCRE ((=~))

-- Hitta alla matchningar
findAll :: String -> String -> [String]
findAll text mönster = text =~ mönster :: [String]

main :: IO ()
main = do
    print $ findAll "test1 test2 test3" "\\btest[0-9]\\b"
    -- Utdata: ["test1","test2","test3"]
```

Varje bibliotek har sina särdrag, men den allmänna metoden att använda `=~` för att applicera regex förblir konsekvent, oavsett om det handlar om att kontrollera för en matchning eller extrahera delsträngar. Valet mellan `regex-posix` och `regex-pcre` beror i stor utsträckning på ditt projekts behov och de specifika regex-funktioner som krävs.
