---
date: 2024-01-26 01:09:08.408602-07:00
description: "Dividir el c\xF3digo en funciones significa descomponer los scripts\
  \ en bloques m\xE1s peque\xF1os y reutilizables que realizan tareas espec\xEDficas.\
  \ Hace que el\u2026"
lastmod: '2024-03-13T22:44:59.252013-06:00'
model: gpt-4-1106-preview
summary: "Dividir el c\xF3digo en funciones significa descomponer los scripts en bloques\
  \ m\xE1s peque\xF1os y reutilizables que realizan tareas espec\xEDficas."
title: "Organizando c\xF3digo en funciones"
weight: 18
---

## Cómo hacerlo:
Crear una función simple en Bash:

```Bash
saludar() {
  echo "¡Hola, $1!"
}
```

Utilízala llamando a la función con un parámetro:

```Bash
saludar "Mundo"  # Salida: ¡Hola, Mundo!
```

Las funciones pueden retornar valores usando `return` para códigos de estado numéricos (no para retornar datos reales):

```Bash
sumar() {
  return $(($1 + $2))
}

sumar 3 4
echo $?  # Salida: 7
```

Nota que `$?` captura el valor de retorno del último comando, que es el resultado numérico de `sumar`.

## Análisis en Profundidad
En Bash, las funciones han sido una manera de compartimentar el código desde las primeras versiones. Históricamente, el uso de funciones se alinea con los principios de la programación estructurada introducidos en los años 60 para mejorar la calidad del código.

Alternativas a las funciones incluyen la incorporación de archivos de script o el uso de alias, pero estos no ofrecen el mismo nivel de modularidad y reutilización.

Un detalle de implementación notable en Bash es que las funciones son ciudadanas de primera clase; no tienen una palabra clave de declaración específica como `function` en otros lenguajes, aunque `function` es opcional en Bash por legibilidad. El ámbito de la función también es interesante: las variables son globales por defecto a menos que se declaren como locales, lo que puede llevar a un comportamiento inesperado si no se manejan adecuadamente.

## Vea También
- Manual de Bash sobre Funciones de Shell: https://www.gnu.org/software/bash/manual/html_node/Shell-Functions.html
- Guía Avanzada de Scripting en Bash: https://tldp.org/LDP/abs/html/functions.html
- "Pro Bash Programming: Scripting the GNU/Linux Shell" para conceptos y prácticas de scripting de funciones en profundidad.
