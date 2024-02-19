---
aliases:
- /no/elm/capitalizing-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:55.309989-07:00
description: "\xC5 kapitalisere en streng inneb\xE6rer \xE5 omforme det f\xF8rste\
  \ tegnet i en gitt streng til stor bokstav mens resten holdes i sm\xE5 bokstaver,\
  \ ofte for\u2026"
lastmod: 2024-02-18 23:08:53.795141
model: gpt-4-0125-preview
summary: "\xC5 kapitalisere en streng inneb\xE6rer \xE5 omforme det f\xF8rste tegnet\
  \ i en gitt streng til stor bokstav mens resten holdes i sm\xE5 bokstaver, ofte\
  \ for\u2026"
title: Sette stor bokstav i en streng
---

{{< edit_this_page >}}

## Hva og hvorfor?

Å kapitalisere en streng innebærer å omforme det første tegnet i en gitt streng til stor bokstav mens resten holdes i små bokstaver, ofte for standardisert formatering eller lesbarhetsformål. Programmerere utfører ofte denne oppgaven for å sikre at data presenteres konsistent, spesielt i brukergrensesnitt eller ved bearbeiding og visning av brukerinndata.

## Hvordan:

I Elm finnes det ikke en innebygd funksjon spesifikt for å kapitalisere strenger. Du kan imidlertid enkelt oppnå dette ved å bruke innebygde `String` modulfunksjoner som `toUpper`, `toLower`, `left` og `dropLeft`.

```elm
capitalize : String -> String
capitalize str =
    if String.isEmpty str then
        ""
    else
        String.toUpper (String.left 1 str) ++ String.toLower (String.dropLeft 1 str)

-- Eksempel på bruk
main =
    String.toList "hello world" |> List.map capitalize |> String.join " "
    -- Utdata: "Hello World"
```

For mer komplekse scenarioer, eller hvis du foretrekker å bruke et bibliotek som gir en direkte måte å kapitalisere strenger på, kan du vurdere en tredjeparts pakke som `elm-community/string-extra`. Men, som per min siste oppdatering, oppmuntrer Elms økosystem til å håndtere slike oppgaver ved hjelp av innebygde funksjoner for å holde språket og prosjektene strømlinjeformet.

```elm
import String.Extra as StringExtra

-- I tilfelle det finnes en `capitalize` funksjon i et tredjeparts bibliotek
capitalizeWithLibrary : String -> String
capitalizeWithLibrary str =
    StringExtra.capitalize str

-- Eksempel på bruk med hypotetisk biblioteksfunksjon
main =
    "this is elm" |> capitalizeWithLibrary
    -- Hypotetisk utdata: "This is elm"
```

Sjekk alltid Elm-pakkebiblioteket for de siste og mest foretrukne bibliotekene for strengmanipulering hvis du ser etter ekstra funksjonalitet utover standardbiblioteket.
