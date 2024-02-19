---
aliases:
- /pt/fish-shell/converting-a-string-to-lower-case/
date: 2024-01-20 17:38:21.467700-07:00
description: "Converter uma string para min\xFAsculas \xE9 o processo de transformar\
  \ todos os caracteres alfab\xE9ticos em um texto para sua variante em caixa baixa.\u2026"
lastmod: 2024-02-18 23:08:58.561003
model: gpt-4-1106-preview
summary: "Converter uma string para min\xFAsculas \xE9 o processo de transformar todos\
  \ os caracteres alfab\xE9ticos em um texto para sua variante em caixa baixa.\u2026"
title: "Convertendo uma string para min\xFAsculas"
---

{{< edit_this_page >}}

## What & Why?
Converter uma string para minúsculas é o processo de transformar todos os caracteres alfabéticos em um texto para sua variante em caixa baixa. Programadores fazem isso para padronizar dados, facilitar comparações de strings, ou atender requisitos específicos de sistemas que diferenciam maiúsculas e minúsculas.

## How to:
No Fish Shell, usar a função `string` com a opção `lower` faz o truque. Aqui está como:

```Fish Shell
echo 'AbacaxI é VIDA!' | string lower
```

Resultado:
```
abacaxi é vida!
```

E se você já tem a string em uma variável:

```Fish Shell
set frase 'PeIXE é o MELhor Shell'
string lower -a -- $frase
```

Resultado:
```
peixe é o melhor shell
```

## Deep Dive
Lá nos primórdios da computação, caracteres eram armazenados de formas diferentes, dependendo do sistema. A uniformização ajuda a evitar erros, principalmente em sistemas Unix-Like, onde `Arquivo.txt` e `arquivo.txt` são considerados diferentes. O Fish Shell, focado em ser prático e moderno, adicionou a função `string` diretamente embutida no shell. Antes disso, ou em outros shells como Bash, teríamos que recorrer a comandos externos como `tr '[:upper:]' '[:lower:]'` ou usar funcionalidades das próprias linguagens de programação. Sob o capô, a conversão para minúsculas no Fish lida com a complexidade do Unicode, garantindo que até mesmo caracteres fora do básico ASCII sejam transformados corretamente.

## See Also
Para mais informações, os links seguintes são bastante úteis:

- Documentação oficial do comando `string`: [fishshell.com/docs/current/cmds/string.html](https://fishshell.com/docs/current/cmds/string.html)
- Discussão sobre manipulação de strings no Fish Shell: [github.com/fish-shell/fish-shell/issues/159](https://github.com/fish-shell/fish-shell/issues/159)

Lembrando que a prática leva à perfeição. Então vá em frente, experimente converter algumas strings e veja o poder do Fish Shell em ação.
