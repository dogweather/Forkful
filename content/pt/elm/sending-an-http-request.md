---
title:                "Enviando uma requisição HTTP"
date:                  2024-01-20T17:59:38.705437-07:00
model:                 gpt-4-1106-preview
simple_title:         "Enviando uma requisição HTTP"
programming_language: "Elm"
category:             "Elm"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/elm/sending-an-http-request.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Enviar uma requisição HTTP é o jeito de o seu programa bater papo com um servidor, pedindo ou enviando dados. Programadores fazem isso para buscar informações, mandar ordens ou simplesmente manter os sistemas conversando.

## Como Fazer:
```Elm
import Http
import Json.Decode exposing (string)

type Msg = Success String | Failure Http.Error

request : Http.Request String
request =
    Http.get
        { url = "https://api.example.com/data"
        , expect = Http.expectString Success Failure
        }

init : () -> ( Model, Cmd Msg )
init _ =
    ( initialModel, Http.send Failure request )
```

Esse código envia uma requisição HTTP GET e espera uma resposta em forma de texto. Quando a resposta chega, dependendo se foi sucesso ou falha, ela dispara uma mensagem `Success` ou `Failure`.

## Mergulho Profundo
Primeiro, uma rápida volta no tempo: as requisições HTTP são um pilar da web desde o começo dos anos 90. Elm, como uma linguagem voltada para a web, tem que lidar bem com isso.

Enviar requisições HTTP em Elm é interessante porque fazemos isso de forma declarativa. Você descreve a requisição e como lidar com a resposta, e o Elm cuida do resto.

Sobre alternativas: antes de Elm, JavaScript era a go-to language para web. Você ainda pode usar JavaScript para requisições HTTP, mas Elm promete menos bugs e mais facilidade de manutenção.

Detalhes de implementação: Elm usa o `Http` module para lidar com requisições. Usamos `Http.get` para buscar dados, mas existem outros métodos como `Http.post` para enviar dados. Decoders, como `Json.Decode.string`, são usados para interpretar as respostas.

## Veja Também
- Documentação oficial do Elm sobre HTTP: https://package.elm-lang.org/packages/elm/http/latest/
- Guia de JSON Decoding no Elm: https://guide.elm-lang.org/interop/json.html
- Uma conversa sobre Elm e requisições HTTP: https://discourse.elm-lang.org/c/show-and-tell
