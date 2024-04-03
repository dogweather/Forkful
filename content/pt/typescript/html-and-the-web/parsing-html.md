---
date: 2024-01-20 15:34:09.632447-07:00
description: "Analisar HTML \xE9 o processo de converter string contendo HTML em algo\
  \ que possamos manipular no c\xF3digo, como um DOM (Document Object Model). Programadores\u2026"
lastmod: '2024-03-13T22:44:46.323757-06:00'
model: unknown
summary: "Analisar HTML \xE9 o processo de converter string contendo HTML em algo\
  \ que possamos manipular no c\xF3digo, como um DOM (Document Object Model)."
title: "An\xE1lise de HTML"
weight: 43
---

## Como Fazer:
Para analisar HTML em TypeScript, você pode usar a biblioteca `node-html-parser`. Aqui está um exemplo de código simples para começar:

```typescript
import { parse } from 'node-html-parser';

// Exemplo de HTML para analisar
const html = `<ul class="frutas">
  <li>Maçã</li>
  <li>Banana</li>
  <li>Laranja</li>
</ul>`;

// Analisando o HTML
const root = parse(html);

// Acessando elementos
const frutas = root.querySelectorAll('li').map(ele => ele.innerText);
console.log(frutas);
```

Saída esperada:

```
[ 'Maçã', 'Banana', 'Laranja' ]
```

## Mergulho Profundo
O ato de analisar HTML existe desde o início da web, permitindo que servidores e clientes comunicassem conteúdo dinâmico. Hoje, além do `node-html-parser`, existem outras bibliotecas como `Cheerio` ou `jsdom`, cada uma com suas peculiaridades e casos de uso específicos. 

O `node-html-parser` é leve e rápido, mas não simula um navegador real, então é melhor para análise de HTML estático. `Cheerio` oferece uma API similar ao jQuery, o que pode ser conveniente para quem já conhece jQuery. Já `jsdom` é mais pesado, mas pode simular um ambiente de navegador inteiro, com suporte a eventos e interações mais complexas.

Detalhes importantes ao analisar HTML incluem lidar com HTML mal formado e evitar ataques de injeção de scripts.

## Veja Também
- [node-html-parser - GitHub](https://github.com/taoqf/node-html-parser)
- [Cheerio](https://cheerio.js.org/)
- [jsdom](https://github.com/jsdom/jsdom)
- [DOM - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
