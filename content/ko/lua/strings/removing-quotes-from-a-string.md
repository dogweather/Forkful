---
aliases:
- /ko/lua/removing-quotes-from-a-string/
date: 2024-01-26 03:40:54.800432-07:00
description: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uB530\uC634\uD45C\uB97C \uC81C\uAC70\
  \uD55C\uB2E4\uB294 \uAC83\uC740 \uD14D\uC2A4\uD2B8\uB97C \uAC10\uC2F8\uACE0 \uC788\
  \uB294 \uADF8 \uB354\uBE14 \uB610\uB294 \uC2F1\uAE00 \uB530\uC634\uD45C \uBB38\uC790\
  \uB97C \uBC97\uACA8\uB0B4\uB294 \uAC83\uC744 \uC758\uBBF8\uD569\uB2C8\uB2E4. \uD504\
  \uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC785\uB825 \uAC12\uC744 \uC815\uD654\uD558\
  \uAC70\uB098, \uD30C\uC2F1\uC744 \uC6A9\uC774\uD558\uAC8C \uD558\uAC70\uB098, \uC77C\
  \uAD00\uC131\uC774 \uC5C6\uAC8C \uC778\uC6A9\uB41C \uB370\uC774\uD130\uB97C \uC870\
  \uD654\uB86D\uAC8C \uB9CC\uB4E4\uAE30 \uC704\uD574 \uC774 \uC791\uC5C5\uC744 \uD569\
  \uB2C8\uB2E4."
lastmod: 2024-02-18 23:09:06.398645
model: gpt-4-0125-preview
summary: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uB530\uC634\uD45C\uB97C \uC81C\uAC70\uD55C\
  \uB2E4\uB294 \uAC83\uC740 \uD14D\uC2A4\uD2B8\uB97C \uAC10\uC2F8\uACE0 \uC788\uB294\
  \ \uADF8 \uB354\uBE14 \uB610\uB294 \uC2F1\uAE00 \uB530\uC634\uD45C \uBB38\uC790\uB97C\
  \ \uBC97\uACA8\uB0B4\uB294 \uAC83\uC744 \uC758\uBBF8\uD569\uB2C8\uB2E4. \uD504\uB85C\
  \uADF8\uB798\uBA38\uB4E4\uC740 \uC785\uB825 \uAC12\uC744 \uC815\uD654\uD558\uAC70\
  \uB098, \uD30C\uC2F1\uC744 \uC6A9\uC774\uD558\uAC8C \uD558\uAC70\uB098, \uC77C\uAD00\
  \uC131\uC774 \uC5C6\uAC8C \uC778\uC6A9\uB41C \uB370\uC774\uD130\uB97C \uC870\uD654\
  \uB86D\uAC8C \uB9CC\uB4E4\uAE30 \uC704\uD574 \uC774 \uC791\uC5C5\uC744 \uD569\uB2C8\
  \uB2E4."
title: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uB530\uC634\uD45C \uC81C\uAC70\uD558\uAE30"
---

{{< edit_this_page >}}

## 무엇 & 왜?
문자열에서 따옴표를 제거한다는 것은 텍스트를 감싸고 있는 그 더블 또는 싱글 따옴표 문자를 벗겨내는 것을 의미합니다. 프로그래머들은 입력 값을 정화하거나, 파싱을 용이하게 하거나, 일관성이 없게 인용된 데이터를 조화롭게 만들기 위해 이 작업을 합니다.

## 어떻게:
Lua에서 따옴표를 제거하는 방법은 여기 있습니다:

```lua
local function remove_quotes(str)
  return (str:gsub("^%p(.*)%p$", "%1"))
end

print(remove_quotes('"안녕, 세상!"'))     -- 안녕, 세상!
print(remove_quotes("'안녕히 가세요, 따옴표!'"))  -- 안녕히 가세요, 따옴표!
```

빙고! 그 따옴표들은 마치 건조기 속 양말처럼 사라졌습니다.

## 심층 분석
언어가 텍스트를 처리할 수 있게 된 이래로 사람들은 문자열에서 따옴표를 제거해 왔습니다, 그것은 거의 영원한 시간 동안의 일입니다. Lua에서는 `gsub` 함수가 무거운 짐을 들어, 패턴을 메스처럼 사용해 따옴표를 제거합니다. 대안? 물론, 지원하는 언어에서는 정규 표현식을 사용하거나, 각 문자를 통해 실행하는 자신만의 루프를 작성할 수 있습니다(하품, 하지만 어쨌든 그것은 당신의 시간입니다).

Lua의 패턴 매칭은 전체 라이브러리를 가져오지 않고도 정규 표현식 경험의 영향을 줍니다. 캐럿(`^`)과 달러 기호(`$`)는 각각 문자열의 시작과 끝을 일치시킵니다; `%p`는 모든 구두점 문자와 일치합니다. 맨 앞과 맨 뒤의 구두점을 털어낸 후, `(.*),`로 모든 것을 캡처하고 `" %1"`을 사용하여 전체 일치를 그 캡처 그룹으로 교체합니다.

Lua의 패턴 매칭이 전체 정규 표현식 엔진만큼 강력하지 않다는 것을 기억하세요 - 예를 들어, 개수를 세거나 되감기(backtrack)를 할 수 없습니다. 이러한 단순함은 당신이 다루고 있는 따옴표와 그것들이 숨어 있는 위치에 따라 축복일 수도 있고 저주일 수도 있습니다.

## 또한 보기
Lua의 패턴 매칭에 대해 더 깊이 파고들어 보세요, PiL(Programming in Lua) 책에서: http://www.lua.org/pil/20.2.html

기교 넘치는 방법을 확인하고 싶다면, 비교를 위해 다른 언어가 이를 어떻게 하는지 확인하세요, Python의 `str.strip`부터 시작하세요: https://docs.python.org/3/library/stdtypes.html#str.strip
