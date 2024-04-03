---
date: 2024-01-20 14:56:14.068274-07:00
description: "Checar se um diret\xF3rio existe \xE9 o processo de verificar se um\
  \ caminho espec\xEDfico refere-se a um diret\xF3rio no sistema de arquivos. Programadores\
  \ fazem isso\u2026"
lastmod: '2024-03-13T22:44:46.514191-06:00'
model: unknown
summary: "Checar se um diret\xF3rio existe \xE9 o processo de verificar se um caminho\
  \ espec\xEDfico refere-se a um diret\xF3rio no sistema de arquivos."
title: "Verificando se um diret\xF3rio existe"
weight: 20
---

## Como Fazer:
Elm é uma linguagem para aplicações web e, portanto, não tem acesso direto ao sistema de arquivos do servidor ou do cliente, então você não pode verificar diretamente se um diretório existe como faria em outras linguagens como Node.js ou Python. Mas você pode fazer requisições para um servidor e manejar respostas para inferir se um diretório ou recurso está disponível. Abaixo está um exemplo simplificado usando `Http` para checar se um recurso existe:

```Elm
module Main exposing (..)

import Browser
import Html exposing (text)
import Http

type Msg
    = CheckResource
    | HandleResponse (Result Http.Error ())

type alias Model =
    { resourceExists : Bool }

init : Model
init =
    { resourceExists = False }

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        CheckResource ->
            (model, Http.head "http://example.com/mydirectory" |> Http.send HandleResponse)

        HandleResponse (Ok _) ->
            ({ model | resourceExists = True }, Cmd.none)
            
        HandleResponse (Err _) ->
            (model, Cmd.none)

view : Model -> Html.Html Msg
view model =
    if model.resourceExists then
        text "O recurso existe!"
    else
        text "O recurso não existe ou está indisponível."

main =
  Browser.sandbox { init = init, update = update, view = view }
```

Esse código manda uma requisição `HEAD` para o servidor, se a resposta for positiva (`Ok _`), isso indica que o recurso existe, o contrário com um erro (`Err _`).

## Mergulho Profundo
Historicamente, verificações de diretórios são relevantes para linguagens com acesso ao sistema de arquivos local ou de servidores, como Python, Ruby ou Node.js. Elm, sendo focada no lado do cliente para aplicações web, opera sob um modelo diferente. Ainda assim, a necessidade de verificar a existência de recursos é gerida através de requisições HTTP, como ilustrado no exemplo acima.

Alternativas para esta função em Elm incluem o desenho de APIs no servidor que podem explicitamente informar sobre a existência de recursos ao invés de confiar em inferências feitas por respostas HTTP.

Detalhes de implementação para a checagem de diretórios em Elm vão normalmente envolver conexões com um backend via requests. O backend é que de fato interage com o sistema de arquivos e fornece respostas adequadas para a aplicação Elm.

## Veja Também
- Elm Http package documentation: [https://package.elm-lang.org/packages/elm/http/latest/](https://package.elm-lang.org/packages/elm/http/latest/)
- Elm Guide on Effects - para um entendimento aprofundado de `Cmd`: [https://guide.elm-lang.org/effects/](https://guide.elm-lang.org/effects/)
- HTTP response status codes - entendendo respostas do servidor: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
