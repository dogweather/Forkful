---
date: 2024-01-20 17:50:13.981080-07:00
description: "La interpolaci\xF3n de cadenas es insertar valores de variables en medio\
  \ de una cadena de texto. En Bash, los programamos para ahorrar tiempo y evitar\u2026"
lastmod: '2024-03-13T22:44:59.230703-06:00'
model: gpt-4-1106-preview
summary: "La interpolaci\xF3n de cadenas es insertar valores de variables en medio\
  \ de una cadena de texto."
title: "Interpolaci\xF3n de cadenas de texto"
weight: 8
---

## Cómo hacerlo:
A continuación, unos ejemplos de cómo interpolamos cadenas en Bash:

```Bash
nombre="Mundo"
# Interpolación básica
echo "Hola, $nombre"

# Interpolación con llaves para claridad
puesto="profesor"
echo "Hola, ${nombre}, eres un gran ${puesto}."

# Ejemplo con comando subshell
echo "Tengo $(ls | wc -l) archivos en el directorio actual."
```

Salida esperada:
```
Hola, Mundo
Hola, Mundo, eres un gran profesor.
Tengo 42 archivos en el directorio actual.
```

## Detalles Profundos
La interpolación de cadenas ha sido una característica en los shells desde los tiempos del Bourne Shell. En Bash, la interpolación permite no solo la inclusión de variables, sino también la ejecución de comandos dentro de cadenas usando la sintaxis `$(comando)`. Esencialmente, Bash reemplaza la variable o el comando con su valor de salida. Alternativas como concatenar con `+` no existen en Bash como en otros lenguajes. Siempre ten en cuenta las comillas dobles para permitir la expansión de variables; las comillas simples no lo harán.

## Ver También
- GNU Bash Documentation: https://www.gnu.org/software/bash/manual/
- Advanced Bash-Scripting Guide: https://tldp.org/LDP/abs/html/ 
- Bash String Manipulation Examples: https://linuxhint.com/bash_string_manipulation/
