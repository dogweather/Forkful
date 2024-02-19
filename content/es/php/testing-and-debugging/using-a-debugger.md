---
aliases:
- /es/php/using-a-debugger/
date: 2024-01-26 03:50:35.687650-07:00
description: "Un depurador es una herramienta que ayuda a los programadores a entender\
  \ qu\xE9 est\xE1 haciendo su c\xF3digo realmente mientras se ejecuta. Es la lupa\
  \ que nos\u2026"
lastmod: 2024-02-18 23:09:10.078831
model: gpt-4-0125-preview
summary: "Un depurador es una herramienta que ayuda a los programadores a entender\
  \ qu\xE9 est\xE1 haciendo su c\xF3digo realmente mientras se ejecuta. Es la lupa\
  \ que nos\u2026"
title: Usando un depurador
---

{{< edit_this_page >}}

## ¿Qué y por qué?
Un depurador es una herramienta que ayuda a los programadores a entender qué está haciendo su código realmente mientras se ejecuta. Es la lupa que nos permite acercarnos a los errores—esos problemas molestos que hacen que nuestros programas se cierren o arrojen respuestas incorrectas—y aplastarlos. Utilizamos depuradores porque nos ahorran horas de declaraciones de impresión y juegos de adivinanzas.

## Cómo hacerlo:
PHP viene con un depurador interactivo llamado Xdebug. Así es como se usa.

Primero, asegúrate de tener Xdebug instalado y configurado en tu archivo `php.ini`:

```
zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-xxxxxxxx/xdebug.so
xdebug.mode=debug
xdebug.start_with_request=yes
```

Luego, escribe un script PHP simple con un error:

```PHP
<?php
function add($a, $b) {
    return $a - $b; // ¡Ups! Esto debería ser un más, no un menos
}

$result = add(1, 2);
echo "El resultado es: $result"; // El resultado debería ser 3, no -1
```

Usando un IDE como PhpStorm, establece un punto de interrupción haciendo clic junto al número de línea. Ejecuta el depurador y observa cómo cambian las variables a medida que avanzas en la ejecución. Cuando pasas por encima de la función `add`, notarás que `$result` se convierte en -1, lo cual es inesperado.

## Inmersión Profunda:
Históricamente, PHP se utilizaba principalmente para scripts pequeños, y la depuración era cuestión de agregar declaraciones `var_dump()` y `print_r()` a lo largo del código. Con el tiempo, con PHP convirtiéndose en un actor clave en el desarrollo web, se comenzaron a utilizar herramientas más sofisticadas como Xdebug y Zend Debugger.

Alternativas a Xdebug incluyen pcov y phpdbg. Estos ofrecen varias características pero podrían no ser tan completos como Xdebug. phpdbg es un depurador específico de PHP, ligero, que se distribuye con PHP desde la versión 5.6, y pcov es un controlador de cobertura de código.

Cuando implementes un depurador, recuerda que nunca debes dejar el depurador activado en tu servidor de producción, ya que puede exponer vulnerabilidades de seguridad y ralentizar el rendimiento.

## Ver También:
- [Documentación de Xdebug](https://xdebug.org/docs/)
- [Guía de Depuración de PhpStorm](https://www.jetbrains.com/help/phpstorm/debugging.html)
- [PHP.net sobre phpdbg](https://www.php.net/manual/es/book.phpdbg.php)
- [pcov en GitHub](https://github.com/krakjoe/pcov)
