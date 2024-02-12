---
title:                "Criando um arquivo temporário"
aliases:
- pt/kotlin/creating-a-temporary-file.md
date:                  2024-01-20T17:40:37.450159-07:00
model:                 gpt-4-1106-preview
simple_title:         "Criando um arquivo temporário"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/kotlin/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## O Que & Por Quê?

Criar um arquivo temporário é o processo de gerar um arquivo que só é necessário durante a execução temporária de um programa. Os programadores fazem isso para não encher o sistema com dados desnecessários permanentemente, manejar arquivos grandes com segurança ou manter dados sensíveis que não devem ser armazenados a longo prazo.

## Como Fazer:

Para criar um arquivo temporário em Kotlin, podemos usar a biblioteca padrão do Java. O código abaixo mostra como fazer isso:

```Kotlin
import java.io.File

fun main() {
    val tempFile = File.createTempFile("meuArquivoTemp", ".tmp").apply {
        deleteOnExit() // O arquivo será deletado quando a JVM terminar
    }
    
    println("Arquivo temporário criado em: ${tempFile.absolutePath}")
    // Escreva dados no arquivo
    tempFile.writeText("Exemplo de conteúdo temporário")

    // Lendo o conteúdo
    val conteudo = tempFile.readText()
    println("Conteúdo do arquivo: $conteudo")
}
```

Saída de exemplo:
```
Arquivo temporário criado em: C:\...\meuArquivoTemp1234567890.tmp
Conteúdo do arquivo: Exemplo de conteúdo temporário
```

## Aprofundando

A criação de arquivos temporários remonta aos primórdios dos sistemas operacionais para manipular dados que só são necessários durante um cálculo ou processo específico. Alternativas incluem armazenamento em memória, mas para grandes quantidades de dados ou para preservar a integridade durante falhas do sistema, arquivos temporários são preferíveis. Em Kotlin, utiliza-se a biblioteca do Java para manipular arquivos temporários, pois Kotlin roda na JVM e tem interoperabilidade total com Java. Importante notar que é responsabilidade do desenvolvedor apagar esses arquivos temporários após o uso, algo que `deleteOnExit()` faz automaticamente ao final da execução da JVM.

## Veja Também

- Guia da API do Java para a classe `File`: [Java 11 `File` API Guide](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/io/File.html)
- Discussão no Stack Overflow sobre a criação de arquivos temporários: [Stack Overflow Discussion](https://stackoverflow.com/questions/16691437/how-to-create-a-temporary-directory-folder-in-java)
