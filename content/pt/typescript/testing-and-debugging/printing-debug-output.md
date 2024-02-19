---
aliases:
- /pt/typescript/printing-debug-output/
date: 2024-01-20 17:53:47.711536-07:00
description: "Imprimir sa\xEDdas de depura\xE7\xE3o \xE9 soltar info \xFAtil no console\
  \ que ajuda a entender o que seu c\xF3digo est\xE1 aprontando. Programadores fazem\
  \ isso pra desenrolar\u2026"
lastmod: 2024-02-18 23:08:57.887527
model: gpt-4-1106-preview
summary: "Imprimir sa\xEDdas de depura\xE7\xE3o \xE9 soltar info \xFAtil no console\
  \ que ajuda a entender o que seu c\xF3digo est\xE1 aprontando. Programadores fazem\
  \ isso pra desenrolar\u2026"
title: "Exibindo sa\xEDdas de depura\xE7\xE3o"
---

{{< edit_this_page >}}

## What & Why? (O Quê e Por Quê?)
Imprimir saídas de depuração é soltar info útil no console que ajuda a entender o que seu código está aprontando. Programadores fazem isso pra desenrolar bugs ou entender o fluxo do programa.

## How to: (Como Fazer:)
```TypeScript
// Imprimir uma string simples
console.log('Olá, depuração!');

// Imprimir uma variável
let vida = 42;
console.log(vida);

// Imprimir vários valores de uma vez
let x = 2, y = 3;
console.log('Valores:', x, y);

// Imprimir objetos e arrays de maneira legível
let heroi = { nome: 'Zé Código', level: 7 };
console.log(heroi);

let sequencia = [1, 1, 2, 3, 5, 8, 13];
console.log(sequencia);

// Utilizando template literals para concatenar valores
console.log(`O herói ${heroi.nome} está no level ${heroi.level}`);
```
_Saída Exemplar:_
```
Olá, depuração!
42
Valores: 2 3
{ nome: 'Zé Código', level: 7 }
[1, 1, 2, 3, 5, 8, 13]
O herói Zé Código está no level 7
```

## Deep Dive (Mergulho Profundo)
Desde os primórdios da programação, ler a saída dos programas era o principal modo de entender o que estava acontecendo na caixa preta do computador. Registrar (log) eventos no console segue sendo a ferramenta de depuração mais facilmente acessível e geralmente é a primeira coisa que um dev tenta.

Outras ferramentas de depuração, como breakpoints e inspetores de variáveis estão incluídos em IDEs modernos e são úteis para um controle mais fino, mas requerem configuração e têm uma curva de aprendizado.

No TypeScript, a função `console.log` é herdada do JavaScript e opera de maneira idêntica, imprimindo para o stdout ou para a tela do console de ferramentas de desenvolvedor. A beleza do `console.log` é sua simplicidade — não requer instalação de ferramentas extras ou configuração complicada.

## See Also (Veja Também)
- [TypeScript Documentation - Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [MDN Web Docs - Console](https://developer.mozilla.org/pt-BR/docs/Web/API/Console)
- [Node.js os módulos util.format() para saída formatada](https://nodejs.org/api/util.html#utilformatformat-args)
- [Debugging TypeScript in Visual Studio Code](https://code.visualstudio.com/docs/typescript/typescript-debugging)
