---
title:                "HTTP 요청 보내기"
aliases:
- ko/ruby/sending-an-http-request.md
date:                  2024-01-20T18:00:44.036075-07:00
model:                 gpt-4-1106-preview
simple_title:         "HTTP 요청 보내기"

tag:                  "HTML and the Web"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/ruby/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
HTTP 요청을 보내는 것은 웹 서버에 정보를 요청하거나 데이터를 전송하는 방법입니다. 프로그래머들은 API와의 상호작용, 웹 컨텐츠 다운로드, 서버에 데이터 제출 등을 위해 이를 수행합니다.

## How to: (방법)
Ruby에서 HTTP 요청을 보내려면 표준 라이브러리인 'net/http'를 활용할 수 있습니다. 여기 간단한 GET 요청 예시가 있어요:

```Ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com')
response = Net::HTTP.get(uri)

puts response
```

이 코드는 http://example.com 로부터 응답을 받아 출력합니다. POST 요청은 다음과 같이 할 수 있어요:

```Ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com/api/v1/users')
request = Net::HTTP::Post.new(uri, 'Content-Type' => 'application/json')
request.body = {name: 'Kim', job: 'Developer'}.to_json

response = Net::HTTP.start(uri.hostname, uri.port) do |http|
  http.request(request)
end

puts response.body
```

이 코드는 `name`과 `job`이라는 데이터를 JSON 형태로 'http://example.com/api/v1/users' 주소에 POST로 보냅니다.

## Deep Dive (심층 분석)
'net/http'는 Ruby에 내장된 라이브러리로, HTTP 프로토콜을 사용한 네트워크 통신을 다룰 수 있게 해줍니다. 이전에는 'open-uri'처럼 다른 라이브러리를 사용한 적도 있지만, 'net/http'로 갈아탔죠. 'net/http' 외에도 Faraday, HTTParty, RestClient 같은 gem들이 있고, 각각의 장단점이 달라 상황에 맞게 선택하면 됩니다.

## See Also (참고 자료)
- Ruby 공식 문서의 'net/http': https://ruby-doc.org/stdlib/libdoc/net/http/rdoc/Net/HTTP.html
- Faraday GitHub 페이지: https://github.com/lostisland/faraday
- HTTParty GitHub 페이지: https://github.com/jnunemaker/httparty
- RestClient GitHub 페이지: https://github.com/rest-client/rest-client
