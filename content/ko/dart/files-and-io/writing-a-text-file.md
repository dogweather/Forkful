---
title:                "텍스트 파일 작성하기"
date:                  2024-03-08T21:57:59.965337-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?
Dart에서 텍스트 파일을 작성하는 것은 디스크에 파일을 생성하거나 수정하여 데이터를 읽을 수 있는 형식으로 저장하는 것을 포함합니다. 프로그래머들은 애플리케이션 데이터, 설정, 로그 또는 애플리케이션 실행 사이에 지속되어야 하는 정보나 다른 애플리케이션 또는 사용자와 데이터를 공유하기 위해 이러한 작업을 합니다.

## 방법:
Dart의 코어 라이브러리는 파일 처리를 위한 `dart:io` 패키지를 제공하여, 서드파티 라이브러리 없이 텍스트 파일을 작성할 수 있게 합니다. 다음은 텍스트 파일을 작성하는 간단한 예입니다:

```dart
import 'dart:io';

void main() async {
  // 현재 디렉토리에 'example.txt'라는 이름의 새 파일 생성
  var file = File('example.txt');
  
  // 파일에 문자열 작성
  await file.writeAsString('Hello, Dart!');
  
  // 내용 확인
  print(await file.readAsString()); // 출력: Hello, Dart!
}
```

큰 파일이나 데이터 스트림을 다룰 때는, `openWrite`을 사용하여 콘텐츠를 작성하는 것을 선호할 수 있으며, 이는 `IOSink`를 반환하고 데이터를 청크로 작성할 수 있게 합니다:

```dart
import 'dart:io';

void main() async {
  var file = File('large_file.txt');
  var sink = file.openWrite();

  // 파일에 여러 줄 작성
  sink
    ..writeln('Line 1: The quick brown fox jumps over the lazy dog.')
    ..writeln('Line 2: Dart is awesome!')
    ..close();

  // 모든 데이터가 파일에 작성되었는지 확인하려면 싱크가 닫힐 때까지 기다림
  await sink.done;

  // 내용을 읽고 인쇄하여 확인
  print(await file.readAsString());
}
```

파일에 추가하거나 바이트를 작성하는 것을 포함하여 보다 고급 파일 작업에 대해 탐구하려면, `dart:io`에 의해 제공되는 `File` 클래스 메소드를 더 깊이 살펴볼 수 있습니다. 또한, 대규모 또는 더 복잡한 프로젝트를 작업할 때는 파일 경로를 다루는 `path` 패키지나 웹 서버 기능을 위한 `shelf`와 같은 패키지를 고려하는 것이 유익할 수 있지만, 직접 파일 작성은 일반적으로 내장된 Dart 라이브러리에 의존합니다.
