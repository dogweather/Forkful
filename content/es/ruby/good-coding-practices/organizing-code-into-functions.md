---
date: 2024-01-26 01:11:28.382482-07:00
description: "Organizar el c\xF3digo en funciones divide tu script en bloques reutilizables.\
  \ Se trata de hacer que tu c\xF3digo sea limpio, manejable y menos propenso a\u2026"
lastmod: '2024-03-13T22:44:59.596808-06:00'
model: gpt-4-1106-preview
summary: "Organizar el c\xF3digo en funciones divide tu script en bloques reutilizables."
title: "Organizando c\xF3digo en funciones"
weight: 18
---

## Cómo hacerlo:
Imagina que estás escribiendo un script rápido para saludar a los usuarios:

```Ruby
def greet(name)
  "¡Hola, #{name}!"
end

puts greet("Alice")   # Salida: ¡Hola, Alice!
puts greet("Bob")     # Salida: ¡Hola, Bob!
```

O tal vez estás calculando el área de un círculo:

```Ruby
def circle_area(radius)
  Math::PI * radius ** 2
end

puts circle_area(5)   # Salida: 78.53981633974483
```

Más ordenado y fácil de manejar, ¿verdad?

## Análisis Profundo
El concepto de funciones, también conocido como métodos en Ruby, no es nuevo; es tan antiguo como la programación misma. Volviendo a los años 50, las subrutinas, como se les conocía, se introdujeron para reducir la redundancia.

¿Alternativas? Claro, tienes código en línea, podrías usar OOP con clases y objetos, o incluso programación funcional con lambdas y procs. Pero las funciones son la base del código ordenado. ¿Quieres rendimiento? Las variables locales en funciones son rápidas y las funciones pueden devolver valores inmediatamente con `return`.

En términos de implementación, puedes definir una función con `def` y terminarla con `end`. Puedes establecer parámetros predeterminados, usar operadores splat para funciones variádicas y más. Las funciones pueden ser tan simples o complejas como desees.

## Ver También
- [Documentación de métodos de Ruby](https://ruby-doc.org/core-2.7.0/Method.html)
- [Learn to Program de Chris Pine](https://pine.fm/LearnToProgram/)
- [Practical Object-Oriented Design in Ruby de Sandi Metz](https://www.poodr.com/)
