---
title:                "HTML 파싱"
aliases:
- /ko/go/parsing-html/
date:                  2024-02-03T18:00:13.643883-07:00
model:                 gpt-4-0125-preview
simple_title:         "HTML 파싱"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/go/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

Go에서 HTML 파싱은 HTML 파일의 내용을 분석하여 데이터를 추출하거나, 구조를 조작하거나, HTML을 다른 형식으로 변환하는 것을 말합니다. 프로그래머들은 웹 스크래핑, 템플릿화 및 데이터 마이닝을 위해 이 작업을 수행하며, Go의 강력한 동시성 기능을 활용하여 대량의 웹 페이지를 효율적으로 처리합니다.

## 방법:

Go에서 HTML을 파싱하기 위해 일반적으로 `goquery` 패키지나 표준 라이브러리의 `net/html` 패키지를 사용합니다. 여기 웹페이지에서 모든 링크를 추출하기 위해 `net/html`을 사용한 기본 예제가 있습니다:

```go
package main

import (
    "fmt"
    "golang.org/x/net/html"
    "net/http"
)

func main() {
    // HTML 문서 가져오기
    res, err := http.Get("http://example.com")
    if err != nil {
        panic(err)
    }
    defer res.Body.Close()

    // HTML 문서 파싱
    doc, err := html.Parse(res.Body)
    if err != nil {
        panic(err)
    }

    // DOM을 재귀적으로 순회하는 함수
    var f func(*html.Node)
    f = func(n *html.Node) {
        if n.Type == html.ElementNode && n.Data == "a" {
            for _, a := range n.Attr {
                if a.Key == "href" {
                    fmt.Println(a.Val)
                    break
                }
            }
        }
        for c := n.FirstChild; c != nil; c = c.NextSibling {
            f(c)
        }
    }

    // DOM 순회
    f(doc)
}
```

샘플 출력 (가정: `http://example.com`에 두 개의 링크가 포함되어 있음):

```
http://www.iana.org/domains/example
http://www.iana.org/domains/reserved
```

이 코드는 HTML 페이지를 요청하고, 파싱하고, DOM을 재귀적으로 순회하여 모든 `<a>` 태그의 `href` 속성을 찾아서 출력합니다.

## 심층 분석

`net/html` 패키지는 HTML5 표준에 명시된 토큰화 및 트리 구축 알고리즘을 직접 구현하여 Go에서 HTML 파싱의 기본을 제공합니다. 이 저수준 접근 방식은 강력하지만 복잡한 작업에 대해 장황할 수 있습니다.

반면에, jQuery에서 영감을 받은 서드파티 `goquery` 패키지는 DOM 조작 및 순회를 간소화하는 고수준 인터페이스를 제공합니다. 개발자가 요소 선택, 속성 추출 및 콘텐츠 조작과 같은 작업에 대해 간결하고 표현력 있는 코드를 작성할 수 있도록 합니다.

하지만, `goquery`의 편리함은 추가적인 의존성과 그 추상화 레이어로 인해 발생하는 잠재적으로 느린 성능의 대가로 이루어집니다. `net/html`과 `goquery`(또는 다른 파싱 라이브러리) 사이의 선택은 프로젝트의 특정 요구 사항, 예를 들면 성능 최적화나 사용 용이성의 필요성에 따라 달라집니다.

역사적으로, Go에서의 HTML 파싱은 기본적인 문자열 연산에서 복잡한 DOM 트리 조작까지 발전하였으며, 이는 언어의 성장하는 생태계와 커뮤니티의 강력한 웹 스크래핑 및 데이터 추출 도구에 대한 요구를 반영합니다. 기본 기능에도 불구하고, `goquery`와 같은 서드파티 라이브러리의 유병함은 Go 커뮤니티가 모듈화되고 재사용 가능한 코드를 선호한다는 것을 강조합니다. 하지만, 성능에 민감한 애플리케이션의 경우, 프로그래머들은 여전히 `net/html` 패키지나 심지어는 간단한 파싱 작업을 위해 정규 표현식(regex)을 선호할 수 있으며, 정규 표현식 기반 HTML 파싱의 내재된 위험성과 한계를 염두에 두어야 합니다.
