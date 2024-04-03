---
date: 2024-01-26 03:39:54.009709-07:00
description: "Remover aspas de uma string significa eliminar quaisquer marcas de cita\xE7\
  \xE3o\u2014simples (' '), duplas (\" \") ou ambas\u2014dos dados de texto. Programadores\
  \ fazem\u2026"
lastmod: '2024-03-13T22:44:46.444544-06:00'
model: gpt-4-0125-preview
summary: "Remover aspas de uma string significa eliminar quaisquer marcas de cita\xE7\
  \xE3o\u2014simples (' '), duplas (\" \") ou ambas\u2014dos dados de texto."
title: Removendo aspas de uma string
weight: 9
---

## Como fazer:
Vamos arrancar essas aspas chatas do nosso texto. Usaremos o método `replace()` para os consertos rápidos e regex para os casos mais complicados.

```java
public class RemovedorDeAspas {
    public static void main(String[] args) {
        String stringWithQuotes = "\"Olá, 'Mundo'!\"";
        String withoutQuotes = stringWithQuotes.replace("\"", "").replace("'", "");
        System.out.println(withoutQuotes); // Olá, Mundo!

        // Agora com regex para os aficionados por padrões
        String stringWithMixedQuotes = "\"Java\" e 'Programação'";
        String cleanString = stringWithMixedQuotes.replaceAll("[\"']", "");
        System.out.println(cleanString); // Java e Programação
    }
}
```

## Aprofundamento
Antigamente, aspas em strings não eram um grande problema—os sistemas eram mais simples, e os dados não eram tão bagunçados. Com o advento de formatos de dados complexos (JSON, XML) e a necessidade de troca de dados, o gerenciamento de aspas tornou-se chave. Falando em alternativas, claro, você poderia escrever um analisador, percorrer cada caractere e construir uma nova string (poderia ser divertido em um dia chuvoso). Há também bibliotecas de terceiros que podem lidar com isso com mais sofisticação, oferecendo opções para escapar caracteres em vez de removê-los, ou para lidar com diferentes tipos de aspas de acordo com a localidade. Quanto à implementação, tenha em mente que remover aspas sem contexto pode alterar o significado ou a estrutura dos dados—sempre considere o "porquê" antes do "como".

## Veja Também
- Para se aprofundar em regex, confira os documentos oficiais do Java: https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html
- Precisa escapar aspas em vez de removê-las? O Stack Overflow pode ajudar: https://stackoverflow.com/questions/383551/escape-string-for-sql-insert
- Processamento de JSON em Java? Provavelmente você encontrará aspas com frequência. Aqui está um ponto de partida: https://www.oracle.com/technical-resources/articles/java/json.html
