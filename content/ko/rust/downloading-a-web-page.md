---
title:                "웹 페이지 다운로드하기"
date:                  2024-01-20T17:45:05.246525-07:00
model:                 gpt-4-1106-preview
simple_title:         "웹 페이지 다운로드하기"
programming_language: "Rust"
category:             "Rust"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/rust/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
웹 페이지 다운로드는 인터넷에서 HTML 문서를 로컬 장치로 가져오는 것입니다. 프로그래머들은 데이터를 수집하거나 웹 콘텐츠를 분석하기 위해 이 작업을 합니다.

## How to: (방법)
Rust에서는 `reqwest` 크레이트를 사용해 웹 페이지를 다운로드할 수 있습니다. 비동기 코드 예제를 포함해 간단하게 시작해보겠습니다.

```rust
// Cargo.toml 파일에 의존성 추가
// [dependencies]
// reqwest = "0.11"
// tokio = { version = "1", features = ["full"] }

#[tokio::main]
async fn main() -> Result<(), reqwest::Error> {
    let url = "http://example.com";
    let response = reqwest::get(url).await?;

    let contents = response.text().await?;
    println!("웹 페이지 내용: {}", contents);
    Ok(())
}
```

이 코드를 실행하면 `http://example.com` 웹 페이지의 HTML 내용이 출력됩니다.

## Deep Dive (심층 분석)
웹 페이지를 다운로드하는 것은 웹 크롤링의 기초입니다. 초기 웹에서는 `wget`과 `curl` 같은 도구를 사용했습니다. Rust에서는 `reqwest`와 같은 라이브러리가 네트워크 요청을 처리하고 `tokio`는 비동기 작업을 다룹니다.

`reqwest`는 기본적으로 비동기 입니다. Rust의 비동기 패턴은 효율적인 I/O 작업을 가능하게 해 서버 또는 고성능 애플리케이션에 적합합니다. `tokio`는 Rust의 비동기 런타임이며, `await` 키워드로 비동기 작업을 쉽게 처리할 수 있습니다.

다른 언어의 `requests`나 `http` 라이브러리처럼, `reqwest`도 쿠키, 리다이렉션, JSON 등 흔히 필요로 하는 HTTP 기능들을 지원합니다.

## See Also (참고 자료)
- [Rust `reqwest` documentation](https://docs.rs/reqwest/)
- [Rust `tokio` project](https://tokio.rs/)
- [Mozilla Developer Network (MDN) - HTTP overview](https://developer.mozilla.org/docs/Web/HTTP/Overview)
- [`curl` command line tool](https://curl.se/)
- [`wget` command line tool](https://www.gnu.org/software/wget/)