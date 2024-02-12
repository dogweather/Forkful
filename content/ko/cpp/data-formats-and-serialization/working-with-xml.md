---
title:                "XML 다루기"
aliases:
- /ko/cpp/working-with-xml/
date:                  2024-01-26T04:28:58.505910-07:00
model:                 gpt-4-0125-preview
simple_title:         "XML 다루기"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/cpp/working-with-xml.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?
XML을 다루는 것은 XML(eXtensible Markup Language) 데이터를 파싱, 생성, 조작하는 것을 의미합니다. 프로그래머들은 플랫폼 중립적인 특성 때문에 구조화된 데이터 교환, 구성 등을 관리하기 위해 XML을 다룹니다.

## 어떻게:
다음은 TinyXML-2 라이브러리를 사용하여 XML을 파싱하는 간단한 방법입니다:

```C++
#include <tinyxml2.h>
#include <iostream>

int main() {
    tinyxml2::XMLDocument doc;
    doc.Parse("<root><message>안녕, 세상!</message></root>");
    const char* content = doc.FirstChildElement("root")->FirstChildElement("message")->GetText();
    std::cout << content << std::endl;
    return 0;
}
```

샘플 출력:

```
안녕, 세상!
```

그리고 이것은 XML 파일을 생성하는 방법입니다:

```C++
#include <tinyxml2.h>
#include <iostream>

int main() {
    tinyxml2::XMLDocument doc;
    auto* declaration = doc.NewDeclaration();
    doc.InsertFirstChild(declaration);
    auto* root = doc.NewElement("root");
    doc.InsertEndChild(root);
    auto* message = doc.NewElement("message");
    message->SetText("안녕, 세상!");
    root->InsertEndChild(message);
    doc.SaveFile("output.xml");
    return 0;
}
```

이것은 내용이 있는 XML 파일 `output.xml`을 생성합니다:

```xml
<?xml version="1.0"?>
<root>
    <message>안녕, 세상!</message>
</root>
```

## 깊은 이해
90년대 말부터 XML은 웹 서비스와 데이터 저장에서 중추적인 역할을 해왔습니다. 현재는 JSON과 YAML이 설정 및 상호 운용성을 위해 더 일반적으로 사용되지만, XML은 여전히 많은 기업 시스템에서 큰 비중을 차지하고 있습니다. C++에서 XML을 파싱하는 것은 수동 DOM/SAX 파싱으로 구식처럼 느껴질 수 있습니다. 다행히도, TinyXML-2와 같은 라이브러리가 그것을 단순화합니다. C++은 내장 XML 지원이 없으며, TinyXML-2, pugixml, Xerces와 같은 라이브러리는 어려운 부분을 해결해줍니다.

## 참고
- TinyXML-2 문서: https://leethomason.github.io/tinyxml2/
- pugixml 라이브러리: https://pugixml.org/
- Xerces-C++ 파서: https://xerces.apache.org/xerces-c/
- W3C XML 규격: https://www.w3.org/XML/
