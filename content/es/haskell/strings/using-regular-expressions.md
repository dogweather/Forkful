---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:53.851895-07:00
description: "Las expresiones regulares en programaci\xF3n son secuencias de caracteres\
  \ que definen un patr\xF3n de b\xFAsqueda, t\xEDpicamente empleadas para la b\xFA\
  squeda y\u2026"
lastmod: '2024-03-13T22:44:59.109414-06:00'
model: gpt-4-0125-preview
summary: "Las expresiones regulares en programaci\xF3n son secuencias de caracteres\
  \ que definen un patr\xF3n de b\xFAsqueda, t\xEDpicamente empleadas para la b\xFA\
  squeda y manipulaci\xF3n de cadenas de texto."
title: Usando expresiones regulares
weight: 11
---

## Cómo hacerlo:
En Haskell, las funcionalidades de expresiones regulares no son parte de la biblioteca estándar, por lo que es necesario utilizar paquetes de terceros como `regex-base` junto con un backend compatible como `regex-posix` (para soporte de regex POSIX), `regex-pcre` (para regex compatible con Perl), etc. Así es como puedes usar estos paquetes para trabajar con expresiones regulares.

Primero, asegúrate de tener los paquetes instalados añadiéndolos `regex-posix` o `regex-pcre` al archivo `.cabal` de tu proyecto o instalándolos directamente mediante cabal:

```bash
cabal install regex-posix
```
o
```bash
cabal install regex-pcre
```

### Usando `regex-posix`:
```haskell
import Text.Regex.Posix ((=~))

-- Comprobar si una cadena coincide con un patrón
isMatch :: String -> String -> Bool
isMatch texto patron = texto =~ patron :: Bool

-- Encontrar la primera coincidencia
findFirst :: String -> String -> String
findFirst texto patron = texto =~ patron :: String

main :: IO ()
main = do
    print $ isMatch "hola mundo" "mu"
    -- Salida: True
    print $ findFirst "buenos días, buenas noches" "buen"
    -- Salida: "buen"
```

### Usando `regex-pcre`:
```haskell
import Text.Regex.PCRE ((=~))

-- Encontrar todas las coincidencias
findAll :: String -> String -> [String]
findAll texto patron = texto =~ patron :: [String]

main :: IO ()
main = do
    print $ findAll "prueba1 prueba2 prueba3" "\\bprueba[0-9]\\b"
    -- Salida: ["prueba1","prueba2","prueba3"]
```

Cada biblioteca tiene sus particularidades, pero la metodología general de usar `=~` para aplicar la regex se mantiene consistente, ya sea para comprobar una coincidencia o para extraer subcadenas. La elección entre `regex-posix` o `regex-pcre` depende en gran medida de las necesidades de tu proyecto y las capacidades específicas de regex requeridas.
