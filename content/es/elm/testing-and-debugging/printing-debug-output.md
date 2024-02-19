---
aliases:
- /es/elm/printing-debug-output/
date: 2024-01-20 17:52:32.241728-07:00
description: "Imprimir mensajes de depuraci\xF3n es como dejar migajas de pan para\
  \ seguir tu camino en el c\xF3digo. Los programadores lo hacemos para entender qu\xE9\
  \ est\xE1\u2026"
lastmod: 2024-02-18 23:09:09.893509
model: gpt-4-1106-preview
summary: "Imprimir mensajes de depuraci\xF3n es como dejar migajas de pan para seguir\
  \ tu camino en el c\xF3digo. Los programadores lo hacemos para entender qu\xE9 est\xE1\
  \u2026"
title: "Imprimiendo salida de depuraci\xF3n"
---

{{< edit_this_page >}}

## ¿Qué y Por Qué?
Imprimir mensajes de depuración es como dejar migajas de pan para seguir tu camino en el código. Los programadores lo hacemos para entender qué está pasando y por qué, especialmente cuando las cosas se ponen raras.

## Cómo Hacerlo:
Con Elm, usamos `Debug.log` para imprimir en la consola del navegador. Aquí te dejo un ejemplo:

```Elm
import Html

main =
  Html.text (Debug.log "Valor de Debug" "¡Hola, Elm!")

```

Esto imprimirá en la consola del navegador algo como:

```
"Valor de Debug: " "¡Hola, Elm!"
```

Recuerda que `Debug.log` tiene dos argumentos: una etiqueta para la traza y el valor que quieres inspeccionar.

## Análisis Profundo
En Elm, la depuración fue evolucionando con el lenguaje. Originalmente, `Debug.log` era la manera estándar de hacerlo. Pero Elm fomenta la construcción de código que no dependa de efectos secundarios, entonces, usar `Debug.log` no es lo más "Elm-ish". Sin embargo, sigue siendo útil en desarrollo.

Alternativas incluyen el paquete `elm/browser` para funciones más avanzadas de depuración, pero `Debug.log` se mantiene por ser simple y directo.

La implementación de `Debug.log` es parte del runtime de Elm y funciona mediante la impresión de mensajes en la consola JavaScript del navegador. No se compila en producción, así que no hay que preocuparse de limpiar los logs antes de desplegar.

## Ver También
- Paquete `elm/browser` con más herramientas de depuración: [https://package.elm-lang.org/packages/elm/browser/latest/](https://package.elm-lang.org/packages/elm/browser/latest/)
