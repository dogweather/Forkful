---
aliases:
- /ko/cpp/extracting-substrings/
date: 2024-01-20 17:45:11.315845-07:00
description: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uBD80\uBD84 \uBB38\uC790\uC5F4\uC744\
  \ \uCD94\uCD9C\uD558\uB294 \uAC83\uC740 \uD2B9\uC815 \uC870\uAC01\uC744 \uC120\uD0DD\
  \uD574 \uC0C8 \uBB38\uC790\uC5F4\uC744 \uB9CC\uB4DC\uB294 \uACFC\uC815\uC785\uB2C8\
  \uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uB370\uC774\uD130\uB97C \uD30C\
  \uC2F1\uD558\uAC70\uB098 \uD544\uC694\uD55C \uC815\uBCF4\uB9CC\uC744 \uBD84\uB9AC\
  \uD560 \uB54C \uC774 \uBC29\uBC95\uC744 \uC790\uC8FC \uC0AC\uC6A9\uD569\uB2C8\uB2E4\
  ."
isCJKLanguage: true
lastmod: 2024-02-18 23:09:06.666356
model: gpt-4-1106-preview
summary: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uBD80\uBD84 \uBB38\uC790\uC5F4\uC744 \uCD94\
  \uCD9C\uD558\uB294 \uAC83\uC740 \uD2B9\uC815 \uC870\uAC01\uC744 \uC120\uD0DD\uD574\
  \ \uC0C8 \uBB38\uC790\uC5F4\uC744 \uB9CC\uB4DC\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4\
  . \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uB370\uC774\uD130\uB97C \uD30C\uC2F1\
  \uD558\uAC70\uB098 \uD544\uC694\uD55C \uC815\uBCF4\uB9CC\uC744 \uBD84\uB9AC\uD560\
  \ \uB54C \uC774 \uBC29\uBC95\uC744 \uC790\uC8FC \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
title: "\uBD80\uBD84 \uBB38\uC790\uC5F4 \uCD94\uCD9C"
---

{{< edit_this_page >}}

## What & Why? (무엇 & 왜?)
문자열에서 부분 문자열을 추출하는 것은 특정 조각을 선택해 새 문자열을 만드는 과정입니다. 프로그래머들은 데이터를 파싱하거나 필요한 정보만을 분리할 때 이 방법을 자주 사용합니다.

## How to (방법)
```C++
#include <iostream>
#include <string>

int main() {
    std::string fullText = "Hello, C++ World!";
    std::string subText = fullText.substr(7, 3); // "C++" 추출

    std::cout << "Original string: " << fullText << std::endl;
    std::cout << "Extracted substring: " << subText << std::endl;

    return 0;
}
```
출력:
```
Original string: Hello, C++ World!
Extracted substring: C++
```

## Deep Dive (깊이 탐구)
`std::string` 안에 있는 `substr` 함수는 C++98부터 사용되어 왔습니다. 문자열을 다룰 때 기본적으로 제공하는 강력한 기능 중 하나죠. `substr` 함수는 두 개의 매개변수를 받아 첫 번째 매개변수는 시작 인덱스를, 두 번째 매개변수는 추출할 문자의 길이를 지정합니다. 

다른 방법도 있습니다. C++17부터는 `std::string_view`, 한정된 메모리 사용으로 문자열을 보다 효율적으로 다루게 도와주죠. 이것을 사용해도 문자열의 부분을 취급할 수 있습니다.

구현 세부사항을 살펴보면, `substr`은 새로운 문자열을 만들기 때문에 메모리를 할당하고 이전 문자열로부터 데이터를 복사합니다. 이것은 큰 문자열이나 빈번한 작업에 대해 성능 저하를 일으킬 수 있습니다.

## See Also (참고 자료)
- C++ Reference for `std::string::substr`: https://en.cppreference.com/w/cpp/string/basic_string/substr
- C++ `std::string_view`: https://en.cppreference.com/w/cpp/string/basic_string_view
- C++ Standard Library Reference: https://cplusplus.com/reference/
