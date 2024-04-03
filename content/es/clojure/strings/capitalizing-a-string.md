---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:51.124098-07:00
description: "Capitalizar una cadena implica modificar la cadena para que su primer\
  \ car\xE1cter est\xE9 en may\xFAsculas, mientras que el resto de la cadena permanece\
  \ sin\u2026"
lastmod: '2024-03-13T22:44:58.639841-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar una cadena implica modificar la cadena para que su primer car\xE1\
  cter est\xE9 en may\xFAsculas, mientras que el resto de la cadena permanece sin\
  \ cambios."
title: Capitalizando una cadena de texto
weight: 2
---

## Cómo hacerlo:
Clojure, al ser un lenguaje JVM, te permite utilizar directamente los métodos de String de Java. Aquí tienes un ejemplo básico de cómo capitalizar una cadena en Clojure:

```clojure
(defn capitalize-string [s]
  (if (empty? s)
    s
    (str (clojure.string/upper-case (subs s 0 1)) (subs s 1))))

(capitalize-string "hello world!") ; => "Hello world!"
```

Clojure no incluye una función integrada específicamente para capitalizar cadenas, pero como se muestra, puedes lograr fácilmente esto combinando las funciones `clojure.string/upper-case`, `subs` y `str`.

Para una solución más concisa y para manejar manipulaciones de cadenas más complejas, podrías recurrir a una biblioteca de terceros. Una biblioteca popular en el ecosistema de Clojure es `clojure.string`. Sin embargo, hasta mi última actualización, no ofrece una función directa de `capitalize` más allá de lo demostrado con las funcionalidades básicas de Clojure, por lo que el método mostrado arriba es tu enfoque directo sin necesidad de incluir bibliotecas adicionales específicamente para capitalización.

Recuerda, cuando trabajas con cadenas en Clojure que interactúan con métodos de Java, efectivamente estás trabajando con cadenas de Java, lo que te permite aprovechar todo el arsenal de métodos de String de Java directamente en tu código Clojure si es necesario.
