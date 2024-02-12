---
title:                "Enviando uma requisição HTTP com autenticação básica"
date:                  2024-01-20T18:02:38.440396-07:00
model:                 gpt-4-1106-preview
simple_title:         "Enviando uma requisição HTTP com autenticação básica"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/rust/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## O Que & Por Quê?
Enviar uma solicitação HTTP com autenticação básica significa incluir credenciais de usuário e senha em um cabeçalho para acessar um recurso protegido. Programadores fazem isso para interagir com APIs que exigem autenticação simples para fornecer segurança básica.

## Como Fazer:
```Rust
use reqwest::{blocking::Client, header};

fn main() -> Result<(), reqwest::Error> {
    // Seu nome de usuário e senha
    let username = "usuario";
    let password = "senha";

    // Codificar em base64 a autenticação
    let basic_auth = format!("Basic {}", base64::encode(format!("{}:{}", username, password)));
    
    // Criar cliente HTTP com cabeçalho de autenticação básica
    let client = Client::new();
    let response = client
        .get("https://seu-endereco-api.com/recurso")
        .header(header::AUTHORIZATION, basic_auth)
        .send()?;

    // Tratar a resposta
    println!("Status: {}", response.status());
    println!("Headers:\n{:?}", response.headers());
    println!("Body:\n{}", response.text()?);

    Ok(())
}
```
Exemplo de saída:
```
Status: 200 OK
Headers:
{
    ...
    "content-type": "application/json",
    ...
}
Body:
{
    "dados": "valor",
    ...
}
```

## Aprofundando
A autenticação básica HTTP é um método clássico, parte do HTTP desde os seus primeiros dias. Apesar de sua simplicidade, hoje em dia é menos usada devido a vulnerabilidades, sendo frequentemente substituída por tokens de autenticação, como o OAuth.

Alternativas incluem HTTPS, que encripta credenciais e evita que sejam interceptadas, e mecanismos de autenticação mais complexos que oferecem maior segurança.

Os detalhes de implementação em Rust envolvem usar bibliotecas como `reqwest` para enviar a solicitação e `base64` para a codificação das credenciais, além de manusear adequadamente os cabeçalhos HTTP.

## Veja Também
- Documentação do `reqwest`: https://docs.rs/reqwest/
- Especificação da autenticação básica HTTP: https://tools.ietf.org/html/rfc7617
- RFC 2617 (autenticação HTTP): https://tools.ietf.org/html/rfc2617
- Tutorial sobre autorização com tokens: https://auth0.com/docs/tokens
