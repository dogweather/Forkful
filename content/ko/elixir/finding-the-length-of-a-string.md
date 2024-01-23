---
title:                "문자열의 길이 찾기"
date:                  2024-01-20T17:47:57.324377-07:00
model:                 gpt-4-1106-preview
simple_title:         "문자열의 길이 찾기"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/elixir/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
문자열의 길이를 찾는 것은 문자열에 포함된 문자의 수를 세는 과정입니다. 프로그래머들은 데이터를 검증하거나, UI를 조정하거나, 특정 조건을 기반으로 로직을 실행하기 위해 이를 수행합니다.

## How to: (어떻게 하나요?)
Elixir에서 문자열의 길이를 얻기 위해 `String.length/1` 함수를 사용합니다. 쉽고 직관적이죠:
```elixir
string = "안녕하세요!"
length = String.length(string)
IO.puts(length)
```
출력: 
```
6
```

숫자 '6'은 "안녕하세요!" 문자열에 있는 문자 개수를 나타냅니다.

## Deep Dive (심층 탐구)
Elixir에서 문자열은 UTF-8로 인코딩되어 있습니다. 이는 각 문자가 하나의 코드포인트로 카운트된다는 것을 의미합니다. `String.length/1`는 바로 이 코드포인트의 수를 세는 함수입니다.

예전에, 문자열 처리는 ASCII 기반이었고, 모든 문자가 동일한 바이트 수로 표현되었습니다. 하지만, 다국어를 지원하기 위해 UTF-8이 중용되면서 문자열의 길이를 계산하는 과정이 복잡해졌습니다.

문자열의 바이트 길이를 알고 싶다면 `byte_size/1` 함수를 사용할 수 있습니다. 이는 내부 바이트 표현의 길이를 반환합니다.
```elixir
byte_size("안녕하세요!") # => 15
```

하지만 대부분의 경우, `String.length/1`는 텍스트 처리에 더 유용합니다. 성능에 민감한 상황에서 `String.length/1` 함수가 문자열 전체를 순회하기 때문에 비용이 발생한다는 점을 염두해두세요. 유니코드 문자열에는 매우 적은 비용이 들긴 하지만, 엄청나게 긴 문자열에서는 중요할 수 있습니다.

## See Also (더 보기)
- Elixir 공식 문서 `String.length/1`: https://hexdocs.pm/elixir/String.html#length/1
- UTF-8과 문자열 인코딩에 대한 정보: https://en.wikipedia.org/wiki/UTF-8
- `byte_size/1` 함수에 대한 Elixir 문서: https://hexdocs.pm/elixir/Kernel.html#byte_size/1
