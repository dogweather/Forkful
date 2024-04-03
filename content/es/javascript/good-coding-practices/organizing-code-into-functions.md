---
date: 2024-01-26 01:10:51.916332-07:00
description: "Organizar el c\xF3digo en funciones divide las tareas en piezas reutilizables,\
  \ lo que hace que el c\xF3digo sea m\xE1s limpio y mantenible. Hacemos esto para\u2026"
lastmod: '2024-03-13T22:44:59.464182-06:00'
model: gpt-4-1106-preview
summary: "Organizar el c\xF3digo en funciones divide las tareas en piezas reutilizables,\
  \ lo que hace que el c\xF3digo sea m\xE1s limpio y mantenible."
title: "Organizando c\xF3digo en funciones"
weight: 18
---

## Cómo hacerlo:
```javascript
// Definir una función para calcular el área de un rectángulo
function calculateArea(ancho, alto) {
  return ancho * alto;
}

// Llamar a la función e imprimir el resultado
let area = calculateArea(5, 3);
console.log(area); // Salida: 15
```

```javascript
// Agrupar funcionalidad relacionada usando funciones
function saludar(nombre) {
  console.log(`Hola, ${nombre}!`);
}

function despedir(nombre) {
  console.log(`Adiós, ${nombre}!`);
}

saludar('Alice'); // Salida: Hola, Alice!
despedir('Bob'); // Salida: Adiós, Bob!
```

## Profundización
Históricamente, lenguajes de programación imperativa como las primeras versiones de BASIC o Assembly carecían de la abstracción que proporcionan las funciones. Con el tiempo, la idea del código modular en lenguajes como C introdujo la noción de que dividir el código en unidades (funciones o procedimientos) conduce a una mejor organización y una lógica más clara.

En JavaScript, además de funciones simples, contamos con funciones flecha desde ES6 (2015) que proporcionan una sintaxis más concisa y son adecuadas para funciones que no sean métodos.

Las alternativas y mejoras en torno a la organización del código en JavaScript incluyen enfoques orientados a objetos utilizando clases, o paradigmas de programación funcional que tratan las funciones como ciudadanos de primera clase.

En términos de implementación, las funciones de JavaScript admiten cierres (closures), proporcionando una forma de retener el acceso al ámbito de una función después de su ejecución, lo que es poderoso para la encapsulación y la creación de funciones de fábrica, entre otros patrones.

## Ver También
- MDN Web Docs sobre Funciones: https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Functions
- Patrones de Diseño en JavaScript: https://addyosmani.com/resources/essentialjsdesignpatterns/book/
- Código Limpio JavaScript: https://github.com/ryanmcdermott/clean-code-javascript
