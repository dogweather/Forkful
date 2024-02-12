---
title:                "숫자 반올림"
aliases:
- /ko/google-apps-script/rounding-numbers/
date:                  2024-02-01T22:00:57.539720-07:00
model:                 gpt-4-0125-preview
simple_title:         "숫자 반올림"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/google-apps-script/rounding-numbers.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇이며 왜?

숫자 반올림은 컴퓨터 프로그래밍의 기본 개념으로, 숫자를 가장 가까운 정수나 지정된 소수점 자릿수로 조정하는 것을 말합니다. 프로그래머들은 숫자를 인간이 읽기 쉽게 단순화하거나 특정 계산 요구사항을 충족시키기 위해 종종 반올림을 수행하여 정확도를 보장하고 계산 부하를 줄입니다.

## 방법:

Google Apps Script는 JavaScript 기반 언어로, 숫자 반올림에 대한 표준 방법을 제공합니다. 자주 사용되는 세 가지 기술을 분석해보겠습니다:

### Math.round()
이 함수는 숫자를 가장 가까운 정수로 반올림합니다.

```javascript
var number = 2.56;
var roundedNumber = Math.round(number); 
Logger.log(roundedNumber); // 출력: 3
```

### Math.ceil()
숫자를 반올림하여 가장 가까운 정수로 올립니다.

```javascript
var number = 2.56;
var roundedUp = Math.ceil(number); 
Logger.log(roundedUp); // 출력: 3
```

### Math.floor()
반대로, 숫자를 반올림하여 가장 가까운 정수로 내립니다.

```javascript
var number = 2.56;
var roundedDown = Math.floor(number); 
Logger.log(roundedDown); // 출력: 2
```

특정 소수점 자릿수에 대해서는, 실제로 문자열을 반환하는 `.toFixed()`를 사용하거나 수학적 반올림에 대한 더 세밀한 접근 방식을 사용할 수 있습니다:

```javascript
var number = 2.56789;
var fixedNumber = number.toFixed(2); 
Logger.log(fixedNumber); // 출력: "2.57"(문자열로서)

var preciseRound = Math.round(number * 100) / 100; 
Logger.log(preciseRound); // 출력: 2.57
```

## 심층 탐구

Google Apps Script에서 숫자를 반올림하는 것은 다른 JavaScript 환경에서 수행되는 작업과 크게 다르지 않습니다. 하지만 반올림 방법의 차이와 부동소수점 산술 문제에 대한 잠재성을 이해하는 것이 중요합니다. 예를 들어, 컴퓨터가 부동소수점을 표현하는 방식으로 인해 모든 소수점 분수를 완벽한 정확도로 표현할 수 없어 때때로 예상치 못한 반올림 결과를 초래할 수 있습니다.

역사적으로, JavaScript(따라서 Google Apps Script 포함)는 부동소수점 산술에 사용되는 다른 많은 프로그래밍 언어와 마찬가지로 IEEE 754 표준을 준수하여 처리합니다. 이 표준은 숫자가 어떻게 반올림되는지 정의하여 다양한 플랫폼 및 언어간에 일관성을 보장합니다.

Google Apps Script에서의 직접적인 반올림 방법은 간단하고 종종 충분하지만, 복잡하거나 고정밀 응용 프로그램은 decimal.js 또는 big.js와 같이 임의 정밀도 산술을 처리하도록 설계된 라이브러리의 이점을 볼 수 있습니다. 이러한 라이브러리는 반올림된 숫자의 정확도가 매우 중요한 재무나 과학 계산에서 작업할 때 특히 유용할 수 있습니다.

단, Google Apps Script에서 외부 라이브러리를 활용하려면 스크립트 편집기를 통해 라이브러리를 로드해야 하므로, 사용 방법에 따라 스크립트의 의존성이나 성능에 영향을 줄 수 있습니다. 많은 경우에 내장된 Math 메소드만으로 충분하지만, nth 정도의 정밀함이 요구되는 경우에는 표준 라이브러리를 넘어서 필요할 수 있습니다.
