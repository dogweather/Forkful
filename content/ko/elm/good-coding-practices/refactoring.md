---
aliases:
- /ko/elm/refactoring/
date: 2024-01-26 01:18:14.609352-07:00
description: "\uB9AC\uD329\uD130\uB9C1\uC740 \uBCF8\uC9C8\uC801\uC73C\uB85C \uCF54\
  \uB4DC \uBCA0\uC774\uC2A4\uB97C \uBD04\uCCAD\uC18C\uD558\uB294 \uAC83\uC785\uB2C8\
  \uB2E4 - \uAE30\uC874 \uCF54\uB4DC\uC758 \uAD6C\uC870\uB97C \uBCC0\uACBD\uD558\uC9C0\
  \ \uC54A\uACE0 \uC678\uBD80 \uD589\uB3D9\uC744 \uBCC0\uACBD\uD558\uC9C0 \uC54A\uB294\
  \ \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740\
  \ \uCF54\uB4DC\uB97C \uB354 \uC77D\uAE30 \uC27D\uAC8C \uB9CC\uB4E4\uACE0, \uBCF5\
  \uC7A1\uC131\uC744 \uC904\uC774\uBA70, \uC720\uC9C0\uBCF4\uC218\uC131\uC744 \uAC1C\
  \uC120\uD558\uACE0, \uD655\uC7A5\uD558\uAE30 \uC27D\uAC8C \uB9CC\uB4E4\uAE30 \uC704\
  \uD574 \uC774 \uC791\uC5C5\uC744 \uD569\uB2C8\uB2E4."
lastmod: 2024-02-18 23:09:06.099041
model: gpt-4-0125-preview
summary: "\uB9AC\uD329\uD130\uB9C1\uC740 \uBCF8\uC9C8\uC801\uC73C\uB85C \uCF54\uB4DC\
  \ \uBCA0\uC774\uC2A4\uB97C \uBD04\uCCAD\uC18C\uD558\uB294 \uAC83\uC785\uB2C8\uB2E4\
  \ - \uAE30\uC874 \uCF54\uB4DC\uC758 \uAD6C\uC870\uB97C \uBCC0\uACBD\uD558\uC9C0\
  \ \uC54A\uACE0 \uC678\uBD80 \uD589\uB3D9\uC744 \uBCC0\uACBD\uD558\uC9C0 \uC54A\uB294\
  \ \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740\
  \ \uCF54\uB4DC\uB97C \uB354 \uC77D\uAE30 \uC27D\uAC8C \uB9CC\uB4E4\uACE0, \uBCF5\
  \uC7A1\uC131\uC744 \uC904\uC774\uBA70, \uC720\uC9C0\uBCF4\uC218\uC131\uC744 \uAC1C\
  \uC120\uD558\uACE0, \uD655\uC7A5\uD558\uAE30 \uC27D\uAC8C \uB9CC\uB4E4\uAE30 \uC704\
  \uD574 \uC774 \uC791\uC5C5\uC744 \uD569\uB2C8\uB2E4."
title: "\uB9AC\uD329\uD1A0\uB9C1"
---

{{< edit_this_page >}}

## 무엇이며 왜 하나요?
리팩터링은 본질적으로 코드 베이스를 봄청소하는 것입니다 - 기존 코드의 구조를 변경하지 않고 외부 행동을 변경하지 않는 것을 말합니다. 프로그래머들은 코드를 더 읽기 쉽게 만들고, 복잡성을 줄이며, 유지보수성을 개선하고, 확장하기 쉽게 만들기 위해 이 작업을 합니다.

## 어떻게 하나요:
너무 많은 일을 하는 Elm 함수가 있고, UI 로직과 상태 업데이트를 혼합한다고 가정해 보세요. 리팩터링하기에 완벽한 후보입니다. 원래:

```Elm
updateAndFormat : String -> Model -> (Model, Cmd Msg)
updateAndFormat input model =
    let
        updatedModel = { model | userInput = input }
    in
    if String.length input > 5 then
        ( updatedModel, Cmd.none )
    else
        ( model, Cmd.none )
```

리팩터링 후, 우리는 로직을 다른 함수로 분리하여 관심사를 분리합니다:

```Elm
-- 업데이트 로직이 분리됩니다
updateUserInput : String -> Model -> Model
updateUserInput input model = 
    { model | userInput = input }

-- 포맷팅(뷰) 로직도 분리됩니다
formatUserInput : Model -> (Model, Cmd Msg)
formatUserInput model =
    if String.length model.userInput > 5 then
        ( model, Cmd.none )
    else
        ( { model | userInput = "" }, Cmd.none ) -- 너무 짧으면 입력을 지우는 예시 규칙.

-- 업데이트 함수는 이제 헬퍼 함수를 사용합니다
updateAndFormat : String -> Model -> (Model, Cmd Msg)
updateAndFormat input model =
    model
    |> updateUserInput input
    |> formatUserInput
```
이러한 변경 사항으로, 명확한 분리가 있으며, 각 함수는 이해하고 테스트하기가 더 쉽습니다.

## 심층 분석
리팩터링은 프로그래밍 초기부터 이미 코드 변경 비용이 개발 과정의 중요한 측면으로 인식되고 있을 때 공식적인 연습으로 사용될 수 있습니다. 특히 Martin Fowler의 "Refactoring: Improving the Design of Existing Code," 책은 1990년대 후반에 발표되어 구조화된 접근 방식과 리팩터링 기회를 식별하기 위한 "코드 냄새" 카탈로그로 리팩터링을 위한 무대를 마련하였습니다.

Elm 컨텍스트에서, 리팩터링은 프로세스 동안에 자신감을 촉진하는 강력한 타입 시스템과 같은 언어의 장점을 활용합니다. 수동 리팩터링에 대한 대안은 자동 코드 변환 툴을 포함할 수 있지만, Elm의 툴링은 일부 더 오래된 언어에 비해 여전히 성숙해지고 있습니다. 구현 세부 사항은 종종 함수 추출, 이름 변경, 조건 단순화와 같은 일반적인 리팩터링을 중심으로 합니다. Elm 컴파일러는 리팩터링에서 중요한 동맹군입니다, 무엇인가 잘못되면 즉시 알려주어 리팩터한 코드가 여전히 작동하는지 확인합니다.

## 참고 자료
- ["Refactoring: Improving the Design of Existing Code" by Martin Fowler](https://martinfowler.com/books/refactoring.html)
- [Elm Discourse - Refactoring에 관한 주제들](https://discourse.elm-lang.org/search?q=refactoring)
