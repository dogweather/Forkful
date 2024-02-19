---
aliases:
- /pt/php/organizing-code-into-functions/
date: 2024-01-26 01:11:28.444969-07:00
description: "Organizar o c\xF3digo em fun\xE7\xF5es trata-se de dividir seu c\xF3\
  digo em blocos reutiliz\xE1veis com prop\xF3sitos definidos. Fazemos isso para manter\
  \ as coisas\u2026"
lastmod: 2024-02-18 23:08:58.246339
model: gpt-4-1106-preview
summary: "Organizar o c\xF3digo em fun\xE7\xF5es trata-se de dividir seu c\xF3digo\
  \ em blocos reutiliz\xE1veis com prop\xF3sitos definidos. Fazemos isso para manter\
  \ as coisas\u2026"
title: "Organizando o c\xF3digo em fun\xE7\xF5es"
---

{{< edit_this_page >}}

## O Que & Por Quê?
Organizar o código em funções trata-se de dividir seu código em blocos reutilizáveis com propósitos definidos. Fazemos isso para manter as coisas organizadas, prevenir redundâncias e tornar a depuração algo simples.

## Como fazer:
Imagine que temos um código repetitivo para cumprimentar usuários. Em vez disso, vamos envolvê-lo em uma função chamada `greet_user`:

```php
function greet_user($name) {
    return "Olá, " . $name . "!";
}

echo greet_user("Alice");
echo greet_user("Bob");
```

Saída:
```
Olá, Alice!
Olá, Bob!
```

Agora, você tem uma ferramenta prática que pode usar a qualquer momento sem reescrever as mesmas linhas de código todas as vezes que quiser dizer olá.

## Aprofundamento
As funções estão na programação desde os primórdios do FORTRAN nos anos 50. Elas são uma pedra angular da programação estruturada e têm a ver com modularidade e isolamento. Alternativas? Bem, você pode adotar a orientação a objetos e falar sobre classes e métodos, que são funções com um traje elegante. Quanto ao PHP, detalhes de implementação incluem especificar valores padrão para parâmetros, indicação de tipo para entradas e a possibilidade de retornar múltiplos valores usando um array ou, a partir do PHP 7.1, uma lista.

Aqui está um toque moderno com declaração de tipo e valores padrão:

```php
function add(float $a, float $b = 0.0): float {
    return $a + $b;
}

echo add(1.5);
echo add(1.5, 2.5);
```

O PHP 7.4 também introduziu funções de seta, ajudando a escrever funções concisas de uma linha só, comumente usadas em operações de array:

```php
$numbers = array(1, 2, 3, 4);
$squared = array_map(fn($n) => $n * $n, $numbers);
print_r($squared);
```

Saída:
```
Array
(
    [0] => 1
    [1] => 4
    [2] => 9
    [3] => 16
)
```

## Veja Também
- [Manual do PHP sobre Funções](https://www.php.net/manual/pt_BR/functions.user-defined.php)
- [PHP: Do Jeito Certo - Funções](https://phptherightway.com/#functions)
- [Aprenda sobre as Funções de Seta do PHP 7.4](https://stitcher.io/blog/short-closures-in-php)
