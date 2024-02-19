---
aliases:
- /pt/fish-shell/logging/
date: 2024-01-26 01:03:41.839293-07:00
description: "Registrar (logging) \xE9, essencialmente, anotar o que seu aplicativo\
  \ est\xE1 fazendo \u2014 um di\xE1rio, por assim dizer, mas para o c\xF3digo. Os\
  \ programadores fazem\u2026"
lastmod: 2024-02-18 23:08:58.582090
model: gpt-4-1106-preview
summary: "Registrar (logging) \xE9, essencialmente, anotar o que seu aplicativo est\xE1\
  \ fazendo \u2014 um di\xE1rio, por assim dizer, mas para o c\xF3digo. Os programadores\
  \ fazem\u2026"
title: Registro de Logs
---

{{< edit_this_page >}}

## O que & Por quê?
Registrar (logging) é, essencialmente, anotar o que seu aplicativo está fazendo — um diário, por assim dizer, mas para o código. Os programadores fazem isso para acompanhar os detalhes, como mudanças de estado, eventos do sistema e bugs irritantes, garantindo que nenhum contratempo passe despercebido.

## Como fazer:
No Fish, registrar pode ser tão simples quanto redirecionar as saídas padrão e de erro para um arquivo. Vamos criar uma entrada de registro para os horários de início e término do nosso script.

```fish
function log_start
  echo (date "+%Y-%m-%d %H:%M:%S") " - Script iniciado" >> my_app.log
end

function log_end
  echo (date "+%Y-%m-%d %H:%M:%S") " - Script finalizado" >> my_app.log
end

log_start
# ... as tarefas do seu script ...
log_end

cat my_app.log
```

Aqui está o que você veria em `my_app.log`:

```
2023-04-01 10:35:47  - Script iniciado
2023-04-01 10:36:02  - Script finalizado
```

Para um registro avançado, você pode utilizar funções com parâmetros para o nível de registro e mensagens:

```fish
function log_message --argument message
  switch "$argv[1]"
    case 'INFO' 'WARN' 'ERROR'
      set log_level $argv[1]
    case '*'
      set log_level 'DEBUG'
  end
  set log_msg (string join " " $argv[2..-1])
  echo (date "+%Y-%m-%d %H:%M:%S") "[$log_level]" $log_msg >> my_app.log
end

log_message INFO "Esta é uma mensagem informativa."
log_message ERROR "Algo deu errado!"
```

Exemplo de saída no `my_app.log` será:
```
2023-04-01 10:35:47 [INFO] Esta é uma mensagem informativa.
2023-04-01 10:35:49 [ERROR] Algo deu errado!
```

## Aprofundando
Historicamente, o registro em scripts de shell era feito com uma série de comandos `echo`, e embora isso ainda seja certamente uma opção, implementar sistemas mais complexos pode ser um desafio. O Fish não possui um mecanismo de registro integrado como algumas outras shells ou linguagens de programação, então muitas vezes você precisa criar o seu próprio.

Alternativas para o comando `echo` integrado do Fish para registro incluem ferramentas Unix como `syslog` ou `logger`, que interagem com o daemon de log do sistema, fornecendo uma abordagem mais integrada para registrar eventos em todo o sistema.

A simplicidade do Fish permite que você crie funções para lidar com a verbosidade do registro, definindo diferentes níveis que você pode ligar ou desligar. Algumas implementações podem até incluir o nome do script, número da linha e carimbo de data/hora, o que facilita rastrear os passos que levaram a um evento.

## Veja Também
- A documentação do Fish Shell sobre escrita de funções: https://fishshell.com/docs/current/#syntax-function
- Dicas Básicas de Scripting em Shell: https://developer.ibm.com/tutorials/l-lpic1-103-4/
- Guia para o Protocolo Syslog: https://tools.ietf.org/html/rfc5424
