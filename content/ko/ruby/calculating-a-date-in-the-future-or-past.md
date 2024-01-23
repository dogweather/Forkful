---
title:                "미래나 과거의 날짜 계산하기"
date:                  2024-01-20T17:32:15.713091-07:00
model:                 gpt-4-1106-preview
simple_title:         "미래나 과거의 날짜 계산하기"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Dates and Times"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/ruby/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?
미래나 과거의 특정 날짜를 계산한다는 것은 날짜에 일정 기간을 더하거나 빼는 것을 말합니다. 프로그래머는 예약 시스템, 기한 설정, 날짜 기반 리마인더와 같은 기능을 구현할 때 이를 활용합니다.

## How to:

```Ruby
require 'date'

# 오늘 날짜를 가져옵니다.
today = Date.today
puts "Today is: #{today}"

# 5일 후의 날짜를 계산합니다.
future_date = today + 5
puts "5 days from today will be: #{future_date}"

# 10일 전 날짜를 계산합니다.
past_date = today - 10
puts "10 days ago was: #{past_date}"

# 출력:
# Today is: 2023-03-25
# 5 days from today will be: 2023-03-30
# 10 days ago was: 2023-03-15
```

Ruby에서 날짜를 다루려면 `date` 라이브러리를 사용해야 합니다. `Date.today`를 이용해 현재 날짜를 얻고, 이를 기준으로 더하거나 빼면 됩니다.

## Deep Dive

날짜 계산은 컴퓨팅의 오래된 문제입니다. 초기 컴퓨터 프로그램에서도 날짜는 중요했고, Y2K 버그 같은 문제가 각광을 받기도 했죠. Ruby에서는 `date`와 `time` 라이브러리를 통해 날짜와 시간 계산이 가능합니다. 며칠 더하기나 빼기는 간단하지만, 윤년이나 시간대 변환 같은 복잡한 상황을 처리할 때는 더 신중해야 합니다.

`Date` 클래스 외에 `Time` 클래스나 외부 gem인 `ActiveSupport`(Rails의 일부)도 있습니다. 이들은 각기 다른 기능과 메소드를 제공하기 때문에, 목적에 맞게 선택해서 사용해야 합니다. 예를 들어, 정확한 시간 계산이 필요할 때는 `Time` 클래스가 더 적합할 수 있습니다.

## See Also

- Ruby의 `time` 라이브러리: [Ruby Time Documentation](https://ruby-doc.org/core-2.7.0/Time.html)
- `ActiveSupport`에 관한 정보: [ActiveSupport Core Extensions](https://edgeguides.rubyonrails.org/active_support_core_extensions.html)

이러한 문서들은 날짜와 시간 계산에 대한 보다 깊은 이해를 위한 좋은 출발점이 될 것입니다.
