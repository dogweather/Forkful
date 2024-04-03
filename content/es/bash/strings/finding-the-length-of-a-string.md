---
date: 2024-01-20 17:46:57.635361-07:00
description: "Encontrar la longitud de una cadena significa contar cu\xE1ntos caracteres\
  \ tiene. Los programadores lo hacen para validar entradas, limitar texto, o\u2026"
lastmod: '2024-03-13T22:44:59.235431-06:00'
model: gpt-4-1106-preview
summary: "Encontrar la longitud de una cadena significa contar cu\xE1ntos caracteres\
  \ tiene."
title: Calculando la longitud de una cadena
weight: 7
---

## Cómo hacerlo:
```Bash
cadena="Hola, ¿cómo estás?"
longitud=${#cadena}
echo $longitud
```
Salida:
```Bash
19
```

Para longitudes en un bucle:
```Bash
nombres=("Alicia" "Bruno" "Carlos")
for nombre in "${nombres[@]}"; do
    echo "${nombre} tiene ${#nombre} caracteres."
done
```
Salida:
```Bash
Alicia tiene 6 caracteres.
Bruno tiene 5 caracteres.
Carlos tiene 6 caracteres.
```

## Profundización


#### Contexto Histórico
En los primeros días de la informática, la gestión eficiente del texto era crucial debido a la memoria limitada. Encontrar la longitud de una cadena era (y sigue siendo) una operación fundamental.

#### Alternativas
En Bash, `${#cadena}` es la forma directa de obtener la longitud. Pero hay métodos alternativos, como usar `expr`, `awk`, o un bucle para contar los caracteres.

#### Detalles de Implementación
`${#cadena}` cuenta los caracteres Unicode correctamente, incluso si la cadena contiene caracteres especiales o acentuados. Con idiomas y juegos de caracteres complejos, esto es vital para una correcta manipulación de strings.

## Véase También
- [Bash String Manipulation Guide](https://www.gnu.org/software/bash/manual/bash.html#Shell-Parameter-Expansion)
- [Advanced Bash-Scripting Guide](https://www.tldp.org/LDP/abs/html/)
- Ejemplos prácticos y explicaciones adicionales en [stackoverflow en español](https://es.stackoverflow.com/questions/tagged/bash)
