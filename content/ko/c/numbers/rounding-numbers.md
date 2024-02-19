---
aliases:
- /ko/c/rounding-numbers/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:07:48.352485-07:00
description: "\uC22B\uC790 \uBC18\uC62C\uB9BC\uC740 \uD2B9\uC815 \uADDC\uCE59\uC5D0\
  \ \uB530\uB77C \uC22B\uC790\uC758 \uC790\uB9BF\uC218\uB97C \uC870\uC815\uD558\uC5EC\
  \ \uAC00\uC7A5 \uAC00\uAE4C\uC6B4 \uC815\uC218 \uB610\uB294 \uC9C0\uC815\uB41C \uC18C\
  \uC218\uC810 \uC790\uB9AC\uC218\uB85C \uC815\uBC00\uB3C4\uB97C \uC904\uC774\uB294\
  \ \uACFC\uC815\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC800\
  \uC7A5\uACF5\uAC04\uC758 \uD544\uC694\uB7C9\uC744 \uC81C\uD55C\uD558\uAC70\uB098\
  , \uC0AC\uC6A9\uC790\uAC00 \uBCF4\uAE30\uC5D0 \uB2E8\uC21C\uD654\uB41C \uCD9C\uB825\
  \uC744 \uC81C\uACF5\uD558\uAC70\uB098, \uB9E4\uC6B0 \uC791\uC740 \uBCC0\uB3D9\uC5D0\
  \ \uBBFC\uAC10\uD55C \uC815\uD655\uD55C \uC218\uD559 \uC5F0\uC0B0\uC744 \uBCF4\uC7A5\
  \uD558\uAE30\u2026"
lastmod: 2024-02-18 23:09:06.942638
model: gpt-4-0125-preview
summary: "\uC22B\uC790 \uBC18\uC62C\uB9BC\uC740 \uD2B9\uC815 \uADDC\uCE59\uC5D0 \uB530\
  \uB77C \uC22B\uC790\uC758 \uC790\uB9BF\uC218\uB97C \uC870\uC815\uD558\uC5EC \uAC00\
  \uC7A5 \uAC00\uAE4C\uC6B4 \uC815\uC218 \uB610\uB294 \uC9C0\uC815\uB41C \uC18C\uC218\
  \uC810 \uC790\uB9AC\uC218\uB85C \uC815\uBC00\uB3C4\uB97C \uC904\uC774\uB294 \uACFC\
  \uC815\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC800\uC7A5\
  \uACF5\uAC04\uC758 \uD544\uC694\uB7C9\uC744 \uC81C\uD55C\uD558\uAC70\uB098, \uC0AC\
  \uC6A9\uC790\uAC00 \uBCF4\uAE30\uC5D0 \uB2E8\uC21C\uD654\uB41C \uCD9C\uB825\uC744\
  \ \uC81C\uACF5\uD558\uAC70\uB098, \uB9E4\uC6B0 \uC791\uC740 \uBCC0\uB3D9\uC5D0 \uBBFC\
  \uAC10\uD55C \uC815\uD655\uD55C \uC218\uD559 \uC5F0\uC0B0\uC744 \uBCF4\uC7A5\uD558\
  \uAE30\u2026"
title: "\uC22B\uC790 \uBC18\uC62C\uB9BC"
---

{{< edit_this_page >}}

## 무엇인가 & 왜인가?

숫자 반올림은 특정 규칙에 따라 숫자의 자릿수를 조정하여 가장 가까운 정수 또는 지정된 소수점 자리수로 정밀도를 줄이는 과정입니다. 프로그래머들은 저장공간의 필요량을 제한하거나, 사용자가 보기에 단순화된 출력을 제공하거나, 매우 작은 변동에 민감한 정확한 수학 연산을 보장하기 위해 이러한 작업을 수행합니다.

## 방법:

C에서 숫자를 반올림하는 방법은 다양한 함수를 사용할 수 있지만, 가장 일반적인 접근 방식은 `floor()`, `ceil()`, 그리고 `round()` 함수를 사용하는 것입니다. 이 함수들은 표준 수학 라이브러리의 일부이므로, 프로그램에 `math.h`를 포함해야 합니다.

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 9.527;

    // floor()를 사용하여 내림
    double floorResult = floor(num);
    printf("floor(9.527) = %.0f\n", floorResult);

    // ceil()를 사용하여 올림
    double ceilResult = ceil(num);
    printf("ceil(9.527) = %.0f\n", ceilResult);

    // round()를 사용하여 가장 가까운 정수로 반올림
    double roundResult = round(num);
    printf("round(9.527) = %.0f\n", roundResult);

    // 소수점 지정 자리수로 반올림하기 위해서는 곱셈과 나눗셈을 포함합니다.
    double twoDecimalPlaces = round(num * 100) / 100;
    printf("소수점 두 자리로 반올림: %.2f\n", twoDecimalPlaces);

    return 0;
}
```

출력:
```
floor(9.527) = 9
ceil(9.527) = 10
round(9.527) = 10
소수점 두 자리로 반올림: 9.53
```

## 심층 분석

숫자 반올림은 수학과 계산에서 깊은 역사적 뿌리를 가지고 있으며, 이론적 및 적용적 측면에서 모두 중요합니다. C에서 `floor()`, `ceil()`, `round()`는 기본적인 기능을 제공하지만, 부동 소수점 숫자의 이진 표현으로 인해 실수를 정수나 특정 소수점 자리수로 반올림하는 본질은 이진수로 정확히 표현할 수 없는 숫자(예: 0.1)를 처리하는 방식으로 인해 예상치 못한 결과를 초래할 수 있어 더 세밀합니다.

이 함수들은 C 표준 라이브러리에 `<math.h>`에 정의되어 있습니다. 숫자를 반올림할 때, 특히 재정 또는 정밀한 공학 계산을 위해 이진 부동 소수점 숫자를 사용하는 것의 함의를 고려해야 합니다. 매우 정확하거나 특정 소수점 반올림이 필요한 경우, 사용자 정의 반올림 함수를 구현하거나, GMP 또는 MPFR과 같이 임의 정밀도 산술을 위해 설계된 라이브러리를 사용할 수 있지만, 이것은 추가적인 복잡성과 의존성을 도입합니다.

실제로, C에서 반올림에 대한 올바른 접근 방식을 선택하는 것은 정밀도, 성능, 실용성의 필요성을 균형잡고, 개발 중인 응용 프로그램의 도메인별 요구사항을 잘 이해하는 것을 포함합니다.
