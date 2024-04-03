---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:56:21.676432-07:00
description: "Organizar o c\xF3digo em fun\xE7\xF5es \xE9 sobre estruturar o seu c\xF3\
  digo do Google Apps Script separando segmentos l\xF3gicos em blocos distintos, cada\
  \ um realizando\u2026"
lastmod: '2024-03-13T22:44:46.114165-06:00'
model: gpt-4-0125-preview
summary: "Organizar o c\xF3digo em fun\xE7\xF5es \xE9 sobre estruturar o seu c\xF3\
  digo do Google Apps Script separando segmentos l\xF3gicos em blocos distintos, cada\
  \ um realizando uma tarefa espec\xEDfica."
title: "Organizando c\xF3digo em fun\xE7\xF5es"
weight: 18
---

## Como fazer:
No Google Apps Script, que é baseado em JavaScript, você define funções usando a palavra-chave `function`, seguida por um nome de função único, parênteses `()` que podem conter parâmetros, e chaves `{}` que encapsulam o bloco de código da função. Aqui está um exemplo básico:

```javascript
function greetUser() {
  var user = Session.getActiveUser().getEmail();
  Logger.log('Olá, ' + user + '!');
}

greetUser();
```

Saída de amostra:

```
Olá, alguem@exemplo.com!
```

Agora, vamos considerar um exemplo mais prático relacionado ao Google Sheets onde separamos a funcionalidade em duas funções: uma para configurar a planilha e outra para preenchê-la com dados.

```javascript
function setupSheet() {
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var sheet = ss.getSheets()[0];
  sheet.setName('Dados de Vendas');
  sheet.appendRow(['Item', 'Quantidade', 'Preço']);
}

function populateSheet(data) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Dados de Vendas');
  data.forEach(function(row) {
    sheet.appendRow(row);
  });
}

// Inicializa o array de dados
var salesData = [
  ['Widgets', 15, 2.5],
  ['Gadgets', 8, 3.75]
];

// Executa as funções
setupSheet();
populateSheet(salesData);
```

Neste exemplo, `setupSheet` prepara a planilha, e `populateSheet` pega um array de dados de vendas para preencher a planilha. Separar essas preocupações torna o código mais limpo e mais adaptável a mudanças.

## Aprofundamento
O conceito de dividir código em funções não é novo ou único do Google Apps Script; é uma prática de programação fundamental defendida em quase todas as linguagens de programação. Historicamente, funções evoluíram do conceito matemático de mapear entradas para saídas, o que se tornou um pilar na programação estruturada. Esta abordagem promove modularidade e reutilização de código, oferecendo caminhos claros para testar partes individuais do script.

O Google Apps Script, sendo baseado em JavaScript, beneficia-se significativamente das funções de primeira classe do JavaScript, permitindo que funções sejam passadas como argumentos, retornadas de outras funções, e atribuídas a variáveis. Essa característica abre possibilidades para padrões avançados como callbacks e programação funcional, embora esses padrões possam introduzir complexidade que pode ser desnecessária para tarefas simples de automação no Google Apps Script.

Para projetos maiores ou aplicações mais complexas, os desenvolvedores podem explorar recursos mais novos do JavaScript como funções de seta, async/await para operações assíncronas e até TypeScript para tipagem estática. TypeScript, em particular, pode ser compilado para rodar como Google Apps Script, fornecendo um caminho para desenvolvedores que buscam uma verificação de tipo mais robusta e recursos orientados a objetos avançados.

No entanto, para a maioria das necessidades de script dentro da suíte Google Apps, manter funções simples e bem organizadas como demonstrado fornece uma base sólida. É sempre um equilíbrio entre aproveitar recursos avançados para eficiência e manter simplicidade para facilidade de manutenção e legibilidade.
