---
aliases:
- /pt/java/creating-a-temporary-file/
date: 2024-01-20 17:40:33.379451-07:00
description: "Criar um arquivo tempor\xE1rio permite armazenar dados que s\xF3 s\xE3\
  o necess\xE1rios durante a execu\xE7\xE3o de um programa. Programadores fazem isso\
  \ para economizar\u2026"
lastmod: 2024-02-18 23:08:58.038036
model: gpt-4-1106-preview
summary: "Criar um arquivo tempor\xE1rio permite armazenar dados que s\xF3 s\xE3o\
  \ necess\xE1rios durante a execu\xE7\xE3o de um programa. Programadores fazem isso\
  \ para economizar\u2026"
title: "Criando um arquivo tempor\xE1rio"
---

{{< edit_this_page >}}

## O Que & Porquê?
Criar um arquivo temporário permite armazenar dados que só são necessários durante a execução de um programa. Programadores fazem isso para economizar memória, gerenciar cache, testar código ou lidar com dados que não precisam ser salvos permanentemente.

## Como Fazer:
```java
import java.io.File;
import java.io.IOException;

public class ArquivoTemporario {
    public static void main(String[] args) {
        try {
            // Criando um arquivo temporário
            File tempFile = File.createTempFile("meuArquivoTemp", ".txt");

            // Escreva seu código aqui para usar o arquivo

            // Deletando o arquivo temporário ao terminar
            tempFile.deleteOnExit();
            
            System.out.println("Arquivo temporário criado em: " + tempFile.getAbsolutePath());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
Output:
```
Arquivo temporário criado em: C:\Users\usuario\AppData\Local\Temp\meuArquivoTemp1234567890.txt
```

## Aprofundamento
Arquivos temporários são um conceito antigo, existente desde os primórdios dos sistemas operacionais para lidar com armazenamento limitado e segurança de dados. Alternativas incluem usar bancos de dados em memória ou estruturas de dados persistentes. Ao criar um arquivo temporário em Java, você pode especificar um prefixo e sufixo para o nome do arquivo, mas o local é muitas vezes gerenciado pelo sistema operacional. O método `deleteOnExit()` é útil, mas cuidado: se o programa encerrar abruptamente, o arquivo pode não ser excluído.

## Veja Também
- [Documentação da Classe File](https://docs.oracle.com/en/java/javase/18/docs/api/java.base/java/io/File.html)
- [Guia sobre a API de I/O do Java](https://docs.oracle.com/javase/tutorial/essential/io/)
- [Artigo sobre o gerenciamento de recursos em Java com try-with-resources](https://www.baeldung.com/java-try-with-resources)
