---
title:                "Escribiendo pruebas"
aliases:
- /es/elm/writing-tests/
date:                  2024-02-03T19:30:26.385044-07:00
model:                 gpt-4-0125-preview
simple_title:         "Escribiendo pruebas"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/elm/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué & Por qué?

Escribir pruebas en Elm implica crear casos de prueba para verificar la corrección de tu código Elm, asegurando que se comporte como se espera. Los programadores lo hacen para detectar errores temprano, facilitar el mantenimiento y mejorar la calidad y la fiabilidad de sus aplicaciones.

## Cómo hacerlo:

Elm utiliza el paquete `elm-explorations/test` para escribir pruebas unitarias y pruebas de fuzz. Comienza añadiendo el paquete a tu proyecto:

```elm
elm install elm-explorations/test
```

Crea un archivo de prueba, digamos `tests/ExampleTest.elm`, e importa los módulos de prueba. Aquí hay una prueba simple que verifica una función `add : Int -> Int -> Int`:

```elm
module ExampleTest exposing (..)

import Expect
import Test exposing (..)
import YourModuleName exposing (add)

suite : Test
suite =
    describe "Una función de suma simple"
        [ test "Sumar 2 y 3 da como resultado 5" <| 
            \_ -> add 2 3 |> Expect.equal 5
        ]

```

Para ejecutar tus pruebas, necesitarás `elm-test`:

```shell
npm install -g elm-test
elm-test
```

Esto compilará tus pruebas e imprimirá los resultados en tu terminal. Para el ejemplo anterior, la salida debería ser algo así como:

```
LA EJECUCIÓN DE LA PRUEBA PASÓ

Duración: 42 ms
Pasadas:   1
Fallidas:   0
```

Para un ejemplo más complejo, digamos que quieres realizar una prueba de fuzz en la función `add` para asegurarte de que maneja correctamente una amplia gama de entradas enteras. Modificarías tu `ExampleTest.elm` de la siguiente manera:

```elm
module ExampleTest exposing (..)

import Expect
import Fuzz exposing (int)
import Test exposing (..)
import YourModuleName exposing (add)

suite : Test
suite =
    describe "Probar add con fuzzing"
        [ fuzz int "Prueba de fuzz en add con enteros aleatorios" <| 
            \int1 int2 -> add int1 int2 |> Expect.equal (int1 + int2)
        ]
```

Ejecuta `elm-test` nuevamente para ver las pruebas de fuzz en acción. La salida variará con entradas aleatorias pero las pruebas exitosas indicarán que no hay fallos:

```
LA EJECUCIÓN DE LA PRUEBA PASÓ

Duración: 183 ms
Pasadas:   100
Fallidas:   0
```

Estos ejemplos muestran cómo escribir y ejecutar pruebas unitarias y de fuzz simples en Elm, utilizando el paquete `elm-explorations/test`. Las pruebas son una parte vital del proceso de desarrollo, ayudando a asegurar que tus aplicaciones Elm sean confiables y mantengan una alta calidad.
