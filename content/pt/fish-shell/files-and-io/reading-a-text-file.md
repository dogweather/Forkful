---
title:                "Lendo um arquivo de texto"
aliases:
- pt/fish-shell/reading-a-text-file.md
date:                  2024-01-20T17:54:14.153382-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lendo um arquivo de texto"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/fish-shell/reading-a-text-file.md"
---

{{< edit_this_page >}}

## O Quê & Por Quê?
Ler um arquivo de texto é acessar o conteúdo de um arquivo no formato de texto simples. Programadores fazem isso para processamento, análise de dados e automação de tarefas.

## Como fazer:
```Fish Shell
# Ler todo o conteúdo do arquivo
cat arquivo.txt

# Ler linha por linha
while read -la linha
    echo $linha
end < arquivo.txt
```
Exemplo de saída para o comando `cat`:
```
Olá, mundo!
Este é conteúdo do meu arquivo de texto.
```

Exemplo de saída para o loop `while`:
```
Olá, mundo!
Este é conteúdo do meu arquivo de texto.
```

## Mergulho Profundo
Ler arquivos de texto é uma operação de I/O básica, que data dos primeiros dias da computação moderna. Alternativas no Fish incluem o uso de comandos como `cat`, `less`, `more` ou a manipulação de fluxo de dados com `while read` para maior controle. Internamente, essas operações se utilizam de syscalls para interagir com o sistema de arquivos do sistema operacional. A eficiência pode variar dependendo do tamanho do arquivo e do método utilizado, já que ler um arquivo inteiro de uma vez pode consumir bastante memória.

## Veja Também
- Documentação oficial do Fish Shell: [https://fishshell.com/docs/current/index.html](https://fishshell.com/docs/current/index.html)
- Tutorial sobre manipulação de arquivos de texto no Unix: [https://www.tutorialspoint.com/unix/unix-file-management.htm](https://www.tutorialspoint.com/unix/unix-file-management.htm)
