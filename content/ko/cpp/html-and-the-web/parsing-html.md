---
title:                "HTML 파싱"
aliases:
- /ko/cpp/parsing-html/
date:                  2024-01-20T15:30:38.324382-07:00
simple_title:         "HTML 파싱"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/cpp/parsing-html.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
HTML 파싱은 HTML 문서를 분석해서 구조를 이해하는 과정입니다. 프로그래머는 데이터 추출, 웹 스크래핑, 콘텐츠 변환 등을 위해 파싱을 합니다.

## How to: (어떻게 하나요?)
C++에서는 여러 라이브러리를 사용해 HTML을 파싱할 수 있습니다. `Gumbo-parser`는 그중 하나입니다.

```C++
#include <iostream>
#include <gumbo.h>

void search_for_links(GumboNode* node) {
    if (node->type != GUMBO_NODE_ELEMENT) {
        return;
    }
    GumboAttribute* href;
    if (node->v.element.tag == GUMBO_TAG_A &&
       (href = gumbo_get_attribute(&node->v.element.attributes, "href"))) {
        std::cout << href->value << std::endl;
    }
    GumboVector* children = &node->v.element.children;
    for (unsigned int i = 0; i < children->length; ++i) {
        search_for_links(static_cast<GumboNode*>(children->data[i]));
    }
}

int main() {
    const char* html = "<html><body><a href=\"https://example.com\">Link</a></body></html>";
    GumboOutput* output = gumbo_parse(html);
    search_for_links(output->root);
    gumbo_destroy_output(&kGumboDefaultOptions, output);
}
```

샘플 출력:

```
https://example.com
```

## Deep Dive (깊이 들여다보기)
HTML 파싱은 웹의 초창기부터 필요했습니다. 초기에는 정규 표현식과 같은 단순한 도구를 사용했지만, HTML의 복잡성 때문에 전문적인 파서가 개발되었습니다. `Gumbo-parser`는 구글이 개발한 오픈소스 HTML5 파서로, C 언어로 작성되었습니다. 대안으로 `htmlcxx`, `MyHTML`, `Gumbo++` 등이 있습니다. 이 파서들은 각각 다르게 HTML을 DOM(Document Object Model) 트리로 변환하여 프로그램에서 사용할 수 있게 해 줍니다.

## See Also (더 보기)
- Gumbo-parser GitHub: https://github.com/google/gumbo-parser
- htmlcxx: http://htmlcxx.sourceforge.net/
- MyHTML GitHub: https://github.com/lexborisov/myhtml
- W3C HTML5 Parser Specifications: https://www.w3.org/TR/html5/syntax.html
