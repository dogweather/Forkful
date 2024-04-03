---
date: 2024-01-26 00:54:13.994961-07:00
description: "Tratar erros significa escrever c\xF3digo que antecipa e lida com as\
  \ coisas dando errado. Programadores fazem isso para tornar o software robusto,\
  \ evitando\u2026"
lastmod: '2024-03-13T22:44:46.463361-06:00'
model: gpt-4-1106-preview
summary: "Tratar erros significa escrever c\xF3digo que antecipa e lida com as coisas\
  \ dando errado."
title: Tratamento de erros
weight: 16
---

## Como Fazer:
Java usa exceções para tratar erros. Você envolve o código de risco com um bloco `try` e captura exceções com `catch`. Aqui está um exemplo simples:

```java
public class ExemploTratamentoDeErro {
    public static void main(String[] args) {
        try {
            int resultado = dividir(10, 0);
            System.out.println("O resultado é: " + resultado);
        } catch (ArithmeticException e) {
            System.out.println("Ops, não é possível dividir por zero!");
        }
    }

    private static int dividir(int numerador, int denominador) {
        return numerador / denominador;
    }
}
```

Saída:
```
Ops, não é possível dividir por zero!
```

## Aprofundamento
O tratamento de erros em Java evoluiu. Nos primeiros dias, não havia exceções; programadores verificavam códigos de erro. Depois, o Java introduziu blocos try-catch, permitindo um tratamento de erros mais elegante.

Alternativas ao `try-catch` tradicional incluem `try-with-resources` para fechamento automático de recursos e um código mais limpo, introduzido no Java 7.

Detalhes da implementação importam. Por exemplo, capturar `Exception` ou `Throwable` geralmente é uma má prática. É muito amplo e pode mascarar bugs dos quais você pode não estar ciente. Prefira exceções específicas.

## Veja Também
- Os tutoriais oficiais da Oracle sobre exceções em Java: [https://docs.oracle.com/javase/tutorial/essential/exceptions/](https://docs.oracle.com/javase/tutorial/essential/exceptions/)
- Documentação da declaração `try-with-resources` do Java: [https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html)
- Effective Java de Joshua Bloch, para as melhores práticas sobre exceções.
