---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:10:19.695808-07:00
description: "Recuperar a data atual na programa\xE7\xE3o \xE9 uma tarefa crucial\
  \ para uma infinidade de aplica\xE7\xF5es, incluindo registro de atividades (logging),\
  \ marca\xE7\xE3o de\u2026"
lastmod: '2024-03-13T22:44:46.719540-06:00'
model: gpt-4-0125-preview
summary: "Recuperar a data atual na programa\xE7\xE3o \xE9 uma tarefa crucial para\
  \ uma infinidade de aplica\xE7\xF5es, incluindo registro de atividades (logging),\
  \ marca\xE7\xE3o de eventos com carimbo de data/hora ou agendamento de tarefas."
title: Obtendo a data atual
weight: 29
---

## Como fazer:
O Lua fornece a função `os.date` para obter a data e a hora atuais. A função pode ser usada sem argumentos para obter uma string formatada ou com especificadores de formato para personalizar a saída. Veja como usá-la:

```lua
-- Obtendo a data e hora atuais como uma string formatada
print(os.date())  -- ex., Qui Mar  3 14:02:03 2022

-- Personalizando o formato de saída
-- %Y para ano, %m para mês, %d para dia, %H para hora, %M para minutos
print(os.date("%Y-%m-%d %H:%M"))  -- ex., 2022-03-03 14:02
```

Para manipulações mais sofisticadas de data e hora, o Lua não possui bibliotecas internas tão ricas quanto algumas outras linguagens de programação. No entanto, você pode usar bibliotecas de terceiros, como `lua-date` (https://github.com/Tieske/date). Esta biblioteca oferece funcionalidades mais abrangentes para manipular datas e horários. Veja como você pode usá-la:

Primeiro, certifique-se de ter instalado a biblioteca `lua-date`. Geralmente, você pode instalá-la usando o LuaRocks com o seguinte comando:

```bash
luarocks install lua-date
```

Então, você pode usá-la em seu script Lua assim:

```lua
local date = require("date")

-- Criando um objeto de data para a data e hora atuais
local agora = date()

print(agora:fmt("%Y-%m-%d %H:%M:%S"))  -- ex., 2022-03-03 14:02:03
```

Este exemplo demonstra a criação de um objeto `date` representando o momento atual, o qual você pode então formatar de maneira similar à função `os.date`, mas com flexibilidade e opções adicionais fornecidas pela biblioteca `lua-date`.
