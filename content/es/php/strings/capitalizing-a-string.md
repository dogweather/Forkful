---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:53.781569-07:00
description: "Capitalizar una cadena implica modificar el primer car\xE1cter de un\
  \ texto dado a may\xFAsculas, asegurando que frases, t\xEDtulos o nombres propios\
  \ comiencen\u2026"
lastmod: '2024-03-13T22:44:59.143686-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar una cadena implica modificar el primer car\xE1cter de un texto\
  \ dado a may\xFAsculas, asegurando que frases, t\xEDtulos o nombres propios comiencen\
  \ correctamente en un conjunto de datos."
title: Capitalizando una cadena de texto
weight: 2
---

## Cómo hacerlo:
PHP soporta de forma nativa varias funciones para capitalizar cadenas, cada una sirviendo a un propósito diferente. Así es cómo puedes usarlas:

### Capitalizando la primera letra de una cadena:
```php
$string = "hola, mundo!";
$capitalizedString = ucfirst($string);
echo $capitalizedString; // Devuelve: Hola, mundo!
```

### Capitalizando la primera letra de cada palabra:
```php
$string = "hola, mundo!";
$capitalizedWords = ucwords($string);
echo $capitalizedWords; // Devuelve: Hola, Mundo!
```

### Convirtiendo toda la cadena a mayúsculas:
```php
$string = "hola, mundo!";
$upperCaseString = strtoupper($string);
echo $upperCaseString; // Devuelve: HOLA, MUNDO!
```

Para escenarios que requieren más personalización o soluciones de terceros, se pueden utilizar bibliotecas como `mbstring` (para cadenas de múltiples bytes), especialmente al tratar con internacionalización donde los caracteres pueden extenderse más allá del conjunto básico ASCII.

### Usando mbstring para capitalizar cadenas UTF-8:
Asegúrate de tener habilitada la extensión `mbstring` en tu configuración de PHP, luego:

```php
$string = "élégant";
$capitalizedString = mb_convert_case($string, MB_CASE_TITLE, "UTF-8");
echo $capitalizedString; // Devuelve: Élégant
```

Este enfoque ayuda a capitalizar de manera precisa cadenas que incluyen caracteres no ASCII, adhiriéndose a las sutilezas de varios idiomas.
