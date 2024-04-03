---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:55.318998-07:00
description: "Capitalizar uma string envolve modificar o primeiro caractere de um\
  \ texto dado para mai\xFAsculo, garantindo que frases, t\xEDtulos ou nomes pr\xF3\
  prios comecem\u2026"
lastmod: '2024-03-13T22:44:46.650573-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar uma string envolve modificar o primeiro caractere de um texto\
  \ dado para mai\xFAsculo, garantindo que frases, t\xEDtulos ou nomes pr\xF3prios\
  \ comecem corretamente em um conjunto de dados."
title: Capitalizando uma string
weight: 2
---

## Como fazer:
O PHP suporta nativamente várias funções para capitalizar strings, cada uma servindo a um propósito diferente. Veja como você pode usá-las:

### Capitalizando a primeira letra de uma string:
```php
$string = "hello, world!";
$capitalizedString = ucfirst($string);
echo $capitalizedString; // Exibe: Hello, world!
```

### Capitalizando a primeira letra de cada palavra:
```php
$string = "hello, world!";
$capitalizedWords = ucwords($string);
echo $capitalizedWords; // Exibe: Hello, World!
```

### Convertendo toda a string para maiúsculo:
```php
$string = "hello, world!";
$upperCaseString = strtoupper($string);
echo $upperCaseString; // Exibe: HELLO, WORLD!
```

Para cenários que requerem mais personalização ou soluções de terceiros, bibliotecas como `mbstring` (para strings multibyte) podem ser utilizadas, especialmente quando lidando com internacionalização onde caracteres podem se estender além do conjunto básico ASCII.

### Usando mbstring para capitalizar strings UTF-8:
Certifique-se de ter a extensão `mbstring` habilitada na sua configuração PHP, então:

```php
$string = "élégant";
$capitalizedString = mb_convert_case($string, MB_CASE_TITLE, "UTF-8");
echo $capitalizedString; // Exibe: Élégant
```

Esta abordagem ajuda a capitalizar com precisão strings que incluem caracteres não-ASCII, aderindo às nuances de várias línguas.
