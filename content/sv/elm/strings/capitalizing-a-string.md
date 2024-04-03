---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:19.617947-07:00
description: "Att versalisera en str\xE4ng inneb\xE4r att omvandla det inledande tecknet\
  \ i en given str\xE4ng till versal medan resten beh\xE5lls i gemener, ofta f\xF6\
  r standardiserad\u2026"
lastmod: '2024-03-13T22:44:37.812588-06:00'
model: gpt-4-0125-preview
summary: "Att versalisera en str\xE4ng inneb\xE4r att omvandla det inledande tecknet\
  \ i en given str\xE4ng till versal medan resten beh\xE5lls i gemener, ofta f\xF6\
  r standardiserad formatering eller l\xE4sbarhet."
title: "G\xF6r om en str\xE4ng till versaler"
weight: 2
---

## Hur gör man:
I Elm finns ingen inbyggd funktion specifikt för att versalisera strängar. Dock kan du enkelt uppnå detta genom att använda de inbyggda funktionerna i `String`-modulen som `toUpper`, `toLower`, `left` och `dropLeft`.

```elm
capitalize : String -> String
capitalize str =
    if String.isEmpty str then
        ""
    else
        String.toUpper (String.left 1 str) ++ String.toLower (String.dropLeft 1 str)

-- Exempelanvändning
main =
    String.toList "hello world" |> List.map capitalize |> String.join " "
    -- Output: "Hello World"
```

För mer komplexa scenarier eller om du föredrar att använda ett bibliotek som erbjuder ett direkt sätt att versalisera strängar, kan du överväga ett tredjepartspaket som `elm-community/string-extra`. Dock uppmuntrar Elm:s ekosystem, enligt min senaste uppdatering, hantering av sådana uppgifter med inbyggda funktioner för att hålla språket och projekten "lean".

```elm
import String.Extra as StringExtra

-- Om det finns en `capitalize` funktion i ett tredjepartsbibliotek
capitalizeWithLibrary : String -> String
capitalizeWithLibrary str =
    StringExtra.capitalize str

-- Exempelanvändning med hypotetisk biblioteksfunktion
main =
    "this is elm" |> capitalizeWithLibrary
    -- Hypotetisk output: "This is elm"
```

Kontrollera alltid Elm-paketdatabasen för de senaste och mest föredragna biblioteken för strängmanipulering om du letar efter ytterligare funktionalitet bortom standardbiblioteket.
