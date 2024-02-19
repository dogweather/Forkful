---
aliases:
- /es/fish-shell/interpolating-a-string/
date: 2024-01-20 17:50:36.479815-07:00
description: "Interpolar una cadena consiste en insertar variables o expresiones en\
  \ medio de una cadena de texto. Programadores lo hacen para construir mensajes\u2026"
lastmod: 2024-02-18 23:09:10.435953
model: gpt-4-1106-preview
summary: "Interpolar una cadena consiste en insertar variables o expresiones en medio\
  \ de una cadena de texto. Programadores lo hacen para construir mensajes\u2026"
title: "Interpolaci\xF3n de cadenas de texto"
---

{{< edit_this_page >}}

## ¿Qué y por qué?
Interpolar una cadena consiste en insertar variables o expresiones en medio de una cadena de texto. Programadores lo hacen para construir mensajes dinámicos sin complicarse concatenando trozos de texto.

## Cómo hacerlo:
En Fish Shell, interpolar es sencillo. Usa las comillas dobles para interpretar variables dentro de una cadena. Si la variable es `username` y vale `Juan`, aquí tienes un ejemplo:

```Fish Shell
set username Juan
echo "Hola, $username. ¿Qué tal tu día?"
```

Salida:

```
Hola, Juan. ¿Qué tal tu día?
```

## Buceo Profundo
Históricamente, la interpolación de cadenas ha facilitado la generación de texto. En otros shells, como Bash, requieres un símbolo especial (`$`) delante de la variable. Fish es más legible porque puedes omitirlo dentro de comillas dobles. Aunque Fish no soporta brace expansion como Bash, ofrece otras maneras de manipular datos con su sintaxis simple y directa. La implementación usa expansión de variables y permite la combinación de texto estático y variables para crear salida personalizada y flexible.

## Ver También
- Documentación oficial de la expansión de variables en Fish: [https://fishshell.com/docs/current/#variable-expansion](https://fishshell.com/docs/current/#variable-expansion)
- Una comparación general de las shells de Unix: [https://en.wikipedia.org/wiki/Comparison_of_command_shells](https://en.wikipedia.org/wiki/Comparison_of_command_shells)
