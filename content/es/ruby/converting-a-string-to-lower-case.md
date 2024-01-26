---
title:                "Conversión de una cadena de texto a minúsculas"
date:                  2024-01-20T17:39:30.367191-07:00
model:                 gpt-4-1106-preview
simple_title:         "Conversión de una cadena de texto a minúsculas"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/ruby/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Convertir un texto (string) a minúsculas es cambiar todas las letras del texto a su versión en minúscula. Esto se hace para uniformizar el texto, facilitar las comparaciones sin preocuparse por mayúsculas o minúsculas y para procesar o almacenar datos de manera más consistente.

## How to:
Ruby es amigable. Para convertir un string a minúsculas, usas `.downcase`. Así de sencillo:

```Ruby
saludo = "Hola, Mundo!"
puts saludo.downcase
```

Esto imprime:

```
hola, mundo!
```

Fácil, ¿verdad?

## Deep Dive
Desde los inicios de Ruby, `.downcase` ha estado ahí para ayudarte a manejar la cuestión de las mayúsculas y minúsculas. Es un método estandarizado y directo, parte del módulo `String`. Pero hay más en el horizonte.

Alternativas incluyen `.downcase!`, que cambia el string original en lugar de crear uno nuevo. ¿Por qué importa? Bueno, es cuestión de memoria y eficiencia si estás manejando muchos datos.

```Ruby
saludo = "Hola, Otro Mundo!"
saludo.downcase!
puts saludo
```

Te da el mismo resultado, pero `saludo` ya no va a tener el texto original. Ha sido reemplazado.

Ahora, la implementación. Ruby se asegura de que `.downcase` funcione bien no solo con el alfabeto inglés, sino con caracteres Unicode multilingües. Esto significa que sea español, alemán, francés o ruso, `.downcase` es tu amigo.

## See Also:
Para seguir aprendiendo cómo manejar strings en Ruby:

- La documentación oficial de Ruby sobre strings: [Ruby Docs - String](https://ruby-doc.org/core-2.7.0/String.html)
- Para explorar el funcionamiento interno de Ruby y cómo maneja la codificación de caracteres: [Ruby Encodings](https://ruby-doc.org/core-2.7.0/Encoding.html)
