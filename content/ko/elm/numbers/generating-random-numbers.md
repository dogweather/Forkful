---
title:                "랜덤 숫자 생성하기"
date:                  2024-02-27T22:50:37.211859-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-02-27, dogweather, edited and tested
  - 2024-02-27, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇이고 왜인가?
Elm에서 무작위 수를 생성하는 데는 `Random` 모듈을 사용하여 가짜 무작위 수를 생성하는 것이 포함되며, 이는 게임, 시뮬레이션, 그리고 확률 과정이 필요한 알고리즘의 일부로 사용되는 등 다양한 작업에 유용합니다. 이 기능은 개발자가 응용 프로그램에 예측 불가능성과 다양성을 추가할 수 있게 하여 사용자 경험 및 기능을 향상시킵니다.

## 방법:
Elm의 순수 함수적 특성은 명령형 언어에서처럼 직접 무작위 수를 생성할 수 없다는 것을 의미합니다. 대신, `Random` 모듈을 명령과 함께 사용합니다. 1부터 100 사이의 무작위 정수를 생성하는 기본 예가 여기 있습니다.

우선, `elm install elm/random`로 `Random` 모듈을 설치합니다. 그런 다음 필요한 HTML 및 이벤트 모듈과 함께 Elm 파일에 가져옵니다. 다음과 같습니다:

`src/Main.elm`

```elm
module Main exposing (..)

import Browser
import Html exposing (Html, button, text, div)
import Html.Events exposing (onClick)
import Random
```

이 예제를 독립 실행 형식으로 만들기 위해서는 이런 템플릿을 추가할 수 있습니다:
```elm
main =
  Browser.element { init = init, update = update, subscriptions = subscriptions, view = view }

init : () -> (Model, Cmd Msg)
init _ =
  (Model 0, Cmd.none)

subscriptions : Model -> Sub Msg
subscriptions _ =
  Sub.none
```

다음으로, 무작위 수를 생성할 **명령**을 정의합니다. 이는 생성될 무작위 수를 처리하는 `Msg` 유형과, 이를 저장할 `Model`, 그리고 이 모든 것을 함께 묶는 업데이트 함수를 설정하는 것을 포함합니다.
```elm
type Msg
    = Generate
    | NewRandom Int

type alias Model = { randomNumber : Int }

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        Generate ->
            ( model, Random.generate NewRandom (Random.int 1 100) )

        NewRandom number ->
            ( { model | randomNumber = number }, Cmd.none )
```

무작위 수 생성을 트리거하려면, 예를 들어, 뷰에서 `Generate` 메시지를 보내는 버튼을 통해 이를 수행할 수 있습니다:
```elm
view : Model -> Html Msg
view model =
    div []
        [ div [] [ text ("Random Number: " ++ String.fromInt model.randomNumber) ]
        , button [ onClick Generate ] [ text "Generate" ]
        ]
```

"Generate" 버튼을 클릭하면 1부터 100 사이의 무작위 수가 표시됩니다.

이 단순한 접근 방식은 적응하고 확장될 수 있으며, `Random` 모듈에 있는 다른 함수를 사용하여 무작위 부동소수점, 리스트 또는 사용자 정의 유형에 기반한 복잡한 데이터 구조까지 생성할 수 있어 Elm 애플리케이션에 예측 불가능성을 더하는 광범위한 장을 제공합니다.

Elm 가이드에서는 훨씬 더 자세히 설명하고 있습니다. 또한 [여섯 면체 주사위를 굴리는 예제](https://guide.elm-lang.org/effects/random)도 있습니다.
