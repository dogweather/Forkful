---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:38.672760-07:00
description: "YAML, en f\xF6rkortning f\xF6r \"YAML Ain't Markup Language\", \xE4\
  r en m\xE4nniskov\xE4nlig standard f\xF6r dataseriering som kan anv\xE4ndas f\xF6\
  r alla programmeringsspr\xE5k.\u2026"
lastmod: '2024-03-13T22:44:37.975098-06:00'
model: gpt-4-0125-preview
summary: "YAML, en f\xF6rkortning f\xF6r \"YAML Ain't Markup Language\", \xE4r en\
  \ m\xE4nniskov\xE4nlig standard f\xF6r dataseriering som kan anv\xE4ndas f\xF6r\
  \ alla programmeringsspr\xE5k."
title: Att Arbeta med YAML
weight: 41
---

## Hur man gör:
Haskell har inte inbyggt stöd för bearbetning av YAML, men du kan använda tredjepartsbibliotek såsom `yaml` och `aeson` för att tolka och generera YAML-data. Så här kommer du igång:

### Läsa YAML
Först, lägg till paketet `yaml` i ditt projekts beroenden. Därefter kan du använda följande exempel för att tolka ett enkelt YAML-dokument:

```haskell
{-# LANGUAGE OverloadedStrings #-}

import Data.YAML
import Data.ByteString (ByteString)
import Control.Monad.IO.Class (liftIO)

-- Exempel på YAML-data
yamlData :: ByteString
yamlData = "
name: John Doe
age: 30
"

-- Definiera en datastruktur som matchar YAML-dokumentet
data Person = Person
  { name :: String
  , age :: Int
  } deriving (Show)

instance FromYAML Person where
  parseYAML = withMap "Person" $ \m -> Person
    <$> m .: "name"
    <*> m .: "age"

main :: IO ()
main = do
  let parsed = decode1 yamlData :: Either (Pos,String) Person
  case parsed of
    Left err -> putStrLn $ "Fel vid tolkning av YAML: " ++ show err
    Right person -> print person
```
Ett exempel på utskrift för ovanstående kod kan se ut som följer:
```
Person {name = "John Doe", age = 30}
```

### Skriva YAML
För att generera YAML från Haskell-datastrukturer kan du använda kodningsfunktionaliteterna som tillhandahålls av paketet `yaml` som visat nedan:

```haskell
{-# LANGUAGE OverloadedStrings #-}

import Data.YAML
import Data.ByteString.Lazy.Char8 (unpack)

-- Använder Person-datastrukturen från föregående exempel

person :: Person
person = Person "Jane Doe" 25

main :: IO ()
main = do
  let yamlData = encode1 person
  putStrLn $ unpack yamlData
```
Utskriften av detta program kommer att vara en YAML-formaterad sträng:
```
name: Jane Doe
age: 25
```

Dessa exempel bör fungera som en utgångspunkt för att arbeta med YAML i Haskell. Beroende på dina behov kan du vilja utforska mer avancerade funktioner och alternativ som dessa bibliotek erbjuder.
