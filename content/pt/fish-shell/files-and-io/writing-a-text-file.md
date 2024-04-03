---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:27:47.596780-07:00
description: "Escrever em um arquivo de texto no Fish Shell permite armazenar dados\
  \ de forma persistente, facilitando a recupera\xE7\xE3o ou manipula\xE7\xE3o de\
  \ dados tanto pelo\u2026"
lastmod: '2024-03-13T22:44:47.024001-06:00'
model: gpt-4-0125-preview
summary: "Escrever em um arquivo de texto no Fish Shell permite armazenar dados de\
  \ forma persistente, facilitando a recupera\xE7\xE3o ou manipula\xE7\xE3o de dados\
  \ tanto pelo mesmo script Fish quanto por outros programas."
title: Escrevendo um arquivo de texto
weight: 24
---

## Como fazer:
Para escrever em um arquivo de texto no Fish, você pode usar o comando `echo` combinado com operadores de redirecionamento. Não existem bibliotecas de terceiros populares especificamente para escrita de arquivos no Fish, pois os comandos internos do shell são diretos e eficientes para esse propósito.

### Escrevendo texto em um arquivo novo ou sobrescrevendo um arquivo existente:
```fish
echo "Olá, Fish Shell!" > output.txt
```
Este comando escreve "Olá, Fish Shell!" em `output.txt`, criando o arquivo se ele não existir ou sobrescrevendo-o se ele existir.

### Acrescentando texto a um arquivo existente:
Se você deseja adicionar texto ao final de um arquivo existente sem remover o conteúdo atual, use o operador de anexar `>>`:
```fish
echo "Adicionando nova linha ao arquivo." >> output.txt
```

### Escrevendo várias linhas:
Você pode escrever várias linhas em um arquivo usando o echo com um caractere de nova linha `\n`, ou você pode encadear múltiplos comandos echo usando ponto e vírgula:
```fish
echo "Primeira Linha\nSegunda Linha" > output.txt
# OU
echo "Primeira Linha" > output.txt; echo "Segunda Linha" >> output.txt
```

### Saída de amostra:
Para visualizar o conteúdo de `output.txt` após a execução dos comandos acima, use o comando `cat`:
```fish
cat output.txt
```
```plaintext
Primeira Linha
Segunda Linha
```
Substituir ou acrescentar textos conforme mostrado manipula o conteúdo do arquivo conforme suas necessidades, demonstrando maneiras simples, porém poderosas, de trabalhar com arquivos de texto no Fish Shell.
