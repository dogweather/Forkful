---
title:                "새 프로젝트 시작하기"
date:                  2024-03-08T21:56:57.451408-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

Dart로 새 프로젝트를 시작하는 것은 효율적인 개발, 테스팅, 배포를 위한 환경을 설정하는 것을 포함합니다. 프로그래머들은 Dart의 최적의 성능과 특히 Flutter와 같은 프레임워크를 사용한 웹 및 모바일 앱 개발에 적합한 강력한 생태계를 활용하기 위해 새 Dart 프로젝트를 시작합니다.

## 방법:

1. **Dart 설치하기**:
   시스템에 Dart가 설치되어 있는지 확인하세요. 설치되어 있지 않다면, [https://dart.dev/get-dart](https://dart.dev/get-dart)에서 다운로드할 수 있습니다. 설치를 확인하려면:

   ```shell
   dart --version
   ```

2. **새 Dart 프로젝트 만들기**:
   Dart CLI를 사용하여 새 프로젝트를 생성하세요:

   ```shell
   dart create hello_dart
   ```

   이 명령은 선택한 내용에 따라 간단한 샘플 웹 또는 콘솔 애플리케이션을 포함한 새로운 디렉토리 `hello_dart`를 생성합니다.

3. **프로젝트 구조 검토하기**:
   
   프로젝트 디렉토리로 이동하세요:

   ```shell
   cd hello_dart
   ```

   일반적인 Dart 프로젝트에는 다음과 같은 주요 파일 및 디렉토리가 포함됩니다:

   - `pubspec.yaml`: 프로젝트의 의존성과 SDK 제약을 포함하는 구성 파일.
   - `lib/`: 대부분의 Dart 코드가 위치한 디렉토리.
   - `test/`: 프로젝트 테스트를 위한 디렉토리.

4. **의존성 추가하기**:
   `pubspec.yaml`를 수정하여 의존성을 추가하세요. 웹 프로젝트의 경우, HTTP 요청을 만들기 위한 인기 있는 패키지인 `http`를 추가하는 것을 고려하세요:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     http: ^0.13.3
   ```

   수정 후, 의존성을 가져오세요:

   ```shell
   dart pub get
   ```

5. **첫 Dart 코드 작성하기**:
   
   `lib/` 디렉토리에 새 Dart 파일인 `main.dart`를 만들고 간단한 Dart 코드를 추가하세요:

   ```dart
   // Dart 코어 라이브러리를 가져옴
   import 'dart:core';

   void main() {
     print('Hello, Dart!');
   }
   ```

6. **Dart 애플리케이션 실행하기**:

   다음을 사용하여 Dart 프로그램을 실행하세요:

   ```shell
   dart run
   ```

   출력 내용은 다음과 같아야 합니다:

   ```
   Hello, Dart!
   ```

이 단계를 따르면, 설치부터 첫 Dart 코드를 실행하기까지 새로운 Dart 프로젝트를 성공적으로 시작했습니다. 이 기초 지식은 규모가 큰 애플리케이션을 개발하기 위한 Dart의 풍부한 생태계와 그 능력에 더 깊이 뛰어들 기반을 마련합니다.
