---
title:                "Concatenando strings"
date:                  2024-01-20T17:35:22.020836-07:00
model:                 gpt-4-1106-preview
simple_title:         "Concatenando strings"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/lua/concatenating-strings.md"
---

{{< edit_this_page >}}

## O Que é & Porquê?
Concatenar strings é basicamente juntar textos diferentes em um só. Programadores fazem isso para construir mensagens, caminhos de arquivos, e sempre que precisam combinar palavras e frases de forma dinâmica.

## Como Fazer:
No Lua, concatenamos strings usando o operador `..`. É direto assim:

```lua
local saudacao = "Olá, "
local nome = "Maria"
local mensagem = saudacao .. nome
print(mensagem)  -- Saída: Olá, Maria
```

Quer incluir números? Converte para string primeiro:

```lua
local base = "Você tem "
local quantidade = 3
local objeto = " mensagens."
local mensagemCompleta = base .. tostring(quantidade) .. objeto
print(mensagemCompleta)  -- Saída: Você tem 3 mensagens.
```
  
Use com cuidado, não exagere na quantidade de operações numa linha só. Isso pode complicar a leitura do código.

## Imersão:
A concatenação de strings existe desde os primórdios da programação. No Lua, o operador `..` é bem direto e serve apenas a esse propósito. Há linguagens em que a sobrecarga de operadores permite que o mesmo símbolo (+, por exemplo) faça operações matemáticas e de concatenação. No Lua, não; simplicidade é chave.

Alternativas de concatenação incluem a função `table.concat`, que é útil quando você tem uma série de strings em uma tabela e quer juntar tudo:

```lua
local pedacos = {"Lua", " é", " incrível!"}
local frase = table.concat(pedacos)
print(frase)  -- Saída: Lua é incrível!
```

Quanto à implementação, o Lua otimiza a concatenação de strings internamente, então é bastante eficiente, mas abusar da concatenação em loops intensivos pode degradar a performance. Por isso, `table.concat` pode ser uma alternativa mais eficaz nesses casos.

## Veja Também:
- [Tutorial de Lua](http://www.lua.org/pil/contents.html)
