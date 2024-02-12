---
title:                "Concatenando strings"
aliases:
- /pt/php/concatenating-strings/
date:                  2024-01-20T17:35:33.731743-07:00
model:                 gpt-4-1106-preview
simple_title:         "Concatenando strings"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/php/concatenating-strings.md"
---

{{< edit_this_page >}}

## O que é & Por quê?

Concatenar strings é basicamente juntá-las para formar uma nova. Programadores fazem isso para montar mensagens, caminhos de arquivos, consultas SQL, dentre outras necessidades de mesclar textos de maneira dinâmica.

## Como Faz:

```php
<?php
$primeiroNome = "João";
$sobrenome = "Silva";
$nomeCompleto = $primeiroNome . " " . $sobrenome;
echo $nomeCompleto; // Saída: João Silva
?>
```
Você pode também concatenar e atribuir ao mesmo tempo:
```php
<?php
$saudacao = "Olá, ";
$saudacao .= "João!";
echo $saudacao; // Saída: Olá, João!
?>
```

## Mergulho Profundo:

Historicamente, a concatenação de strings em PHP sempre foi feita com o operador ponto (.), sem muitas complicações. Existem alternativas, como a função `sprintf` ou interpolação com aspas duplas, mas para unir partes simples, o ponto é rei. 

A partir do PHP 8.0, há também a função `str_concat()`, oferecendo uma nova maneira de concatenar strings, embora o operador ponto ainda seja mais comum.

Detalhes de implementação importantes incluem entender que a concatenação pode consumir mais memória e ser menos eficiente que a interpolação em casos de strings muito grandes, mas para a maioria dos casos de uso cotidianos, a diferença é negligenciável.

```php
// Interpolação com aspas duplas
$nomeCompleto = "$primeiroNome $sobrenome";

// Uso da função sprintf
$nomeCompleto = sprintf("%s %s", $primeiroNome, $sobrenome);

// PHP 8.0 str_concat()
$nomeCompleto = str_concat($primeiroNome, " ", $sobrenome);
```

Lembrando que, antes de PHP 8.0, não existia a função `str_concat()`, e a concatenação era exclusivamente pelo operador ponto.

## Veja Também:

- A documentação oficial do PHP sobre strings para entender melhor todos os aspectos das strings em PHP: [https://www.php.net/manual/pt_BR/language.types.string.php](https://www.php.net/manual/pt_BR/language.types.string.php)
- Você pode ler mais sobre a função `sprintf` aqui: [https://www.php.net/manual/pt_BR/function.sprintf.php](https://www.php.net/manual/pt_BR/function.sprintf.php)
- E se estiver curioso(a) sobre as novidades do PHP 8, incluindo a `str_concat()`: [https://www.php.net/releases/8.0/en.php](https://www.php.net/releases/8.0/en.php)
