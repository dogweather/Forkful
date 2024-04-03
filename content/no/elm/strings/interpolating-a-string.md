---
date: 2024-01-20 17:50:40.548706-07:00
description: "Strenginterpolasjon betyr \xE5 smelte sammen variabler med tekst. Vi\
  \ gj\xF8r det for \xE5 bygge brukertilpassede meldinger eller for \xE5 kombinere\
  \ data dynamisk."
lastmod: '2024-03-13T22:44:40.694435-06:00'
model: gpt-4-1106-preview
summary: "Strenginterpolasjon betyr \xE5 smelte sammen variabler med tekst."
title: Interpolering av en streng
weight: 8
---

## How to:
Elm bruker `++` operatoren for å sette sammen strenger. Det er ingen innebygget strenginterpolasjon, men vi kan lage klar og lesbar kode likevel:

```Elm
name = "Ola"
greeting = "Hei, " ++ name ++ "!"

-- Output: "Hei, Ola!"
```

Du kan også sette sammen tall og strenger etter å ha konvertert tallet:

```Elm
age = 30
ageMessage = "Jeg er " ++ String.fromInt(age) ++ " år gammel."

-- Output: "Jeg er 30 år gammel."
```

## Deep Dive
Elm har aldri hatt innebygget strenginterpolasjon som i andre språk (JavaScript's template literals for eksempel). Dette holder språket enkelt og konsistent. Du klarer deg godt med `++` for å sette sammen strenger.

Alternativer inkluderer skreddersydde interpolasjonsfunksjoner. Noen biblioteker gir også ekstra funksjonalitet, men for de fleste Elm-utviklere, `++` gjør jobben.

Interessant, tidligere versjoner av språk som JavaScript hadde ikke heller strenginterpolasjon. Utviklere brukte pluss-operatoren, lik Elm i dag.

## See Also
- Elm dokumentasjon om strenger: https://package.elm-lang.org/packages/elm/core/latest/String
- Elm community diskusjoner: https://discourse.elm-lang.org/
- En hjelpsom Elm pakke for mer kompleks strengmanipulasjon: https://package.elm-lang.org/packages/elm-community/string-extra/latest/
