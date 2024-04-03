---
date: 2024-01-20 17:47:17.968040-07:00
description: "Encontrar o comprimento de uma string significa descobrir quantos caracteres\
  \ ela possui. Programadores fazem isso para validar entradas, manipular texto e\u2026"
lastmod: '2024-03-13T22:44:46.188143-06:00'
model: gpt-4-1106-preview
summary: Encontrar o comprimento de uma string significa descobrir quantos caracteres
  ela possui.
title: Descobrindo o comprimento de uma string
weight: 7
---

## Como Fazer:
```Clojure
;; Para descobrir o comprimento de uma string, use a função count:
(count "Olá, mundo!")
;; Saída esperada: 11

;; Você também pode usar a função .length de Java:
(.length "Olá, mundo!")
;; Saída esperada: 11
```

## Aprofundando
Historicamente, Clojure, sendo uma linguagem hospedada na JVM (Java Virtual Machine), tira proveito das funcionalidades do Java. Por isso, além de usar `count`, uma função genérica para contar coleções, você pode acessar o método `.length` específico para strings do Java. Como alternativa, algumas pessoas podem preferir usar `count` para consistência e para aproveitar melhor a abstração das collections do Clojure.

Devemos lembrar que, como o Clojure lida com dados imutáveis, a operação de contagem é segura e previsível - uma vez que a string não pode mudar durante a operação. Sob o capô, `count` é otimizado para ser uma operação rápida, de tempo constante (`O(1)`) para strings, porque a JVM mantém um registro do comprimento da string, o que evita ter que contar cada caractere toda vez.

Por fim, é raro, mas em contextos de internacionalização (i18n), o conceito de "comprimento" de uma string pode ser mais complexo, especialmente em scripts que usam composições de caracteres, como alguns sistemas de escrita asiáticos. Para a maioria dos propósitos, entretanto, as operações padrão do Clojure e Java lidam bem com isso.

## Veja Também
- Documentação oficial da Clojure: [clojure.org](https://clojure.org/)
- Guia para a função `count` do Clojure: [ClojureDocs - count](https://clojuredocs.org/clojure.core/count)
- Referência Java para o método `.length`: [Java String length() Method](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#length())
