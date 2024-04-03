---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:52:46.081604-07:00
description: "La extracci\xF3n de subcadenas implica tomar una porci\xF3n de una cadena,\
  \ esencialmente creando una nueva cadena a partir de una existente. Los programadores\u2026"
lastmod: '2024-03-13T22:44:58.510919-06:00'
model: gpt-4-0125-preview
summary: "La extracci\xF3n de subcadenas implica tomar una porci\xF3n de una cadena,\
  \ esencialmente creando una nueva cadena a partir de una existente."
title: "Extracci\xF3n de subcadenas"
weight: 6
---

## Cómo:
En Google Apps Script, que se basa en JavaScript moderno, la extracción de subcadenas se puede lograr a través de varios métodos, incluidos `substring()`, `substr()` y `slice()`. Cada uno tiene sus matices, pero todos sirven para extraer caracteres especificados de una cadena.

```javascript
// Ejemplo usando substring()
var str = "Hola, mundo!";
var result = str.substring(0, 5);
console.log(result); // Salida: Hola

// Ejemplo usando substr()
var resultSubstr = str.substr(7, 5);
console.log(resultSubstr); // Salida: mundo

// Ejemplo usando slice()
var resultSlice = str.slice(-6);
console.log(resultSlice); // Salida: mundo!
```

Cada método toma dos argumentos: la posición de inicio y, excepto por `slice()` que puede aceptar índices negativos para comenzar desde el final, la posición de fin o el número de caracteres a extraer. Vale la pena señalar que la cadena original permanece sin cambios después de estas operaciones, ya que devuelven nuevos valores de cadena.

## Análisis Profundo
Históricamente, los métodos de JavaScript para extraer subcadenas han sido una fuente de confusión debido a sus nombres y funcionalidades similares. Sin embargo, en Google Apps Script y JavaScript moderno, `substring()` y `slice()` son los más utilizados, considerándose `substr()` como obsoleto. Esto es importante a tener en cuenta para aquellos que escriben código a prueba de futuro.

La principal diferencia entre `substring()` y `slice()` es cómo manejan los índices negativos; `substring()` trata los índices negativos como 0, mientras que `slice()` puede aceptar un índice negativo para comenzar la extracción desde el final de la cadena. Esto hace que `slice()` sea particularmente útil para casos en los que la longitud exacta de la cadena podría no ser conocida o cuando se necesita extraer desde el final.

Al decidir qué método utilizar para la extracción de subcadenas, la elección a menudo se reduce a los requisitos específicos de la operación (por ejemplo, si es beneficioso manejar índices negativos) y los estándares de codificación personales o del equipo. Aunque no hay una mejor práctica única para todos, entender las diferencias sutiles y las implicaciones de rendimiento puede ayudar a tomar una decisión informada.
