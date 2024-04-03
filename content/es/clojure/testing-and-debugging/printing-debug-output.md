---
date: 2024-01-20 17:52:21.679613-07:00
description: "La impresi\xF3n de salidas de depuraci\xF3n (debug output) es un m\xE9\
  todo para mostrar informaci\xF3n de un programa mientras se ejecuta. Los programadores\
  \ lo usan\u2026"
lastmod: '2024-03-13T22:44:58.659283-06:00'
model: gpt-4-1106-preview
summary: "La impresi\xF3n de salidas de depuraci\xF3n (debug output) es un m\xE9todo\
  \ para mostrar informaci\xF3n de un programa mientras se ejecuta."
title: "Imprimiendo salida de depuraci\xF3n"
weight: 33
---

## Cómo:
Con Clojure, puedes imprimir mensajes usando `println`, `print`, o `prn`. Te dejamos unos ejemplos rápida y concisos:

```Clojure
;; Imprimiendo un simple mensaje
(println "Hola, estoy depurando!")

;; Visualizar el contenido de una variable
(def mi-variable 42)
(println "El valor de mi-variable es:" mi-variable)

;; Inspeccionar una estructura más complicada
(def mi-mapa {:nombre "Carmen" :edad 30})
(prn "Detalles del mapa:" mi-mapa)
```

Salida esperada:

```
Hola, estoy depurando!
El valor de mi-variable es: 42
"Detalles del mapa:" {:nombre "Carmen", :edad 30}
```

## Inmersión Profunda:
La depuración es vital en el desarrollo de software. En Clojure, se hereda la filosofía de Lisp de código como datos, lo que facilita la inspección de estructuras de datos. Históricamente, `println` ha sido una herramienta cruda pero efectiva para la depuración.

Alternativas más avanzadas incluyen herramientas como logging libraries (e.g., `timbre` o `log4j`), que ofrecen más control y flexibilidad. También herramientas de IDE o editores de texto avanzados, como CIDER para Emacs, incorporan capacidades de depuración interactivas.

En la práctica, `println` es implementado en la JVM para Clojure y se beneficia del rendimiento y estabilidad de la plataforma Java. Pero, usarlo excesivamente puede afectar el rendimiento del programa, así que úsalo con moderación.

## Ver También:
- [Clojure.org - reference to special forms including prn](https://clojure.org/reference/special_forms)
- [Clojure for the Brave and True - a humorous and practical guide to Clojure](https://www.braveclojure.com/)
- [Logback - a logging library for Java and JVM languages](http://logback.qos.ch/)
- [CIDER - the Clojure Interactive Development Environment that Rocks for Emacs](https://cider.mx/)
