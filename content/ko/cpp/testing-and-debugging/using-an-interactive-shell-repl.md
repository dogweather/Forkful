---
date: 2024-01-26 04:12:39.726981-07:00
description: "REPL(\uC77D\uAE30-\uD3C9\uAC00-\uCD9C\uB825-\uBC18\uBCF5)\uC740 \uAC04\
  \uB2E8\uD55C \uC778\uD130\uB799\uD2F0\uBE0C \uD504\uB85C\uADF8\uB798\uBC0D \uD658\
  \uACBD\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC2E4\uC2DC\
  \uAC04 \uC5B8\uC5B4 \uC2E4\uD5D8, \uAC04\uB2E8\uD55C \uC791\uC5C5 \uB610\uB294 \uC804\
  \uCCB4 \uC560\uD50C\uB9AC\uCF00\uC774\uC158\uC744 \uC0DD\uC131\uD558\uB294 \uC624\
  \uBC84\uD5E4\uB4DC \uC5C6\uC774 \uC0C8\uB85C\uC6B4 \uAC1C\uB150\uC744 \uC774\uD574\
  \uD558\uAE30 \uC704\uD574 \uC774\uB97C \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:55.670273-06:00'
model: gpt-4-0125-preview
summary: "REPL(\uC77D\uAE30-\uD3C9\uAC00-\uCD9C\uB825-\uBC18\uBCF5)\uC740 \uAC04\uB2E8\
  \uD55C \uC778\uD130\uB799\uD2F0\uBE0C \uD504\uB85C\uADF8\uB798\uBC0D \uD658\uACBD\
  \uC785\uB2C8\uB2E4."
title: "\uC778\uD130\uB799\uD2F0\uBE0C \uC178 (REPL) \uC0AC\uC6A9\uD558\uAE30"
weight: 34
---

## 사용 방법:
C++은 내장된 REPL을 제공하지 않지만, Cling과 같은 도구는 그 기능을 제공합니다. 다음은 Cling을 사용하여 두 수의 합을 계산하는 방법입니다:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 7;
    std::cout << "합계는: " << a + b << std::endl;
    return 0;
}

// 출력:
// 합계는: 12
```

Cling을 시작하고 코드를 한 줄씩 입력하면서 각 명령어 후의 출력을 관찰하세요. 컴파일 없이 즉각적인 피드백을 받을 수 있습니다.

## 심층 분석
REPL은 Python이나 Lisp와 같은 언어에서 흔하며, 1960년대부터 사용되어 왔습니다. C++와 같은 컴파일 언어의 경우, 개념이 자연스럽게 들어맞지 않기 때문에 Cling과 같은 도구가 존재합니다—이는 C++을 즉석에서 해석합니다. 대안으로는 온라인 컴파일러나 전통적으로 컴파일된 소규모 테스트 프로그램이 있습니다. Cling은 LLVM과 Clang 위에 구축되어, C++이 해석 방식으로 사용될 수 있도록 다리 역할을 합니다.

## 참고 자료
- [Cling](https://root.cern/cling/): LLVM과 Clang 라이브러리 위에 구축된 인터랙티브 C++ 해석기.
- [Jupyter Notebooks](https://jupyter.org/): 노트북 환경 내에서 인터랙티브 쉘을 제공하며, xeus-cling 커널을 통해 C++을 지원합니다.
- [LLVM](https://llvm.org/): Cling이 구축된 모듈식 및 재사용 가능한 컴파일러 및 툴체인 기술 모음.
