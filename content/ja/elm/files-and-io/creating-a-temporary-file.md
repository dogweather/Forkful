---
aliases:
- /ja/elm/creating-a-temporary-file/
date: 2024-01-20 17:40:06.594950-07:00
description: "\u4F5C\u696D\u4E2D\u30C7\u30FC\u30BF\u306E\u4E00\u6642\u4FDD\u5B58\u306B\
  \u4F7F\u3046\u300C\u4E00\u6642\u30D5\u30A1\u30A4\u30EB\u300D\u3092\u4F5C\u308B\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30E0\u304C\u30AF\u30E9\u30C3\u30B7\u30E5\u3057\u3066\u3082\
  \u30C7\u30FC\u30BF\u3092\u5B88\u308A\u3064\u3064\u3001\u5F8C\u51E6\u7406\u306E\u697D\
  \u306A\u7BA1\u7406\u3092\u5B9F\u73FE\u3059\u308B\u305F\u3081\u3002"
isCJKLanguage: true
lastmod: 2024-02-18 23:08:54.858948
model: gpt-4-1106-preview
summary: "\u4F5C\u696D\u4E2D\u30C7\u30FC\u30BF\u306E\u4E00\u6642\u4FDD\u5B58\u306B\
  \u4F7F\u3046\u300C\u4E00\u6642\u30D5\u30A1\u30A4\u30EB\u300D\u3092\u4F5C\u308B\u3002\
  \u30D7\u30ED\u30B0\u30E9\u30E0\u304C\u30AF\u30E9\u30C3\u30B7\u30E5\u3057\u3066\u3082\
  \u30C7\u30FC\u30BF\u3092\u5B88\u308A\u3064\u3064\u3001\u5F8C\u51E6\u7406\u306E\u697D\
  \u306A\u7BA1\u7406\u3092\u5B9F\u73FE\u3059\u308B\u305F\u3081\u3002"
title: "\u4E00\u6642\u30D5\u30A1\u30A4\u30EB\u306E\u4F5C\u6210"
---

{{< edit_this_page >}}

## What & Why? (「何となぜ？」)
作業中データの一時保存に使う「一時ファイル」を作る。プログラムがクラッシュしてもデータを守りつつ、後処理の楽な管理を実現するため。

## How to:
Elmで一時ファイルを直接扱うことはできませんが、Elmでフロントエンドを書いて、バックエンド（例えばNode.js）を介して一時ファイルを扱う方法があります。以下はElmからHTTPリクエストを使ってバックエンドに一時ファイルを作るよう依頼する例です。

```Elm
module Main exposing (..)

import Http
import Json.Encode as Encode

type Msg = CreateTempFile | TempFileCreated (Result Http.Error String)

createTempFile : Cmd Msg
createTempFile =
    Http.post
        { url = "バックエンドのURL/temp-file"
        , body = Http.jsonBody <| Encode.string "ファイルに必要なデータ"
        , expect = Http.expectWhatever TempFileCreated
        }

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        CreateTempFile ->
            (model, createTempFile)
            
        TempFileCreated result ->
            case result of
                Ok response ->
                    -- 一時ファイルが作成されたときの処理
                    -- response は一時ファイルのパスかもしれない
                    (model, Cmd.none)
                Err error ->
                    -- エラー処理
                    (model, Cmd.none)
```

## Deep Dive (「深掘り」)
Elmはウェブブラウザ内で動作する言語で、ファイルシステムに直接触る機能はありません。伝統的なプログラミング言語では、一時ファイルはデータを一時的に格納するのに使われますが、Elmでのソリューションはバックエンドと組み合わせることが必要です。以前の言語（CやRubyなど）では、組み込みのライブラリを使って直接一時ファイルを作れますが、Elmではそうではありません。よって、Elmを使う際の一時ファイルのアプローチは、主にバックエンドに委託する形となります。

## See Also (「関連項目」)
- ElmのHTTPパッケージドキュメント：[https://package.elm-lang.org/packages/elm/http/latest/](https://package.elm-lang.org/packages/elm/http/latest/)
- Node.jsの一時ファイル作成に関するライブラリ（例えば、`tmp`パッケージ）：[https://www.npmjs.com/package/tmp](https://www.npmjs.com/package/tmp)
- フロントエンドとバックエンドの通信に関する一般的な概要：[https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Client-Server_overview](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Client-Server_overview)
