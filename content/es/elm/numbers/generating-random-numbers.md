---
changelog:
- 2024-02-27, dogweather, edited and tested
- 2024-02-27, gpt-4-0125-preview, translated from English
date: 2024-02-27 22:50:20.728417-07:00
description: "Generar n\xFAmeros aleatorios en Elm implica usar el m\xF3dulo `Random`\
  \ para producir n\xFAmeros pseudo-aleatorios, los cuales son \xFAtiles para una\
  \ variedad de\u2026"
lastmod: '2024-03-13T22:44:58.975260-06:00'
model: gpt-4-0125-preview
summary: "Generar n\xFAmeros aleatorios en Elm implica usar el m\xF3dulo `Random`\
  \ para producir n\xFAmeros pseudo-aleatorios, los cuales son \xFAtiles para una\
  \ variedad de tareas como juegos, simulaciones, e incluso como parte de algoritmos\
  \ que requieren procesos estoc\xE1sticos."
title: "Generando n\xFAmeros aleatorios"
weight: 12
---

## Cómo hacerlo:
La naturaleza puramente funcional de Elm significa que no puedes generar números aleatorios directamente como podrías hacerlo en lenguajes imperativos. En su lugar, usas el módulo `Random` en conjunción con comandos. Aquí tienes un ejemplo básico que genera un entero aleatorio entre 1 y 100.

Primero, instala el módulo `Random` con `elm install elm/random`. Luego impórtalo en tu archivo Elm, junto con los módulos de HTML y eventos necesarios, así:

`src/Main.elm`

```elm
module Main exposing (..)

import Browser
import Html exposing (Html, button, text, div)
import Html.Events exposing (onClick)
import Random
```

Para que este sea un ejemplo autocontenido, puedes agregar este código base:
```elm
main =
  Browser.element { init = init, update = update, subscriptions = subscriptions, view = view }

init : () -> (Model, Cmd Msg)
init _ =
  (Model 0, Cmd.none)

subscriptions : Model -> Sub Msg
subscriptions _ =
  Sub.none
```

A continuación, define un **comando** para generar un número aleatorio. Esto implica configurar un tipo `Msg` para manejar el número aleatorio una vez generado, un `Model` para almacenarlo, y una función de actualización para unirlo todo.
```elm
type Msg
    = Generate
    | NewRandom Int

type alias Model = { randomNumber : Int }

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        Generate ->
            ( model, Random.generate NewRandom (Random.int 1 100) )

        NewRandom number ->
            ( { model | randomNumber = number }, Cmd.none )
```

Para disparar la generación de un número, podrías enviar un mensaje `Generate`, por ejemplo, a través de un botón en tu vista:
```elm
view : Model -> Html Msg
view model =
    div []
        [ div [] [ text ("Número Aleatorio: " ++ String.fromInt(model.randomNumber)) ]
        , button [ onClick Generate ] [ text "Generar" ]
        ]
```

Cuando hagas clic en el botón "Generar", se mostrará un número aleatorio entre 1 y 100.

Este enfoque simplista puede ser adaptado y ampliado, aprovechando otras funciones en el módulo `Random` para producir flotantes aleatorios, listas, o incluso estructuras de datos complejas basadas en tipos personalizados, proporcionando un vasto terreno de juego para agregar imprevisibilidad a tus aplicaciones en Elm.

La Guía de Elm profundiza mucho más en este tema. También tiene [un ejemplo de lanzamiento de un dado de seis caras](https://guide.elm-lang.org/effects/random).
