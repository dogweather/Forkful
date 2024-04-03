---
date: 2024-01-26 04:17:03.456985-07:00
description: "Una shell interactiva o REPL (Bucle Leer-Evaluar-Imprimir), te permite\
  \ probar c\xF3digo en tiempo real. Los programadores la utilizan para experimentar,\u2026"
lastmod: '2024-03-13T22:44:59.593088-06:00'
model: gpt-4-0125-preview
summary: "Una shell interactiva o REPL (Bucle Leer-Evaluar-Imprimir), te permite probar\
  \ c\xF3digo en tiempo real."
title: Usando una shell interactiva (REPL)
weight: 34
---

## Cómo hacerlo:
El REPL de Ruby se llama IRB (Ruby Interactivo). Salta y prueba Ruby directamente desde tu terminal:

```Ruby
irb
2.7.0 :001 > puts "¡Hola, mundo de Ruby!"
¡Hola, mundo de Ruby!
 => nil
2.7.0 :002 > 5.times { print "¡Ruby! " }
¡Ruby! ¡Ruby! ¡Ruby! ¡Ruby! ¡Ruby!  => 5
```

## Profundización
Introducido en Ruby 1.8, IRB es un pilar para los Rubyistas. Se inspira en las shells interactivas de Lisp y Python, fusionando la experimentación con retroalimentación inmediata. Alternativas como Pry ofrecen más características como resaltado de sintaxis y un entorno de depuración más robusto. IRB por sí mismo es sencillo pero puede ser complementado con gemas como 'irbtools' para extender la funcionalidad. Cómo maneja IRB el bucle leer-evaluar-imprimir es leyendo cada línea de entrada, evaluándola como código de Ruby y luego imprimiendo el resultado, repitiendo este proceso hasta salir.

## Ver También
- [IRB de Ruby](https://ruby-doc.org/stdlib-2.7.0/libdoc/irb/rdoc/IRB.html)
- [La gema irbtools](https://github.com/janlelis/irbtools)
