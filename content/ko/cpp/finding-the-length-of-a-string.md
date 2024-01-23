---
title:                "문자열의 길이 찾기"
date:                  2024-01-20T17:47:19.626135-07:00
model:                 gpt-4-1106-preview
simple_title:         "문자열의 길이 찾기"
programming_language: "C++"
category:             "C++"
tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/cpp/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
문자열의 길이를 찾는 것은 개수를 셉니다. 프로그래머들은 데이터 처리나 유효성 검사할 때 이 정보가 필요합니다.

## How to: (어떻게: )
C++에는 `std::string`의 `size()` 혹은 `length()` 메소드를 사용하여 문자열 길이를 쉽게 찾을 수 있습니다.

```C++
#include <iostream>
#include <string>

int main() {
    std::string myString = "안녕하세요!";
    std::cout << "문자열의 길이: " << myString.size() << std::endl; // size() 사용
    std::cout << "문자열의 길이: " << myString.length() << std::endl; // length() 사용
    return 0;
}

// 출력:
// 문자열의 길이: 6
// 문자열의 길이: 6
```

## Deep Dive (심층 탐구)
C++에서 문자열 길이를 찾는 방법은 `std::string`의 도입과 함께 C++의 표준 일부가 되었습니다. 이전 C 스타일 문자열에서는 `strlen()` 함수를 사용해야 했습니다. 이 함수는 문자열 끝의 널 문자(`'\0'`)를 찾을 때까지 루프를 돌며 길이를 계산합니다. `std::string`에 내장된 `size()`와 `length()` 메소드는 내부적으로 문자열의 길이를 저장하고 바로 반환하므로, `strlen()`보다 효율적입니다. 두 메소드는 기능적으로 동일합니다. 

C++17 부터는 `std::string_view`가 등장하여 메모리 할당 없이 문자열을 참조할 수 있게 해주며, 여기서도 `size()` 메소드를 사용하여 길이를 알 수 있습니다. 표현식 `myString.size()`는 상수 시간 복잡도 O(1)로 실행됩니다.

## See Also (참고 자료)
- C++ std::string reference: https://cplusplus.com/reference/string/string/
- C++ std::string_view reference: https://cplusplus.com/reference/string_view/string_view/
- C-style strings and strlen: https://cplusplus.com/reference/cstring/strlen/
