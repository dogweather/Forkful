---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:27:26.228763-07:00
description: "C++\uC5D0\uC11C \uD14D\uC2A4\uD2B8 \uD30C\uC77C\uC5D0 \uC4F0\uAE30\uB294\
  \ \uD30C\uC77C\uC744 \uC0DD\uC131\uD558\uAC70\uB098 \uC5F4\uACE0 \uAC70\uAE30\uC5D0\
  \ \uB370\uC774\uD130\uB97C \uC791\uC131\uD558\uB294 \uAC83\uC744 \uD3EC\uD568\uD569\
  \uB2C8\uB2E4. \uC774\uAC83\uC740 \uB85C\uADF8, \uC0AC\uC6A9\uC790 \uC0DD\uC131 \uCF58\
  \uD150\uCE20 \uB610\uB294 \uC124\uC815\uAC12\uACFC \uAC19\uC774 \uB370\uC774\uD130\
  \uB97C \uC720\uC9C0\uD574\uC57C \uD558\uB294 \uC751\uC6A9 \uD504\uB85C\uADF8\uB7A8\
  \uC5D0 \uD544\uC218\uC801\uC778 \uC791\uC5C5\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\
  \uB798\uBA38\uB4E4\uC740 \uD504\uB85C\uADF8\uB7A8 \uC2E4\uD589 \uC911\uC5D0 \uC0DD\
  \uC131\uB41C \uB370\uC774\uD130\uB97C \uC800\uC7A5\uD558\uAC70\uB098\u2026"
lastmod: '2024-03-13T22:44:55.696511-06:00'
model: gpt-4-0125-preview
summary: "C++\uC5D0\uC11C \uD14D\uC2A4\uD2B8 \uD30C\uC77C\uC5D0 \uC4F0\uAE30\uB294\
  \ \uD30C\uC77C\uC744 \uC0DD\uC131\uD558\uAC70\uB098 \uC5F4\uACE0 \uAC70\uAE30\uC5D0\
  \ \uB370\uC774\uD130\uB97C \uC791\uC131\uD558\uB294 \uAC83\uC744 \uD3EC\uD568\uD569\
  \uB2C8\uB2E4."
title: "\uD14D\uC2A4\uD2B8 \uD30C\uC77C \uC4F0\uAE30"
weight: 24
---

## 어떻게:
C++은 텍스트 파일에 쓰는 몇 가지 방법을 제공하지만, 가장 간단한 방법 중 하나는 파일 쓰기 작업에 사용되는 `ofstream` (출력 파일 스트림) 클래스를 제공하는 `<fstream>` 라이브러리를 사용하는 것입니다.

### `<fstream>` 사용 예시:
```cpp
#include <fstream>
#include <iostream>

int main() {
    std::ofstream file("example.txt");
    if (file.is_open()) {
        file << "Hello, world!\n";
        file << "C++에서 파일에 쓰기는 간단합니다.";
        file.close();
    } else {
        std::cerr << "파일을 열기에 실패했습니다\n";
    }
    return 0;
}
```

**'example.txt'의 샘플 출력:**
```
Hello, world!
C++에서 파일에 쓰기는 간단합니다.
```

프로그래머가 더 복잡한 데이터를 다루거나 쓰기 과정에 더 많은 제어가 필요한 경우, Boost Filesystem과 같은 제3자 라이브러리를 이용할 수 있습니다.

### Boost Filesystem 사용 예시:
파일 작업을 위해 Boost를 사용하려면 먼저 Boost 라이브러리를 설치해야 합니다. 다음 예시는 `boost::filesystem`과 `boost::iostreams`를 사용하여 파일을 생성하고 그에 쓰는 것을 보여줍니다.

```cpp
#include <boost/filesystem.hpp>
#include <boost/iostreams/device/file.hpp>
#include <boost/iostreams/stream.hpp>
#include <iostream>

namespace io = boost::iostreams;
namespace fs = boost::filesystem;

int main() {
    fs::path filePath("boost_example.txt");
    io::stream_buffer<io::file_sink> buf(filePath.string());
    std::ostream out(&buf);
    out << "Boost는 파일 작업을 쉽게 만듭니다.\n";
    out << "이 줄은 Boost로 작성되었습니다.";
    
    return 0;
}
```

**'boost_example.txt'의 샘플 출력:**
```
Boost는 파일 작업을 쉽게 만듭니다.
이 줄은 Boost로 작성되었습니다.
```

특정 프로젝트의 요구 사항과 파일 I/O 작업에 대해 필요한 제어 또는 유연성의 정도에 따라 원시 C++과 Boost와 같은 제3자 라이브러리 사이에 선택할 수 있습니다.
