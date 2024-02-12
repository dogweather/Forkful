---
title:                "Imprimiendo salida de depuración"
aliases:
- /es/haskell/printing-debug-output/
date:                  2024-01-20T17:52:53.552439-07:00
model:                 gpt-4-1106-preview
simple_title:         "Imprimiendo salida de depuración"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/haskell/printing-debug-output.md"
---

{{< edit_this_page >}}

## Qué & Por Qué?

La impresión de mensajes de depuración es simplemente mostrar información en la consola para entender qué está pasando en tu código. Los programadores lo hacen para rastrear errores o verificar el flujo del programa.

## Cómo Hacerlo:

Para imprimir algo en Haskell, usualmente usamos la función `print` o `putStrLn`.

```haskell
main :: IO ()
main = do
  putStrLn "Este es un mensaje de depuración"
  print $ 1 + 2
```

Salida:

```
Este es un mensaje de depuración
3
```

Si quieres depurar dentro de una expresión, puedes usar `Debug.Trace`:

```haskell
import Debug.Trace (trace)

sumaDebug :: Int -> Int -> Int
sumaDebug x y = trace ("sumando " ++ show x ++ " y " ++ show y) $ x + y

main :: IO ()
main = print $ sumaDebug 3 4
```

Salida:

```
sumando 3 y 4
7
```

## Profundización

Historicamente, los programas de Haskell no imprimían directamente a la consola, debido a su naturaleza puramente funcional. `Debug.Trace` permite añadir impurezas para la depuración. Como alternativa, puedes usar herramientas más avanzadas como depuradores o profilers para hacer un análisis más detallado.

Haskell define operaciones de impresión en el módulo `System.IO`, y el uso de `print` es realmente un atajo para `putStrLn . show`. `Debug.Trace` es poderoso pero debería usarse con precaución, ya que puede romper la naturaleza perezosa y pura del código, llevando a resultados inesperados si no se retira después de la depuración.

## Ver También

- Haskell Documentation for `Debug.Trace`: https://hackage.haskell.org/package/base-4.15.0.0/docs/Debug-Trace.html
- GHC Documentation, para entender más sobre depuración en Haskell: https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html
- "Real World Haskell", capítulo de depuración y optimización: http://book.realworldhaskell.org/read/profiling-and-optimization.html
