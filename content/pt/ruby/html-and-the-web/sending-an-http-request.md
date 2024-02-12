---
title:                "Enviando uma requisição HTTP"
aliases:
- /pt/ruby/sending-an-http-request/
date:                  2024-01-20T18:00:20.331192-07:00
model:                 gpt-4-1106-preview
simple_title:         "Enviando uma requisição HTTP"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/ruby/sending-an-http-request.md"
---

{{< edit_this_page >}}

## O Que é & Porquê?
Enviar uma requisição HTTP é o ato de pedir informações a um servidor web. Programadores fazem isso para interagir com APIs, solicitar dados, ou submeter informações.

## Como fazer:
Ruby é pura conveniência quando se trata de enviar requisições HTTP. Você pode usar a biblioteca `net/http` padrão ou, para algo mais avançado, `httparty`. Aqui está um exemplo básico:

```ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com/users')
response = Net::HTTP.get_response(uri)
puts response.body if response.is_a?(Net::HTTPSuccess)
```

E a saída seria o HTML ou JSON (ou qualquer outro tipo de conteúdo) que o servidor responder.

Com `httparty`, o código fica ainda mais simples:

```ruby
require 'httparty'

response = HTTParty.get('http://example.com/users')
puts response.body if response.code == 200
```

## Mergulho Profundo:
Enviar requisições HTTP é essencial desde os primórdios da web. Antes do Ruby existir, essa tarefa era feita em outras linguagens como Perl ou C. Ruby facilitou a vida com bibliotecas que abstraem os detalhes.

Além do `net/http` e do `httparty`, tem outras opções como `Faraday` e `RestClient`. Cada uma tem suas vantagens. O `Faraday`, por exemplo, oferece um middleware que permite customizações profundas. Já o `RestClient` é conhecido pela sua simplicidade e uso direto.

Detalhes importantes na implementação incluem a gestão de estados de resposta HTTP, codificação de parâmetros de URL, e tratamento de timeouts e exceções.

## Veja Também:
- Documentação do `net/http`: https://ruby-doc.org/stdlib-3.0.0/libdoc/net/http/rdoc/Net/HTTP.html
- GitHub do `httparty`: https://github.com/jnunemaker/httparty
- Documentação do `Faraday`: https://lostisland.github.io/faraday/
- Documentação do `RestClient`: https://github.com/rest-client/rest-client
