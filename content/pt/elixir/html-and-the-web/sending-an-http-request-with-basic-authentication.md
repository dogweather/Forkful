---
date: 2024-01-20 18:01:32.296895-07:00
description: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica \xE9\
  \ passar credenciais de acesso (usu\xE1rio e senha) para um servidor via HTTP. Programadores\
  \ fazem isso\u2026"
lastmod: '2024-03-13T22:44:46.237889-06:00'
model: gpt-4-1106-preview
summary: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica \xE9 passar\
  \ credenciais de acesso (usu\xE1rio e senha) para um servidor via HTTP."
title: "Enviando uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica"
weight: 45
---

## Como Fazer:
Para enviar uma requisição HTTP com autenticação básica em Elixir, utilizamos a biblioteca `HTTPoison` para facilitar o processo. Aqui está um exemplo:

```elixir
# Adicione HTTPoison à sua lista de dependências no mix.exs
defp deps do
  [
    {:httpoison, "~> 1.8"}
  ]
end

# Execute mix deps.get para instalar a biblioteca
# Após instalar, você pode fazer uma requisição com autenticação básica:

defmodule MyHTTPClient do
  def send_request do
    auth = {"meu_usuario", "minha_senha"}
    HTTPoison.get!(
      "https://minha.api/protegida",
      [],
      basic_auth: auth
    )
  end
end

# Usar a função e mostrar a resposta
IO.inspect(MyHTTPClient.send_request)
```

Saída esperada (exemplo):
```elixir
%HTTPoison.Response{
  body: "Conteúdo protegido",
  status_code: 200,
  ...
}
```

## Mergulho Profundo
Antes de `HTTPoison`, a comunidade de Elixir frequentemente recorria ao `hackney` diretamente (é a biblioteca que o `HTTPoison` abstrai). As autenticações via HTTP surgiram como um método simples para controlar o acesso a webpages, antes mesmo do advento de formas mais complexas e seguras como o OAuth.

Enviar uma requisição com autenticação básica é simples, mas não muito seguro por si só, pois as credenciais são codificadas em Base64, não criptografadas. Por isso, é crucial usar HTTPS, que adiciona uma camada de segurança com a criptografia SSL/TLS.

Alternativas para a autenticação em APIs incluem tokens de acesso, autenticação Digest e JWT (Json Web Tokens), que oferecem medidas de segurança adicionais. Em Elixir, bibliotecas como `Guardian` são frequentemente usadas para trabalhar com JWT.

## Veja Também
- Documentação oficial do HTTPoison: https://hexdocs.pm/httpoison
- Guia sobre autenticação básica da MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication
- `Guardian`, uma biblioteca de autenticação para Elixir: https://github.com/ueberauth/guardian
- Mais sobre HTTPS e SSL/TLS: https://letsencrypt.org/pt-br/about/
