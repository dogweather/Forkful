---
title:                "Usando um shell interativo (REPL)"
aliases:
- /pt/javascript/using-an-interactive-shell-repl/
date:                  2024-01-26T04:15:31.495023-07:00
model:                 gpt-4-0125-preview
simple_title:         "Usando um shell interativo (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/javascript/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## O Que & Por Quê?
Shells interativos, ou REPLs (Read-Eval-Print Loops, ou Laços de Ler-Avaliar-Imprimir), permitem que você execute código de forma instantânea, testando funções, algoritmos ou brincando com ideias. Eles são os blocos de notas da programação, rápidos e diretos, sem necessidade de configurar um ambiente de desenvolvimento completo.

## Como usar:
O Node.js vem com um REPL acessível através do terminal. Abra-o e você está pronto para começar. Aqui vai uma amostra:

```javascript
$ node
> let sum = (a, b) => a + b;
indefinido
> sum(5, 10);
15
> .exit
```

Simples, certo? Defina variáveis, funções ou execute laços. Quando terminar, `.exit` te leva de volta ao mundo real.

## Aprofundamento
REPLs existem desde a década de 1960 – LISP foi o pioneiro do conceito. A ideia: fornecer feedback imediato ao programador. Alternativas? Além do REPL do Node.js, existem consoles baseados em navegador como o Chrome DevTools, sandboxes online como o JSFiddle, ou IDEs completas como o VSCode com playgrounds interativos.

Por baixo do capô, os workflows do REPL tipicamente:
1. Leem a entrada
2. Compilam e executam o código
3. Imprimem a saída
4. Voltam ao início

É um ciclo simples, mas eficaz que tem influenciado massivamente a codificação interativa.

## Veja Também
- [Documentação do Node.js REPL](https://nodejs.org/api/repl.html)
- [Introdução da Mozilla aos módulos JavaScript em REPLs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)
- [JSFiddle](https://jsfiddle.net/)
