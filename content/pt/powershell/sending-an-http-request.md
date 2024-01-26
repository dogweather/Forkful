---
title:                "Enviando uma requisição HTTP"
date:                  2024-01-20T18:00:32.571971-07:00
model:                 gpt-4-1106-preview
simple_title:         "Enviando uma requisição HTTP"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/powershell/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why?
Enviar uma requisição HTTP significa pedir informações a um servidor web. Programadores fazem isso para interagir com APIs, buscar dados e comunicar-se com outros serviços pela internet.

## How to:
Vamos usar o comando `Invoke-RestMethod` para enviar uma requisição GET simples:

```PowerShell
$response = Invoke-RestMethod -Uri 'http://api.exemplo.com/dados' -Method Get
Write-Output $response
```

Para enviar uma requisição POST com corpo JSON, faríamos:

```PowerShell
$body = @{
    chave = 'valor'
    outro = 'dado'
} | ConvertTo-Json

$response = Invoke-RestMethod -Uri 'http://api.exemplo.com/envio' -Method Post -Body $body -ContentType 'application/json'
Write-Output $response
```

## Deep Dive
O `Invoke-RestMethod` é um cmdlet disponível no PowerShell que simplifica o envio de requisições HTTP. Ele foi introduzido no PowerShell 3.0 e se tornou uma ferramenta principal para interações web. Alternativas incluem `Invoke-WebRequest`, mas este é mais verboso para trabalhar com APIs RESTful, uma vez que retorna mais dados e cabeçalhos de resposta. Em comparação, o `Invoke-RestMethod` retorna diretamente o conteúdo da resposta, frequentemente em um objeto PowerShell.

Numa requisição POST, comumente usa-se `ConvertTo-Json` para formatar corretamente o corpo da mensagem. A requisição será enviada com o header 'Content-Type' configurado para 'application/json' para que o servidor saiba como processar o corpo da mensagem.

Lembrando que você precisa lidar com autenticação, timeouts, e outros aspectos de uma conexão HTTP que podem ser configurados através de parâmetros adicionais do cmdlet.

## See Also
- [Documentação oficial do Invoke-RestMethod](https://docs.microsoft.com/pt-br/powershell/module/microsoft.powershell.utility/invoke-restmethod)
