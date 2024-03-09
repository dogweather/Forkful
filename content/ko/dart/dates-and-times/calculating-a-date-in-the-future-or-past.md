---
title:                "미래 또는 과거의 날짜 계산하기"
date:                  2024-03-08T21:53:39.215374-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?
프로그래머에게 미래 또는 과거의 날짜를 계산하는 것은 일정 관리, 리마인더 설정, 날짜 계산에 의존하는 기능 처리 등에 있어서 흔한 작업입니다. 날짜를 조작하는 방법을 이해하는 것은 백엔드 시스템, 사용자 인터페이스, 데이터 분석에 있어서 중요하며, 특히 Dart로 전환하는 사람들에게 시간적 논리를 효율적으로 구현하는 데에 있어서 중요합니다.

## 방법:
Dart는 `DateTime` 클래스를 통해 날짜 조작을 위한 강력한 지원을 제공합니다. 여기 Dart만을 사용하여 제3자 라이브러리가 필요 없이 미래 또는 과거의 날짜를 계산하는 방법이 있습니다.

### 미래 날짜 계산하기
미래의 날짜를 계산하기 위해, `DateTime` 객체를 생성하고 원하는 기간과 함께 `add` 메서드를 사용합니다.

```dart
DateTime today = DateTime.now();
Duration tenDays = Duration(days: 10);
DateTime futureDate = today.add(tenDays);

print(futureDate); // 출력: 2023-04-21 14:22:35.123456 (예시 출력, 현재 날짜와 시간에 따라 다름)
```

### 과거 날짜 계산하기
과거의 날짜를 계산하기 위해, 필요한 기간을 가진 `DateTime` 객체에 `subtract` 메서드를 사용합니다.

```dart
DateTime today = DateTime.now();
Duration fifteenDaysAgo = Duration(days: 15);
DateTime pastDate = today.subtract(fifteenDaysAgo);

print(pastDate); // 출력: 2023-03-27 14:22:35.123456 (예시 출력, 현재 날짜와 시간에 따라 다름)
```

### 제3자 라이브러리 사용하기
Dart의 기본 날짜 조작 기능이 강력하지만, 날짜를 더 쉽게 파싱하거나 형식을 지정하거나 복잡한 계산을 수행하는 등 더 구체적인 작업이 필요할 수 있습니다. 이러한 경우, `time` 패키지가 매우 유용할 수 있습니다.

먼저, `pubspec.yaml` 의존성에 `time`을 추가합니다:

```yaml
dependencies:
  time: ^2.0.0
```

그런 다음, 유사한 계산을 더 읽기 쉽게 수행할 수 있습니다:

```dart
import 'package:time/time.dart';

void main() {
  DateTime today = DateTime.now();

  // 미래 날짜 계산하기
  DateTime futureDate = today + 10.days;
  print(futureDate); // 출력 형식: 2023-04-21 14:22:35.123456

  // 과거 날짜 계산하기
  DateTime pastDate = today - 15.days;
  print(pastDate); // 출력 형식: 2023-03-27 14:22:35.123456
}
```

이 예시들은 Dart에서의 기본적인 날짜 조작을 보여줍니다. 현재 날짜에 시간을 더하거나 빼는 것을 포함해, 얼마나 쉽게 Dart 애플리케이션에서 날짜를 관리할 수 있는지를 보여줍니다.
