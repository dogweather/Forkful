---
title:                "Convertendo uma string para minúsculas"
aliases:
- /pt/arduino/converting-a-string-to-lower-case/
date:                  2024-01-20T17:37:43.092097-07:00
model:                 gpt-4-1106-preview
simple_title:         "Convertendo uma string para minúsculas"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/arduino/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## O Que é & Porquê?
Converter uma string para minúsculas significa transformar todos os caracteres alfabéticos da string de maiúsculas para minúsculas. Programadores realizam isso para padronizar dados, simplificar comparações e buscas de texto.

## Como Fazer:
```Arduino
String mensagem = "Olá, MUNDO!";
mensagem.toLowerCase();
Serial.begin(9600);
Serial.println(mensagem); // Saída: olá, mundo!
```

## Mergulho Profundo:
Converter strings para minúsculas é uma prática comum desde os primórdios da computação, pois as comparações de texto são sensíveis a maiúsculas e minúsculas por padrão. Alternativas incluem o uso de funções como `strcasecmp()` para comparações insensíveis a maiúsculas/minúsculas, mas para normalizar dados (como entradas de usuário) a conversão para minúsculas é uma operação padrão. Na implementação do método `toLowerCase()` do Arduino, cada caractere da string é verificado e se estiver no intervalo ASCII de letras maiúsculas (65 a 90), é convertido para o respectivo minúsculo adicionando 32 a seu código ASCII.

## Ver Também:
- Documentação oficial da Arduino: https://www.arduino.cc/reference/pt/language/variables/data-types/string/functions/tolowercase/
- Tutorial sobre comparação de strings no Arduino: https://www.arduino.cc/en/Tutorial/BuiltInExamples/StringComparisonOperators
