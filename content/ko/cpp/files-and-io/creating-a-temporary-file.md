---
date: 2024-01-20 17:40:14.177051-07:00
description: "\uC784\uC2DC \uD30C\uC77C \uC0DD\uC131\uC740 \uB370\uC774\uD130\uB97C\
  \ \uC77C\uC2DC\uC801\uC73C\uB85C \uC800\uC7A5\uD558\uAE30 \uC704\uD574 \uC0AC\uC6A9\
  \uD569\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB294 \uC8FC\uB85C \uD14C\uC2A4\
  \uD2B8, \uB370\uC774\uD130 \uAD50\uD658, \uB610\uB294 \uD070 \uD30C\uC77C \uCC98\
  \uB9AC \uC2DC \uC784\uC2DC \uC800\uC7A5\uACF5\uAC04\uC73C\uB85C \uC0AC\uC6A9\uD558\
  \uAE30 \uC704\uD574 \uC774\uB97C \uC0DD\uC131\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.697996-06:00'
model: gpt-4-1106-preview
summary: "\uC784\uC2DC \uD30C\uC77C \uC0DD\uC131\uC740 \uB370\uC774\uD130\uB97C \uC77C\
  \uC2DC\uC801\uC73C\uB85C \uC800\uC7A5\uD558\uAE30 \uC704\uD574 \uC0AC\uC6A9\uD569\
  \uB2C8\uB2E4."
title: "\uC784\uC2DC \uD30C\uC77C \uC0DD\uC131\uD558\uAE30"
weight: 21
---

## How to: (어떻게 하나요?)
```C++
#include <cstdio>
#include <filesystem>

int main() {
    // 임시 파일 생성
    char temp_name[] = "tempfile-XXXXXX"; // XXXXXX 부분이 고유한 문자열로 대체됩니다.
    int file_descriptor = mkstemp(temp_name);
    
    if (file_descriptor != -1) {
        // 성공 메시지 출력
        printf("임시 파일이 생성되었습니다: %s\n", temp_name);
        
        // 파일 사용 후 제거
        std::filesystem::remove(temp_name);
    } else {
        // 에러 메시지 출력
        perror("임시 파일을 생성할 수 없습니다");
    }
    return 0;
}
```

**출력 예제**:
```
임시 파일이 생성되었습니다: tempfile-1b2e34
```

## Deep Dive (심층 분석)
임시 파일은 자동 삭제가 필요 없는 경우에 주로 사용됩니다. 과거에는 주로 `tmpnam` 또는 `tempnam` 함수를 사용했지만, 이런 함수들은 보안 문제로 권장되지 않습니다. C++17 부터는 `<filesystem>` 라이브러리의 `std::filesystem::temp_directory_path`함수를 통해 현재 시스템의 임시 디렉토리 경로를 얻을 수 있으며 이를 활용해 파일 경로를 생성할 수도 있습니다.

POSIX 시스템에서는 `mkstemp` 함수가 자주 쓰이며 고유한 파일명을 생성하고 해당 파일을 안전하게 열 수 있습니다. 파일이 열렸다면 반환된 파일 디스크립터를 통해 안전하게 파일 I/O 작업을 할 수 있습니다. 고유한 파일명 생성이 보안상 중요한 이유는 누군가가 예측 가능한 이름을 알고 있다면, 파일 생성 전에 미리 그 이름을 사용해 악의적인 공격을 할 수 있기 때문입니다.

`<cstdio>` 라이브러리는 C 기반 함수를 제공하며, C++에서는 이 라이브러리를 이용해서도 파일 작업을 할 수 있습니다. 하지만 C++은 자체 파일 핸들링 기능을 더 많이 제공하니, 여러분의 프로젝트 요구사항에 맞춰 적합한 방식을 선택하세요.

## See Also (참고 자료)
- C++ Filesystem Library: https://en.cppreference.com/w/cpp/filesystem
- C++ mkstemp: https://www.cplusplus.com/reference/cstdio/tmpfile/
- C++ 보안 강화된 임시 파일 생성: https://www.cplusplus.com/articles/j3wTURfi/
