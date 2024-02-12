---
title:                "HTTP 요청 보내기"
aliases:
- ko/swift/sending-an-http-request.md
date:                  2024-01-20T18:00:47.738387-07:00
model:                 gpt-4-1106-preview
simple_title:         "HTTP 요청 보내기"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/swift/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
HTTP 요청을 보내는 것은 웹 서버와 데이터를 교환하는 방법이에요. 프로그래머가 사용자 어플리케이션을 서버의 리소스와 동기화하거나 외부 API를 통해 정보를 얻기 위해 사용합니다.

## How to: (어떻게 하나요?)
Swift에서 HTTP 요청을 보내려면 `URLSession` 객체를 사용하면 됩니다. 아래 예제는 `GET` 요청을 보내는 방법을 보여줍니다:

```Swift
import Foundation

let url = URL(string: "https://api.example.com/data")!
let session = URLSession.shared

let task = session.dataTask(with: url) { data, response, error in
    if let error = error {
        print("Error: \(error)")
    } else if let data = data,
              let string = String(data: data, encoding: .utf8) {
        print("Received data:\n\(string)")
    }
}

task.resume()
```
실행 결과:
```
Received data:
{
  "example": "Hello, this is a JSON response!"
}
```

## Deep Dive (심층 분석)
HTTP 요청은 웹의 기본입니다. 1991년에 처음 소개된 이후로, HTTP 프로토콜은 웹 개발의 핵심 요소로 자리 잡았습니다. `URLSession` 외에도, Swift에서는 Alamofire나 Moya 같은 써드파티 라이브러리를 사용해서 HTTP 요청을 보낼 수 있습니다. 하지만 여기서는 Swift의 표준 라이브러리인 `URLSession`의 기본 사용법을 다룹니다.

HTTP 요청을 보낼 때 중요한 것은 요청에 필요한 적절한 HTTP 메서드 (GET, POST, PUT 등)를 사용하여 서로 다른 종류의 행동을 할 수 있도록 하는 것입니다. `URLSession`은 콜백 방식, 프로미스 방식(`SwiftyURLRequest`) 혹은 결합형(`Combine`)으로 비동기적인 HTTP 통신을 지원합니다.

## See Also (추가 정보)
- [Apple의 URLSession 문서](https://developer.apple.com/documentation/foundation/urlsession)
- [HTTP 프로토콜에 대한 MDN 설명](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [Alamofire GitHub 페이지](https://github.com/Alamofire/Alamofire)
- [Moya GitHub 페이지](https://github.com/Moya/Moya)
