---
title:                "YAML로 작업하기"
date:                  2024-03-08T21:57:43.282536-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇이며 왜 사용하는가?

YAML은 "YAML Ain't Markup Language"의 약자로, 인간이 읽을 수 있는 데이터 직렬화 포맷을 말합니다. 프로그래머들은 설정 파일, 데이터 교환 그리고 데이터를 쉽게 이해할 수 있는 포맷으로 저장하거나 전송해야 하는 애플리케이션에서 이를 사용합니다.

## 어떻게 사용하는가:

Dart에서 YAML을 다루는 것은 주로 내장 YAML 파싱 기능이 없기 때문에 제3자 라이브러리를 사용하는 것을 의미합니다. 인기 있는 선택 중 하나는 `yaml` 패키지입니다. 시작하려면, 이 패키지를 `pubspec.yaml`에 추가해야 합니다:

```yaml
dependencies:
  yaml: ^3.1.0
```

패키지를 가져오기 위해 `pub get`을 실행하는 것을 잊지 마세요.

### YAML 읽기

YAML 파일을 읽으려면, 먼저 `yaml` 패키지를 import하고 `loadYaml` 함수를 사용합니다:

```dart
import 'package:yaml/yaml.dart';
import 'dart:io';

void main() {
  final file = File('config.yaml').readAsStringSync();
  final yamlMap = loadYaml(file);

  print(yamlMap['name']); // 출력: John Doe
}

```

여러분의 `config.yaml` 파일이 다음과 같다고 가정합니다:

```yaml
name: John Doe
age: 30
```

### YAML 쓰기

`yaml` 패키지는 파싱에는 좋지만 YAML을 쓰는 것을 지원하지 않습니다. 그러므로, 데이터를 수동으로 YAML로 변환하거나 가능한 다른 패키지를 사용할 수도 있습니다. 또는, 보다 직관적으로 데이터 변환을 관리하고 YAML 문법에 맞는 문자열로 출력하는 것입니다:

```dart
Map<String, dynamic> data = {
  'name': 'Jane Doe',
  'age': 29,
};

String toYamlString(Map<String, dynamic> map) {
  String yaml = '';
  map.forEach((key, value) {
    yaml += '$key: $value\n';
  });
  return yaml;
}

void main() {
  print(toYamlString(data)); // 출력: name: Jane Doe
                             //         age: 29
}
```

이는 기본적인 접근 방법이며 복잡한 데이터 구조나 특별한 YAML 기능을 필요로 하는 경우에는 적합하지 않을 수 있습니다. 정교한 요구를 가진 경우, 보다 포괄적인 Dart 패키지를 찾거나 기여해야 할 수도 있습니다.
