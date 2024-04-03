---
date: 2024-01-26 03:44:02.376206-07:00
description: "\uC22B\uC790\uB97C \uBC18\uC62C\uB9BC\uD558\uB294 \uAC83\uC740 \uB2E8\
  \uC21C\uD654\uD558\uAC70\uB098 \uD2B9\uC815\uD55C \uC815\uBC00\uB3C4\uC5D0 \uB9DE\
  \uCD94\uAE30 \uC704\uD574 \uADF8 \uAC12\uB4E4\uC744 \uAC00\uAE4C\uC6B4 \uAC12\uC73C\
  \uB85C \uC870\uC815\uD558\uB294 \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4. \uC774\uB294\
  \ \uAC00\uB3C5\uC131\uC744 \uD5A5\uC0C1\uC2DC\uD0A4\uAC70\uB098 \uC800\uC7A5 \uACF5\
  \uAC04\uC744 \uC904\uC774\uAC70\uB098, \uAC00\uC7A5 \uAC00\uAE4C\uC6B4 \uC13C\uD2B8\
  \uB85C \uBC18\uC62C\uB9BC\uD558\uACE0 \uC2F6\uC740 \uB3C8 \uACC4\uC0B0\uACFC \uAC19\
  \uC740 \uB3C4\uBA54\uC778 \uD2B9\uC815 \uC694\uAD6C \uC0AC\uD56D\uC744 \uCDA9\uC871\
  \uC2DC\uD0A4\uB294 \uB370 \uC720\uC6A9\uD569\uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:54.714753-06:00'
model: gpt-4-0125-preview
summary: "\uC22B\uC790\uB97C \uBC18\uC62C\uB9BC\uD558\uB294 \uAC83\uC740 \uB2E8\uC21C\
  \uD654\uD558\uAC70\uB098 \uD2B9\uC815\uD55C \uC815\uBC00\uB3C4\uC5D0 \uB9DE\uCD94\
  \uAE30 \uC704\uD574 \uADF8 \uAC12\uB4E4\uC744 \uAC00\uAE4C\uC6B4 \uAC12\uC73C\uB85C\
  \ \uC870\uC815\uD558\uB294 \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4."
title: "\uC22B\uC790 \uBC18\uC62C\uB9BC\uD558\uAE30"
weight: 13
---

## 방법:
Elixir에서는 `Float.round/2`를 사용하여 부동 소수점 숫자를 반올림할 수 있습니다. 유지하고 싶은 소수점 자릿수를 지정할 수 있습니다. 작동 방식은 다음과 같습니다:

```elixir
# 소수점 없이 숫자 반올림
Float.round(3.14159) # => 3.0

# 소수점 2자리까지 숫자 반올림
Float.round(3.14159, 2) # => 3.14

# 소수점을 음수 정밀도로 반올림하여 가장 가까운 10으로 반올림
Float.round(123.456, -1) # => 120.0
```

## 깊이 알아보기
숫자를 반올림하는 것은 컴퓨터 과학에서 고전적인 문제입니다. 그만큼 반올림 전략의 선택은 금융 시스템, 과학 계산 등에 영향을 미칠 수 있습니다. Elixir의 `Float.round/2`는 수학 수업에서 배운 전통적인 반올림, 즉 "반올림"을 기본으로 합니다.

다른 유형의 반올림이 필요한 경우, Elixir는 직접 만들 수 있습니다. 예를 들어, "floor" 반올림(항상 내림) 또는 "ceiling" 반올림(항상 올림)을 고려해 보세요. 각각 `Float.floor/1` 또는 `Float.ceil/1`을 사용하면 됩니다.

```elixir
# Floor 반올림
Float.floor(3.999) # => 3.0

# Ceiling 반올림
Float.ceil(3.001) # => 4.0
```

이러한 대안들은 금융 계산, 그래픽 렌더링 또는 데이터 근사와 같은 애플리케이션의 정확한 요구 사항에 맞게 반올림을 맞춤화하는 데 도움이 됩니다.

## 또한 보기
Elixir의 반올림 함수와 부동 소수점 숫자에 대한 자세한 내용은:

- Elixir 공식 문서 중 `Float`: https://hexdocs.pm/elixir/Float.html
- 부동 소수점 산술에 대한 IEEE 표준 (IEEE 754): https://ieeexplore.ieee.org/document/4610935
