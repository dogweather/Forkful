---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:53:50.544310-07:00
description: "Generar n\xFAmeros aleatorios es una tarea fundamental en la programaci\xF3\
  n que se utiliza para una mir\xEDada de aplicaciones, tales como simulaciones, juegos\
  \ y\u2026"
lastmod: '2024-03-13T22:44:58.522163-06:00'
model: gpt-4-0125-preview
summary: "Generar n\xFAmeros aleatorios es una tarea fundamental en la programaci\xF3\
  n que se utiliza para una mir\xEDada de aplicaciones, tales como simulaciones, juegos\
  \ y sistemas de seguridad."
title: "Generando n\xFAmeros aleatorios"
weight: 12
---

## Cómo hacerlo:
En Google Apps Script, puedes generar números aleatorios usando la función `Math.random()`, similar a JavaScript. Esta función devuelve un número pseudoaleatorio de punto flotante en el rango de 0 (inclusive) a 1 (exclusivo). Para adaptar estos números para varios casos de uso, como generar enteros dentro de un rango específico, es posible que necesites realizar cálculos adicionales.

### Generando un Número Aleatorio Básico
Para generar un número aleatorio simple y registrarle en la consola:

```javascript
function generateRandomNumber() {
  var randomNumber = Math.random();
  Logger.log(randomNumber);
}
```
*Salida de muestra:* `0.1234567890123456`

### Generando un Entero Dentro de un Rango Específico
Para generar un entero aleatorio entre dos valores (`min` y `max`), inclusivo:

```javascript
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  var randomNumber = Math.floor(Math.random() * (max - min + 1)) + min;
  Logger.log(randomNumber);
  return randomNumber;
}

// Ejemplo:
getRandomInt(1, 10);
```
*Salida de muestra*: `7`

Recuerda, la función `Math.ceil()` se utiliza para redondear el valor mínimo hacia arriba, y `Math.floor()` se utiliza para redondear el valor máximo hacia abajo, asegurando que el número aleatorio esté dentro del rango especificado.

## Análisis Profundo
El mecanismo para generar números aleatorios en Google Apps Script, y de hecho en la mayoría de los lenguajes de programación, utiliza un generador de números pseudoaleatorios (PRNG, por sus siglas en inglés). Esta técnica es determinista y se basa en un valor inicial, conocido como la semilla, para producir una secuencia de números que parece aleatoria. Aunque es suficiente para muchas aplicaciones, es importante tener en cuenta que los números pseudoaleatorios pueden no ser apropiados donde se requiera alta seguridad o verdadera aleatoriedad, como en aplicaciones criptográficas.

La verdadera aleatoriedad se puede lograr a través de generadores de números aleatorios de hardware o servicios que generan aleatoriedad a partir de fenómenos naturales. Sin embargo, para la mayoría de las necesidades de script diarias en Google Apps Script, `Math.random()` es suficiente.

Históricamente, la búsqueda de técnicas más efectivas de generación de números aleatorios ha llevado al desarrollo de varios algoritmos, siendo ejemplos notables el Mersenne Twister y el Generador Lineal Congruencial (LCG). Sin embargo, dado el alto nivel de abstracción en Google Apps Script, la mayoría de los usuarios no necesitarán implementar estos algoritmos directamente, pero entender los principios subyacentes puede ayudar a apreciar la importancia y las limitaciones de la generación de números aleatorios en tus scripts.
