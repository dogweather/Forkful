---
title:                "Baixando uma página da web"
date:                  2024-01-20T17:44:39.229205-07:00
model:                 gpt-4-1106-preview
simple_title:         "Baixando uma página da web"
programming_language: "Lua"
category:             "Lua"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/lua/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Baixar uma página da web significa capturar o conteúdo de uma página da internet e salvá-lo localmente. Programadores fazem isso para análise, monitoramento, ou para extrair dados.

## Como Fazer:
Vamos usar o LuaSocket, uma biblioteca Lua para redes. Para instalar, use `luarocks install luasocket`.

```Lua
local http = require("socket.http")
local url = "http://www.example.com"

-- Baixa o conteúdo da URL
local body, statusCode, headers, statusText = http.request(url)

if statusCode == 200 then
    print("Conteúdo baixado com sucesso!")
    print(body)
else
    print("Falha ao baixar conteúdo: " .. statusText)
end
```

Isso deve resultar em:
```
Conteúdo baixado com sucesso!
<html>...
```

## Mergulho Profundo:
Lua não inclui funcionalidades de rede no núcleo da linguagem. Por isso, o LuaSocket é essencial. Ele existe desde os anos 2000, ajudando a Lua em operações de rede. Alternativas incluem as bibliotecas "Lua-cURL" e "HTTP Client for Lua". Ao baixar uma página, o LuaSocket faz uma requisição HTTP, aguarda a resposta, e então lida com a resposta - seja ela uma página web real ou uma mensagem de erro.

## Veja Também:
- LuaSocket: http://w3.impa.br/~diego/software/luasocket/
- GitHub Lua-cURL: https://github.com/Lua-cURL/Lua-cURL
- Documentação Lua 5.4 (versão atual): https://www.lua.org/manual/5.4/
