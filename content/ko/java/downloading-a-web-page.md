---
title:                "웹 페이지 다운로드하기"
date:                  2024-01-20T17:44:40.332768-07:00
model:                 gpt-4-1106-preview
simple_title:         "웹 페이지 다운로드하기"
programming_language: "Java"
category:             "Java"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/java/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (무엇인가 & 왜?)
웹 페이지 다운로드는 인터넷에서 페이지의 내용을 로컬 컴퓨터로 가져오는 과정입니다. 프로그래머들은 데이터를 수집, 분석하거나, 백업을 생성하고, 웹 앱의 기능을 테스트하기 위해 이 작업을 수행합니다.

## How to: (어떻게:)
Java에는 웹 페이지를 다운로드하기 위한 여러 방법이 있지만, 여기서는 `java.net.http` 패키지를 사용하는 방법에 집중하겠습니다.

```java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class WebPageDownloader {
    public static void main(String[] args) {
        HttpClient client = HttpClient.newHttpClient();
        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create("http://example.com"))
                .build();
        
        client.sendAsync(request, HttpResponse.BodyHandlers.ofString())
              .thenApply(HttpResponse::body)
              .thenAccept(System.out::println)
              .join();
    }
}
```

실행 결과, `http://example.com` 의 내용이 콘솔에 출력됩니다. 이 예제는 비동기적으로 웹 페이지를 가져오고, 결과를 콘솔에 인쇄합니다.

## Deep Dive (심층 분석)
과거에는 Java에서 웹 페이지를 다운로드하려면 `java.net.URL` 또는 `org.apache.http` 같은 외부 라이브러리를 사용해야 했습니다. 그러나 Java 11부터 `java.net.http.HttpClient`가 등장하며 더 간결하고 현대적인 API를 제공합니다. 전통적인 방법에 비해 `HttpClient`는 비동기 처리를 쉽게 하여 성능을 개선해줍니다.

대안으로, `Jsoup`이나 `HtmlUnit`과 같은 서드파티 라이브러리를 사용할 수 있습니다. 그들은 웹 스크래핑을 위한 추가적인 기능을 제공하나, 단순 다운로드의 경우에는 `HttpClient`만으로 충분합니다.

구현 세부 사항에서는 요청 헤더 설정, 타임아웃 지정, 프록시 설정 등의 요소를 설정할 수 있습니다. 또한 HTTP POST, PUT 등의 다른 메서드로의 확장성도 있다는 것을 알아두는 것이 좋습니다.

## See Also (추가 정보)
- [HttpClient 공식 문서](https://docs.oracle.com/en/java/javase/11/docs/api/java.net.http/java/net/http/HttpClient.html)
- [Jsoup 공식 사이트](https://jsoup.org/)
- [HtmlUnit 공식 사이트](http://htmlunit.sourceforge.net/)