---
date: 2024-01-20 17:37:32.325879-07:00
description: "\uB0A0\uC9DC\uB97C \uBB38\uC790\uC5F4\uB85C \uBCC0\uD658\uD558\uB294\
  \ \uAC83\uC740 \uB0A0\uC9DC \uB370\uC774\uD130\uB97C \uC27D\uAC8C \uC77D\uC744 \uC218\
  \ \uC788\uB294 \uD14D\uC2A4\uD2B8 \uD615\uD0DC\uB85C \uBC14\uAFB8\uB294 \uC791\uC5C5\
  \uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC0AC\uC6A9\uC790\
  \ \uC778\uD130\uD398\uC774\uC2A4\uC5D0 \uD45C\uC2DC\uD558\uAC70\uB098, \uB370\uC774\
  \uD130\uB97C \uB85C\uAE45 \uBC0F \uC11C\uBC84 \uC804\uC1A1\uC744 \uC704\uD574 \uC774\
  \uB7F0 \uBCC0\uD658\uC744 \uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.747945-06:00'
model: gpt-4-1106-preview
summary: "\uB0A0\uC9DC\uB97C \uBB38\uC790\uC5F4\uB85C \uBCC0\uD658\uD558\uB294 \uAC83\
  \uC740 \uB0A0\uC9DC \uB370\uC774\uD130\uB97C \uC27D\uAC8C \uC77D\uC744 \uC218 \uC788\
  \uB294 \uD14D\uC2A4\uD2B8 \uD615\uD0DC\uB85C \uBC14\uAFB8\uB294 \uC791\uC5C5\uC785\
  \uB2C8\uB2E4."
title: "\uB0A0\uC9DC\uB97C \uBB38\uC790\uC5F4\uB85C \uBCC0\uD658\uD558\uAE30"
weight: 28
---

## How to: (방법)
Swift에서 날짜를 문자열로 변환하려면 `DateFormatter`를 사용합니다. 아래의 예시를 참고하세요.

```Swift
import Foundation

// 날짜 생성하기
let now = Date()

// DateFormatter 인스턴스 생성
let dateFormatter = DateFormatter()

// 변환 형식 설정하기
dateFormatter.dateFormat = "yyyy-MM-dd HH:mm:ss"

// Date -> String 변환
let dateString = dateFormatter.string(from: now)

// 출력
print(dateString) // "2023-04-05 14:23:36" 예시 출력
```

`dateFormat`은 날짜와 시간의 형식을 결정합니다. 적절한 형식 문자열을 사용하여 원하는 출력을 얻을 수 있습니다.

## Deep Dive (심층 분석)
날짜 형식 변환은 프로그래밍 초기부터 필요한 기능이었습니다. 표준화된 날짜 및 시간 형식이 필요한 사용 사례가 늘면서, 여러 프로그래밍 언어는 이를 위한 도구를 갖추게 되었습니다.

Swift는 `DateFormatter`를 제공하여 날짜와 문자열 간의 변환을 가능하게 합니다. `dateFormat`에서 사용하는 형식 문자열은 Unicode 기술 표준인 'Date Format Patterns'을 기반으로 합니다.

`DateFormatter` 이외에도 `ISO8601DateFormatter`가 있으며, 특히 ISO 8601 날짜 형식 변환에 최적화되어 있습니다. JSON과 같은 데이터 형식과 일할 때 유용하죠.

```Swift
import Foundation

// ISO8601DateFormatter 인스턴스 생성
let isoFormatter = ISO8601DateFormatter()

// Date -> String 변환
let isoDateString = isoFormatter.string(from: now)

// 출력
print(isoDateString) // "2023-04-05T14:23:36Z" 예시 출력
```

또한, Swift의 `Date`와 `String` 변환은 시스템의 지역 설정이나 시간대 영향을 받을 수 있습니다. 이런 변수를 적절히 관리하는 것은 국제화된 앱에서 중요합니다.

## See Also (참고하기)
- Apple Date Formatting Guide: [https://developer.apple.com/documentation/foundation/dateformatter](https://developer.apple.com/documentation/foundation/dateformatter)
- Unicode Date Format Patterns: [http://unicode.org/reports/tr35/tr35-25.html#Date_Format_Patterns](http://unicode.org/reports/tr35/tr35-25.html#Date_Format_Patterns)
- Swift `Date` and `Calendar` Documentation: [https://developer.apple.com/documentation/foundation/date](https://developer.apple.com/documentation/foundation/date)
