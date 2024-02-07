---
title:                "Organizando o código em funções"
date:                  2024-01-26T01:09:04.694547-07:00
model:                 gpt-4-1106-preview
simple_title:         "Organizando o código em funções"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/bash/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## O Quê & Porquê?
Dividir código em funções significa decompor scripts em blocos menores e reutilizáveis que realizam tarefas específicas. Isso torna o código mais limpo, mais compreensível e mais fácil de depurar.

## Como fazer:
Crie uma função simples em Bash:

```Bash
greet() {
  echo "Olá, $1!"
}
```

Use-a chamando a função com um parâmetro:

```Bash
greet "Mundo"  # Saída: Olá, Mundo!
```

Funções podem retornar valores usando `return` para códigos de status numéricos (não para retorno de dados reais):

```Bash
add() {
  return $(($1 + $2))
}

add 3 4
echo $?  # Saída: 7
```

Note que `$?` captura o valor de retorno do último comando, que é o resultado numérico de `add`.

## Aprofundamento
No Bash, funções têm sido uma forma de compartimentar código desde as primeiras versões. Historicamente, o uso de funções está alinhado com princípios de programação estruturada introduzidos nos anos 1960 para melhorar a qualidade do código.

Alternativas às funções incluem a importação de arquivos de script ou o uso de aliases, mas esses não oferecem o mesmo nível de modularidade e reutilização.

Um detalhe de implementação notável no Bash é que funções são cidadãos de primeira classe; elas não têm uma palavra-chave de declaração específica como `function` em outras linguagens, embora `function` seja opcional no Bash para legibilidade. O escopo da função também é interessante — variáveis são globais por padrão, a menos que declaradas como locais, o que pode levar a comportamentos inesperados, se não gerenciados adequadamente.

## Veja Também
- Manual do Bash sobre Funções do Shell: https://www.gnu.org/software/bash/manual/html_node/Shell-Functions.html
- Guia de Scripting Avançado em Bash: https://tldp.org/LDP/abs/html/functions.html
- "Pro Bash Programming: Scripting the GNU/Linux Shell" para conceitos de script de função aprofundados e práticas.
