---
title:                "Convertendo uma string para minúsculas"
date:                  2024-01-20T17:38:47.774819-07:00
model:                 gpt-4-1106-preview
simple_title:         "Convertendo uma string para minúsculas"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/javascript/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Converter uma string para letras minúsculas significa transformar todos os caracteres alfabéticos dentro dela para a sua forma minúscula. Programadores fazem isso para normalizar texto, facilitando comparações e buscas de padrões, sem se preocupar com a capitalização original.

## Como fazer:
```Javascript
let frase = "Olá, Mundo!";
let fraseMin = frase.toLowerCase();

console.log(fraseMin); // saída: "olá, mundo!"
```

## Mergulho Profundo
No mundo do Javascript, a função `toLowerCase()` é como uma ferramenta antiga numa caixa nova. Faz parte do ECMAScript desde a primeira versão, e a razão para sua permanência é simples: é essencial. Antes de métodos como `toLowerCase()`, programadores precisavam criar suas próprias funções para lidar com a conversão de caracteres, comparando manualmente os códigos ASCII ou Unicode correspondentes.

Alternativas existem, mas são variantes para casos específicos. Por exemplo, `toLocaleLowerCase()` leva em conta a localidade do usuário, o que pode ser crucial para idiomas com regras de minúsculas/maiúsculas únicas.

Quanto à implementação, quando você invoca `toLowerCase()`, por trás dos panos, o Javascript vai mapeando cada caractere alfabético para o equivalente em minúscula baseado na tabela Unicode. Isso significa que não só os caracteres latinos são cobertos, como também um mundo de alfabetos diferentes será corretamente tratado.

## Veja Também
- Documentação MDN sobre `toLowerCase()`: [MDN toLowerCase](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
- Tabela Unicode para entender como os caracteres são mapeados: [Unicode Character Table](https://unicode-table.com/)
- Artigo sobre localização e internacionalização em Javascript: [MDN Internationalization](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Intl)
