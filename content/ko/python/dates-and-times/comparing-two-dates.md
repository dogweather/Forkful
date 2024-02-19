---
aliases:
- /ko/python/comparing-two-dates/
date: 2024-01-20 17:33:44.860756-07:00
description: "\uB450 \uB0A0\uC9DC\uB97C \uBE44\uAD50\uD55C\uB2E4\uB294 \uAC74, \uADF8\
  \uB4E4\uC774 \uC11C\uB85C \uC5BC\uB9C8\uB098 \uCC28\uC774\uB098\uB294\uC9C0, \uC5B4\
  \uB5A4 \uAC83\uC774 \uB354 \uC774\uC804\uC774\uAC70\uB098 \uCD5C\uC2E0\uC778\uC9C0\
  \ \uD30C\uC545\uD558\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4. \uC774\uB97C \uD1B5\uD574\
  \ \uD504\uB85C\uADF8\uB798\uBA38\uB294 \uC720\uD6A8\uC131 \uAC80\uC0AC, \uC774\uBCA4\
  \uD2B8 \uAE30\uAC04 \uBD84\uC11D, \uC2DC\uAC04 \uAE30\uBC18\uC758 \uB85C\uC9C1 \uC2E4\
  \uD589 \uB4F1\uC744 \uD560 \uC218 \uC788\uC2B5\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: 2024-02-18 23:09:05.644316
model: gpt-4-1106-preview
summary: "\uB450 \uB0A0\uC9DC\uB97C \uBE44\uAD50\uD55C\uB2E4\uB294 \uAC74, \uADF8\uB4E4\
  \uC774 \uC11C\uB85C \uC5BC\uB9C8\uB098 \uCC28\uC774\uB098\uB294\uC9C0, \uC5B4\uB5A4\
  \ \uAC83\uC774 \uB354 \uC774\uC804\uC774\uAC70\uB098 \uCD5C\uC2E0\uC778\uC9C0 \uD30C\
  \uC545\uD558\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4. \uC774\uB97C \uD1B5\uD574 \uD504\
  \uB85C\uADF8\uB798\uBA38\uB294 \uC720\uD6A8\uC131 \uAC80\uC0AC, \uC774\uBCA4\uD2B8\
  \ \uAE30\uAC04 \uBD84\uC11D, \uC2DC\uAC04 \uAE30\uBC18\uC758 \uB85C\uC9C1 \uC2E4\
  \uD589 \uB4F1\uC744 \uD560 \uC218 \uC788\uC2B5\uB2C8\uB2E4."
title: "\uB450 \uB0A0\uC9DC \uBE44\uAD50\uD558\uAE30"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
두 날짜를 비교한다는 건, 그들이 서로 얼마나 차이나는지, 어떤 것이 더 이전이거나 최신인지 파악하는 과정입니다. 이를 통해 프로그래머는 유효성 검사, 이벤트 기간 분석, 시간 기반의 로직 실행 등을 할 수 있습니다.

## How to: (어떻게 하나요?)
```Python
from datetime import datetime

# 날짜 생성
date1 = datetime(2023, 4, 1)
date2 = datetime(2023, 4, 15)

# 날짜 비교
is_before = date1 < date2
days_difference = (date2 - date1).days

# 출력
print(f"Is date1 before date2? {is_before}")
print(f"The difference in days is: {days_difference}")

# 샘플 출력
# Is date1 before date2? True
# The difference in days is: 14
```

## Deep Dive (심도 있는 탐구)
날짜 비교는 `datetime` 모듈로 킬러 기능을 발휘합니다. 2003년에 처음 나온 이후, Python은 날짜와 시간을 다루는 강력한 표준 라이브러리를 제공합니다. 대안으로 `dateutil` 라이브러리가 있지만, 대부분 표준 `datetime`이면 충분해요. 비교하는 것은 내부적으로 날짜와 시간을 POSIX 타임스탬프로 변환해서 수행합니다. 이는 1970년 1월 1일 0시 0분 0초로부터의 초 수를 의미하죠.

## See Also (더 보기)
- Python 공식 문서에서 `datetime` 모듈: https://docs.python.org/3/library/datetime.html
- Python 날짜와 시간 다루기, Real Python 가이드: https://realpython.com/python-datetime/
- `dateutil` 라이브러리 문서: https://dateutil.readthedocs.io/en/stable/
