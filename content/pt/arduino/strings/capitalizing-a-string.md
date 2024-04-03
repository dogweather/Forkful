---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:04:55.868709-07:00
description: "Capitalizar uma string envolve converter o primeiro caractere de cada\
  \ palavra em uma string para mai\xFAscula enquanto garante que o restante permane\xE7\
  a em\u2026"
lastmod: '2024-03-13T22:44:46.822448-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar uma string envolve converter o primeiro caractere de cada palavra\
  \ em uma string para mai\xFAscula enquanto garante que o restante permane\xE7a em\
  \ min\xFAsculas."
title: Capitalizando uma string
weight: 2
---

## Como fazer:
O Arduino, conhecido principalmente por interagir com hardware, também inclui capacidades básicas de manipulação de strings através do seu objeto `String`. No entanto, ele não possui uma função direta de `capitalizar` como vista em linguagens de nível mais alto. Assim, implementamos a capitalização iterando sobre uma string e aplicando transformações de maiúsculas e minúsculas.

Aqui está um exemplo básico sem usar bibliotecas de terceiros:

```cpp
String capitalizeString(String input) {
  if (input.length() == 0) {
    return ""; // Retorna uma string vazia se a entrada estiver vazia
  }
  input.toLowerCase(); // Converte a string inteira para minúscula primeiro
  input.setCharAt(0, input.charAt(0) - 32); // Capitaliza o primeiro caractere
  
  // Capitaliza letras que seguem um espaço
  for (int i = 1; i < input.length(); i++) {
    if (input.charAt(i - 1) == ' ') {
      input.setCharAt(i, input.charAt(i) - 32);
    }
  }
  return input;
}

void setup() {
  Serial.begin(9600);
  String testStr = "hello arduino world";
  String capitalizedStr = capitalizeString(testStr);
  Serial.println(capitalizedStr); // Saída: "Hello Arduino World"
}

void loop() {
  // Loop vazio
}
```

Este trecho de código define uma função `capitalizeString` que primeiro converte toda a string para minúscula para padronizar seu caso. Em seguida, capitaliza o primeiro caractere e qualquer caractere que siga um espaço, efetivamente capitalizando cada palavra na string de entrada. Note que esta implementação rudimentar assume a codificação de caracteres ASCII e pode precisar de ajustes para suporte completo ao Unicode.

Atualmente, não há bibliotecas de terceiros amplamente adotadas especificamente para manipulação de strings no ecossistema Arduino, principalmente devido ao seu foco na interação com hardware e eficiência. No entanto, o exemplo fornecido é uma maneira direta de alcançar a capitalização de strings dentro do ambiente de programação do Arduino.
