---
title:                "Imprimindo a saída de depuração"
aliases:
- /pt/google-apps-script/printing-debug-output/
date:                  2024-02-01T21:57:52.924566-07:00
model:                 gpt-4-0125-preview
simple_title:         "Imprimindo a saída de depuração"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/google-apps-script/printing-debug-output.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?

Imprimir saídas de depuração envolve colocar estrategicamente declarações de registro no seu código para exibir valores de variáveis, fluxo de execução ou mensagens de erro durante a execução. Programadores utilizam isso extensivamente para rastrear e diagnosticar o comportamento de seus scripts, garantindo correção e eficiência em suas aplicações do Google Apps Script.

## Como fazer:

O Google Apps Script oferece a classe `Logger` para depuração básica, e para necessidades mais avançadas, a classe `console` introduzida no tempo de execução V8.

**Usando Logger:**

A classe Logger permite que você registre mensagens de depuração, as quais você pode visualizar após a execução no Editor do Apps Script em `Visualizar > Logs`. Aqui está um exemplo simples:

```javascript
function logSample() {
  var name = "Wired Reader";
  Logger.log("Olá, %s!", name);
}
```

Após executar `logSample()`, você pode visualizar o log com "Olá, Wired Reader!" no visualizador de Logs.

**Usando console.log com o tempo de execução V8:**

Com o tempo de execução V8, `console.log` proporciona uma sintaxe mais familiar para desenvolvedores que vêm de outras linguagens:

```javascript
function consoleSample() {
  var status = 'ativo';
  var count = 150;
  console.log(`Status atual: ${status}, Contagem: ${count}`);
}
```

Após a execução, acesse o Registro do Stackdriver em `Visualizar > Registro do Stackdriver` para visualizar a saída. É mais poderoso, suportando interpolação de strings e inspeção de objetos, e integra-se com o registro do Google Cloud, oferecendo logs persistentes e recursos avançados de filtragem.

**Saída de Exemplo do console.log:**

```
Status atual: ativo, Contagem: 150
```

## Aprofundamento

Inicialmente, `Logger.log` era a ferramenta primária para depuração no Google Apps Script, oferecendo uma maneira simples e direta de imprimir saídas para inspeção. No entanto, à medida que os scripts se tornam mais complexos e integrados aos serviços da Google Cloud Platform, a necessidade de uma solução de registro mais robusta tornou-se evidente.

Então veio o tempo de execução V8, trazendo `console.log` para o cenário. Isso não apenas alinha o Google Apps Script com a sintaxe JavaScript padrão, tornando a linguagem mais acessível para desenvolvedores familiarizados com JavaScript, mas também aproveita a poderosa infraestrutura de registro do Google Cloud. A introdução de `console.log` e sua integração com a Google Cloud Platform marca uma evolução significativa nas capacidades de depuração dentro do Google Apps Script, proporcionando aos desenvolvedores uma abordagem mais dinâmica e escalável para monitorar e solucionar problemas em seus scripts.

Enquanto `Logger.log` é suficiente para necessidades básicas de depuração e projetos pequenos, `console.log` com o tempo de execução V8 oferece uma solução mais abrangente e preparada para o futuro. Isso inclui a capacidade de reter logs além da sessão de execução, pesquisar e filtrar logs dentro do console do Google Cloud, e o alinhamento geral com as práticas modernas de desenvolvimento em JavaScript. No entanto, os desenvolvedores devem avaliar suas necessidades contra a complexidade e escala de seus projetos ao escolher entre essas opções.
