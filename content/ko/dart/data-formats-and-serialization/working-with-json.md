---
title:                "JSON과 작업하기"
date:                  2024-03-08T21:57:51.656567-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

JSON(JavaScript Object Notation)을 사용하는 것은 문자열에서 Dart 객체로 JSON 데이터를 파싱하거나 반대로 하는 일반적인 작업이며, 웹과 앱 개발에서 데이터 교환을 위해 수행됩니다. 프로그래머들은 이를 API에서 데이터를 효율적으로 다루거나, 설정 또는 앱 내 컴포넌트 간의 통신을 위해 수행합니다.

## 어떻게 사용하나요?

Dart는 `dart:convert` 라이브러리를 통해 JSON을 지원하며, JSON을 인코드하고 디코드하는 것을 직관적으로 만듭니다. 아래 예제는 기본적인 작업을 보여줍니다:

**JSON 문자열을 Dart 객체로 파싱하기:**
```dart
import 'dart:convert';

void main() {
  // 예제 JSON 문자열
  String jsonString = '{"name": "John", "age": 30, "email": "john@example.com"}';
  
  // JSON을 Dart Map으로 디코딩
  Map<String, dynamic> user = jsonDecode(jsonString);
  
  print('안녕하세요, ${user['name']}님! 나이는 ${user['age']}세입니다.');
  // 출력: 안녕하세요, John님! 나이는 30세입니다.
}
```

**Dart 객체를 JSON 문자열로 인코딩하기:**
```dart
import 'dart:convert';

void main() {
  // 예제 Dart 객체
  Map<String, dynamic> user = {
    'name': 'Jane',
    'age': 25,
    'email': 'jane@example.com'
  };
  
  // Dart Map을 JSON으로 인코딩
  String jsonString = jsonEncode(user);
  
  print(jsonString);
  // 출력: {"name":"Jane","age":25,"email":"jane@example.com"}
}
```

**복잡한 모델을 위한 `json_serializable` 사용하기:**
복잡한 데이터 모델의 경우, 수동 직렬화는 번거로울 수 있습니다. `json_serializable` 패키지는 이 과정을 자동화합니다. 추가 설정이 필요하며, `pubspec.yaml`에 의존성을 추가하고 빌드 파일을 생성하는 것을 포함합니다. 설정 후에는 다음과 같이 사용할 수 있습니다:

1. 주석으로 모델 정의하기:
```dart
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

@JsonSerializable()
class User {
  String name;
  int age;
  String email;
  
  User({required this.name, required this.age, required this.email});
  
  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);
  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```

2. 직렬화 보일러플레이트 생성하기:
빌드 러너 명령을 사용하여 `user.g.dart` 파일을 생성합니다:
```shell
flutter pub run build_runner build
```

3. 모델 사용하기:
```dart
void main() {
  // JSON을 User로 파싱
  Map userMap = jsonDecode('{"name": "John", "age": 30, "email": "john@example.com"}');
  User user = User.fromJson(userMap);
  
  print('User: ${user.name}, Age: ${user.age}');
  // 출력: User: John, Age: 30

  // User를 다시 JSON으로 변환
  String jsonString = jsonEncode(user.toJson());
  print(jsonString);
  // 출력: {"name":"John","age":30,"email":"john@example.com"}
}
```

이 예시들은 Dart에서의 기본 및 고급 JSON 상호 작용을 보여주며, 개발자들이 애플리케이션에서 데이터 직렬화 작업을 원활하게 처리할 수 있도록 합니다.
