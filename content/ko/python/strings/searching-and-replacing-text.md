---
aliases:
- /ko/python/searching-and-replacing-text/
date: 2024-01-20 17:58:47.791666-07:00
description: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9\uACFC \uAD50\uCCB4\uB294 \uBB38\uC790\
  \uC5F4 \uB0B4\uC5D0\uC11C \uD2B9\uC815 \uD328\uD134\uC744 \uCC3E\uC544 \uB2E4\uB978\
  \ \uD14D\uC2A4\uD2B8\uB85C \uBC14\uAFB8\uB294 \uC77C\uC785\uB2C8\uB2E4. \uD504\uB85C\
  \uADF8\uB798\uBA38\uB4E4\uC740 \uC790\uB3D9\uD654, \uB370\uC774\uD130 \uC815\uC81C\
  , \uCF54\uB4DC \uB9AC\uD329\uD1A0\uB9C1 \uB4F1 \uB2E4\uC591\uD55C \uC774\uC720\uB85C\
  \ \uC774 \uC791\uC5C5\uC744 \uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: 2024-02-18 23:09:05.602538
model: gpt-4-1106-preview
summary: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9\uACFC \uAD50\uCCB4\uB294 \uBB38\uC790\uC5F4\
  \ \uB0B4\uC5D0\uC11C \uD2B9\uC815 \uD328\uD134\uC744 \uCC3E\uC544 \uB2E4\uB978 \uD14D\
  \uC2A4\uD2B8\uB85C \uBC14\uAFB8\uB294 \uC77C\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\
  \uB798\uBA38\uB4E4\uC740 \uC790\uB3D9\uD654, \uB370\uC774\uD130 \uC815\uC81C, \uCF54\
  \uB4DC \uB9AC\uD329\uD1A0\uB9C1 \uB4F1 \uB2E4\uC591\uD55C \uC774\uC720\uB85C \uC774\
  \ \uC791\uC5C5\uC744 \uD569\uB2C8\uB2E4."
title: "\uD14D\uC2A4\uD2B8 \uAC80\uC0C9 \uBC0F \uAD50\uCCB4"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)

텍스트 검색과 교체는 문자열 내에서 특정 패턴을 찾아 다른 텍스트로 바꾸는 일입니다. 프로그래머들은 자동화, 데이터 정제, 코드 리팩토링 등 다양한 이유로 이 작업을 합니다.

## How to (방법)

Python에서 텍스트를 검색하고 교체하는 가장 간단한 방법은 `replace()` 메소드를 사용하는 것입니다.

```python
text = "안녕하세요! 파이썬은 재밌습니다."
new_text = text.replace("재밌습니다", "쉽습니다")
print(new_text)
```

```
안녕하세요! 파이썬은 쉽습니다.
```

정규 표현식을 사용하면 더 복잡한 패턴을 다룰 수 있습니다.

```python
import re

text = "My phone number is 010-1234-5678."
pattern = r'\d{3}-\d{4}-\d{4}'
new_text = re.sub(pattern, "REDACTED", text)
print(new_text)
```

```
My phone number is REDACTED.
```

## Deep Dive (심층 분석)

텍스트 검색과 교체는 프로그래밍의 역사와 함께 시작되었습니다. 초기 텍스트 편집기들로부터 시작해 모든 현대 IDE와 텍스트 처리 라이브러리의 기본 기능이 되었죠.

다른 방법들도 있습니다:
- `str.find()` 또는 `str.index()`를 사용해 위치를 찾고 슬라이싱으로 교체
- 파이썬의 `re` 모듈을 사용한 정규 표현식

정규 표현식은 강력하지만 느릴 수 있고 복잡해질 수 있습니다. `replace()`는 빠르고 간단할 때 가장 좋습니다.

## See Also (참고 자료)

- Python 문자열 메소드: https://docs.python.org/3/library/stdtypes.html#string-methods
- 파이썬 정규 표현식 모듈 `re`: https://docs.python.org/3/library/re.html
- 정규 표현식에 대한 더 깊이 있는 학습: https://www.regular-expressions.info/tutorial.html
