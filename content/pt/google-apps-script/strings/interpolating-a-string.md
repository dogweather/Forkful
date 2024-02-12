---
title:                "Interpolando uma string"
aliases:
- pt/google-apps-script/interpolating-a-string.md
date:                  2024-02-01T21:55:16.747492-07:00
model:                 gpt-4-0125-preview
simple_title:         "Interpolando uma string"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/google-apps-script/interpolating-a-string.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Que?

A interpolação de strings no Google Apps Script permite a incorporação dinâmica de expressões dentro de strings, facilitando a criação de códigos mais legíveis e fáceis de manter. Programadores usam essa técnica para incorporar variáveis ​​e expressões em strings de maneira suave, sem a sintaxe de concatenação complicada.

## Como Fazer:

No Google Apps Script, a interpolação de strings é alcançada através de literais de template. Estes são literais de string que permitem expressões incorporadas, indicadas por crases (\`) ao invés das aspas usuais. Veja como você pode usá-las:

```javascript
// Um exemplo básico
function basicInterpolationExample() {
  const user = 'Alice';
  console.log(`Olá, ${user}!`); // Saída: Olá, Alice!
}

// Usando expressões
function expressionInterpolationExample() {
  const a = 5;
  const b = 10;
  console.log(`Cinco mais dez é ${a + b}.`); // Saída: Cinco mais dez é 15.
}

// Strings de múltiplas linhas
function multiLineStringExample() {
  const item = 'Google Apps Script';
  console.log(`Esta é uma string de múltiplas linhas:
Olá a todos,
Hoje estamos discutindo ${item}.`);
  // Saída:
  // Esta é uma string de múltiplas linhas:
  // Olá a todos,
  // Hoje estamos discutindo Google Apps Script.
}

basicInterpolationExample();
expressionInterpolationExample();
multiLineStringExample();
```

Estes exemplos ilustram o uso básico, embutindo expressões e criando strings de múltiplas linhas com valores interpolados.

## Aprofundamento

Literais de template, incluindo a interpolação de strings, foram introduzidos no ECMAScript 2015 (ES6) e posteriormente adotados no Google Apps Script. Antes disso, programadores tinham que depender puramente da concatenação de strings, o que poderia se tornar pesado para strings complexas ou ao integrar muitos valores de variáveis.

```javascript
// Maneira antiga (anterior ao ES6)
var user = 'Bob';
console.log('Olá, ' + user + '!');
```

Enquanto a interpolação de strings é uma característica poderosa, é importante estar atento aos contextos nos quais é usada. Por exemplo, a incorporação direta de entrada do usuário sem a devida sanitização pode levar a questões de segurança, como ataques de injeção. Desenvolvedores do Google Apps Script devem garantir que qualquer conteúdo dinâmico interpolado em strings seja devidamente verificado ou sanitizado.

Comparado a outras linguagens de programação, o conceito de interpolação de strings existe amplamente, com sintaxe variável. Python utiliza f-strings ou o método `format`, Ruby usa `#{}` dentro de strings com aspas duplas, e muitas linguagens modernas adotaram características similares devido à legibilidade e conveniência que oferecem.

Embora o Google Apps Script não ofereça recursos de interpolação adicionais além dos fornecidos pelos padrões ECMAScript, a funcionalidade presente é poderosa e suficiente para a maioria dos casos de uso. Desenvolvedores vindos de linguagens com mecanismos de interpolação mais elaborados podem precisar ajustar suas expectativas, mas provavelmente apreciarão a simplicidade e eficiência dos literais de template no Google Apps Script.
