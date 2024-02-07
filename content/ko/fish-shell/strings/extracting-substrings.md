---
title:                "부분 문자열 추출"
date:                  2024-01-20T17:45:31.303140-07:00
model:                 gpt-4-1106-preview
simple_title:         "부분 문자열 추출"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/fish-shell/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why?
무엇이며 왜 사용하는가? 문자열에서 특정 부분을 추출하는 것을 'substring 추출'이라고 합니다. 이런 작업은 데이터 파싱, 사용자 입력 처리, 혹은 텍스트 기반의 조건 확인 시 필요합니다.

## How to:
```Fish Shell
# 문자열 정의
set full_string "Fish Shell is fantastic!"

# 인덱스 6부터 10개 문자 추출
set substring (string sub -s 6 -l 10 -- $full_string)
echo $substring  # 출력: Shell is f

# 인덱스 6부터 끝까지 문자 추출
set substring_end (string sub -s 6 -- $full_string)
echo $substring_end  # 출력: Shell is fantastic!
```

## Deep Dive
Fish Shell에서 문자열을 다루는 것은 상당히 직관적입니다. 과거에는 UNIX 환경에서 `cut`, `awk`, `sed` 같은 툴들로 이 작업을 했습니다. Fish는 이러한 작업을 더 간단하게 할 수 있는 `string` 자체 명령어를 제공합니다. 예를 들어, `string sub` 명령은 문자열을 쉽게 추출할 수 있게 해줍니다. 인덱스와 길이, 혹은 시작점과 끝점을 정해서 원하는 부분만 가져올 수 있죠. 별도의 복잡한 정규 표현식이나 외부 프로그램 없이도 말이죠.

## See Also
- [Fish Shell Documentation on String Manipulation](https://fishshell.com/docs/current/cmds/string.html)
- [Stack Overflow: How to extract a substring in Fish shell](https://stackoverflow.com/questions/tagged/fish)
