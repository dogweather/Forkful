---
title:                "Lectura de un archivo de texto"
aliases:
- es/haskell/reading-a-text-file.md
date:                  2024-01-20T17:54:17.631758-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lectura de un archivo de texto"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/haskell/reading-a-text-file.md"
---

{{< edit_this_page >}}

## ¿Qué & Por Qué?
Leer un archivo de texto en programación implica acceder y obtener el contenido almacenado en un archivo. Los programadores lo hacen para procesar o analizar datos, configuraciones, o simplemente recuperar información para usar en sus aplicaciones.

## Cómo hacerlo:
Leer un archivo en Haskell es sencillo. Vamos a usar la función `readFile`, que forma parte del módulo `Prelude`. Aquí está el ejemplo:

```Haskell
main :: IO ()
main = do
    contenido <- readFile "archivo.txt"
    putStrLn contenido
```

Si tu archivo `archivo.txt` tiene el texto `Hola, mundo!`, la salida será:

```
Hola, mundo!
```

## Profundizamos
Leer archivos en Haskell ha evolucionado a lo largo del tiempo. Antes, se usaban funciones más básicas y ahora hay múltiples alternativas como `readFile`, `getContents` y bibliotecas de terceros. La elección depende del uso específico, como procesamiento en paralelo o manejo de grandes archivos sin cargar todo en memoria.

Haskell maneja la E/S (Entrada/Salida) de una manera especial a través de monadas, que encapsulan los efectos secundarios. `readFile` es no estricta, lee el archivo a medida que se necesita el contenido, lo cual es útil para archivos grandes. Alternativamente, `Data.ByteString` o `Data.Text` ofrecen más control y eficiencia con diferentes tipos de datos.

## Ver También
- [Haskell IO tutorial](https://www.haskell.org/tutorial/io.html)
- [Haskell `ByteString` library](https://hackage.haskell.org/package/bytestring)
- [Haskell `Text` library](https://hackage.haskell.org/package/text)
