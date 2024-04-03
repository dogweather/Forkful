---
date: 2024-01-20 17:57:10.180624-07:00
description: "Procurar e substituir texto \xE9 um processo b\xE1sico para trocar uma\
  \ sequ\xEAncia de caracteres por outra num bloco de texto. Programadores fazem isso\
  \ para\u2026"
lastmod: '2024-03-13T22:44:46.824359-06:00'
model: gpt-4-1106-preview
summary: "Procurar e substituir texto \xE9 um processo b\xE1sico para trocar uma sequ\xEA\
  ncia de caracteres por outra num bloco de texto."
title: Pesquisando e substituindo texto
weight: 10
---

## Como Fazer:
```Arduino
String original = "Folha de Flandres";
String substituido = original.replace("Flandres", "Bananeira");
Serial.begin(9600);
Serial.println(substituido);
```
Saída esperada:
```
Folha de Bananeira
```

## Mergulho Profundo:
Procurar e substituir texto é uma necessidade antiga - pense em editores de texto dos anos 60 que já tinham essa função. No mundo do Arduino, essa necessidade surge quando lidamos com strings - para, por exemplo, adaptar mensagens de LCDs. Embora o exemplo acima use o método `replace` de `String`, há alternativas mais rápidas e com menor uso de memória como o uso de `char` arrays e funções como `strncpy` e `strstr`. A escolha do método depende do tamanho do texto e das restrições de memória do microcontrolador.

## Veja Também:
- Documentação oficial do Arduino sobre strings: https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/
- Tutorial sobre manipulação de strings no Arduino: https://www.arduino.cc/en/Tutorial/BuiltInExamples/StringReplace
- Discussões no Arduino Forum sobre substituição de texto: https://forum.arduino.cc/
