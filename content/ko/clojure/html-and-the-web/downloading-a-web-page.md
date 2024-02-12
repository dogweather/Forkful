---
title:                "웹 페이지 다운로드하기"
aliases:
- /ko/clojure/downloading-a-web-page/
date:                  2024-01-20T17:43:54.220881-07:00
model:                 gpt-4-1106-preview
simple_title:         "웹 페이지 다운로드하기"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/clojure/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
웹 페이지를 다운로드한다는 것은 인터넷 상의 페이지 내용을 로컬 컴퓨터에 저장하는 것을 말합니다. 프로그래머들은 데이터 분석, 웹 크롤링 또는 백업용으로 웹 페이지를 다운로드합니다.

## How to: (방법)
Clojure에서 웹 페이지를 다운로드하려면 `clj-http` 라이브러리를 사용합니다. 먼저, 라이브러리를 프로젝트에 추가하세요:

```clj
; project.clj에 의존성 추가
:dependencies [[clj-http "3.12.3"]]
```

다음, 웹 페이지를 다운로드하고 내용을 출력하는 간단한 함수를 작성합니다:

```clj
(require '[clj-http.client :as client])

(defn download-page [url]
  (let [response (client/get url)]
    (:body response)))

;; 사용 예:
(println (download-page "http://example.com"))
```

출력 예:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
```

## Deep Dive (심층 분석)
`clj-http` 라이브러리는 Java의 Apache HttpComponents에 기반한 Clojure 래퍼입니다. 2009년에 개발되어 널리 사용되고 있습니다.

대안으로는 `http-kit`이나 Java 자체의 `java.net.HttpURLConnection`을 사용할 수 있습니다. `clj-http`는 동기식으로 수행되며, 내부적으로 connection pooling, 자동 리다이렉트 처리 등을 지원합니다.

## See Also (참고 자료)
- `clj-http` GitHub 페이지: [https://github.com/dakrone/clj-http](https://github.com/dakrone/clj-http)
- HttpComponents 공식 웹사이트: [https://hc.apache.org/](https://hc.apache.org/)
