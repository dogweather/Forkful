---
title:                "두 날짜 비교하기"
date:                  2024-01-20T17:33:21.783135-07:00
model:                 gpt-4-1106-preview
simple_title:         "두 날짜 비교하기"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/haskell/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why?
(무엇과 왜?)
두 날짜를 비교한다는 건, 그것들이 얼마나 떨어져 있는지, 어느 것이 앞선지 뒤쳐지는지 판단하는 것입니다. 프로그래머들이 이런 비교를 진행하는 건, 시간 기반의 로직을 결정하거나, 기간을 계산하기 위해서죠.

## How to:
(어떻게 하나:)
다음은 두 날짜를 비교하는 Haskell 예제와 출력 결과입니다.

```Haskell
import Data.Time

-- 두 날짜를 비교하는 함수
compareDates :: Day -> Day -> Ordering
compareDates date1 date2 = compare date1 date2

main :: IO ()
main = do
  let date1 = fromGregorian 2023 3 14  -- 2023년 3월 14일
      date2 = fromGregorian 2024 3 14  -- 2024년 3월 14일
  print $ compareDates date1 date2
```

위 코드를 실행하면 다음과 같은 출력을 얻을 수 있습니다:

```
LT  -- date1이 date2보다 앞선 날짜임
```

## Deep Dive:
(깊은 탐색:)
Haskell에서 날짜를 비교하는 일은 `Data.Time` 모듈 덕분에 간단합니다. 이 모듈은 Haskell에서 시간을 처리하는 표준 방식을 제공하는데, 국제 표준 시간과 역사적으로 사용되어온 그레고리력을 지원합니다.

`Day` 타입은 그레고리력의 날짜를 나타내고, `compare` 함수로 쉽게 비교할 수 있습니다. 두 날짜가 같은지, 이전인지, 이후인지를 판단하는 세 가지 결과(`EQ`, `LT`, `GT`)가 있죠.

대안으로, `diffDays` 함수를 사용하여 두 날짜 간의 차이를 일 단위로 계산하는 것도 가능합니다. 또한 더 복잡한 날짜와 시간의 비교를 위해서는 `UTCTime` 타입을 사용할 수 있습니다.

구현에 있어서, 일반적으로 시간대(timezone) 처리는 복잡할 수 있지만, Haskell은 `TimeZone` 타입과 관련 함수들을 제공해 이 문제를 해결하도록 도와줍니다.

## See Also:
(더 보기:)
- Haskell `Data.Time` 문서: http://hackage.haskell.org/package/time-1.9.3/docs/Data-Time.html
- Haskell 시간 처리에 대한 안내서: https://wiki.haskell.org/Working_with_time
- 그레고리력에 대한 정보: https://en.wikipedia.org/wiki/Gregorian_calendar