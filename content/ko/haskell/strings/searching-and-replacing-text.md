---
date: 2024-01-20 17:57:54.821040-07:00
description: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9 \uBC0F \uB300\uCCB4\uB294 \uBB38\uC790\
  \uC5F4 \uB0B4\uC5D0\uC11C \uD2B9\uC815 \uD328\uD134\uC744 \uCC3E\uC544 \uB2E4\uB978\
  \ \uD14D\uC2A4\uD2B8\uB85C \uBC14\uAFB8\uB294 \uC77C\uC785\uB2C8\uB2E4. \uD504\uB85C\
  \uADF8\uB798\uBA38\uB4E4\uC740 \uB370\uC774\uD130 \uC815\uC81C, \uBC84\uADF8 \uC218\
  \uC815, \uCF54\uB4DC \uC5C5\uB370\uC774\uD2B8 \uB4F1\uC744 \uC704\uD574 \uC790\uC8FC\
  \ \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.274753-06:00'
model: gpt-4-1106-preview
summary: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9 \uBC0F \uB300\uCCB4\uB294 \uBB38\uC790\uC5F4\
  \ \uB0B4\uC5D0\uC11C \uD2B9\uC815 \uD328\uD134\uC744 \uCC3E\uC544 \uB2E4\uB978 \uD14D\
  \uC2A4\uD2B8\uB85C \uBC14\uAFB8\uB294 \uC77C\uC785\uB2C8\uB2E4."
title: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9 \uBC0F \uAD50\uCCB4"
weight: 10
---

## How to: (방법)
Haskell에서 텍스트 검색 및 대체를 하려면 `Data.Text` 모듈을 쓸 수 있습니다. 예시와 결과를 봅시다.

```Haskell
import Data.Text as T

-- 텍스트 검색 및 대체하는 함수
searchReplace :: Text -> Text -> Text -> Text
searchReplace searchFor replaceWith textContent =
  T.replace searchFor replaceWith textContent

-- 사용 예시
main :: IO ()
main = do
  let originalText = "Haskell is fun. Haskell is functional."
  let newText = searchReplace "fun" "awesome" originalText
  
  putStrLn $ T.unpack newText
  -- 출력: "Haskell is awesome. Haskell is functional."
```

## Deep Dive (심층 분석)
텍스트 검색 및 대체 기능은 1970년대 초기 유닉스 텍스트 편집기에서 시작되었습니다. `sed`(stream editor)와 같은 도구가 이 일을 위해 만들어졌죠. Haskell의 `Data.Text` 모듈은 성능 최적화를 위해 내부적으로 배열을 사용하여 구현되었습니다. `replace` 함수는 순수 함수로, 바꾸려는 문자열이 없다면 원본 텍스트를 그대로 반환합니다.

대안으로, 규칙 기반 문자열 전환을 위한 `regex` 패키지를 사용할 수 있습니다. 하지만 간단한 작업이라면 `Data.Text`의 `replace`가 더 간결합니다.

## See Also (참고 자료)
- Haskell `Data.Text` 모듈: https://hackage.haskell.org/package/text-1.2.4.1/docs/Data-Text.html
- Haskell `regex` 패키지: https://hackage.haskell.org/package/regex-base
- `sed` 스트림 편집기 정보: https://www.gnu.org/software/sed/manual/sed.html
