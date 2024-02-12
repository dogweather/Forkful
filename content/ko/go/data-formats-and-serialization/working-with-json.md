---
title:                "JSON 작업하기"
aliases:
- /ko/go/working-with-json/
date:                  2024-02-03T18:12:18.532687-07:00
model:                 gpt-4-0125-preview
simple_title:         "JSON 작업하기"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/go/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

Go에서 JSON(JavaScript Object Notation)을 다루는 것은 Go 데이터 구조와 JSON 형식 간의 데이터를 인코딩하고 디코딩하는 작업을 포함합니다. 이 작업은 웹 서비스와 API에서 보편적이며, JSON은 가벼운, 텍스트 기반, 언어 독립적 데이터 교환 형식으로, 다양한 프로그래밍 환경간에 단순한 데이터 공유를 가능하게 합니다.

## 방법:

Go에서는 `encoding/json` 패키지가 JSON 처리의 관문으로, Go 데이터 구조를 JSON으로 변환(마샬링)하고 돌아가는(언마샬링) 메커니즘을 제공합니다. 아래는 시작하는 데 도움이 될 기본 예시들입니다:

### 인코딩(마샬링)

Go 구조체를 JSON으로 변환하려면 `json.Marshal`을 사용할 수 있습니다. 다음 Go 구조체를 고려해보세요:

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
)

type User struct {
    ID        int      `json:"id"`
    Username  string   `json:"username"`
    Languages []string `json:"languages"`
}

func main() {
    user := User{1, "JohnDoe", []string{"Go", "JavaScript", "Python"}}
    userJSON, err := json.Marshal(user)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(string(userJSON))
}
```

출력:

```json
{"id":1,"username":"JohnDoe","languages":["Go","JavaScript","Python"]}
```

### 디코딩(언마샬링)

Go 데이터 구조로 JSON을 파싱하려면 `json.Unmarshal`을 사용하세요:

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
)

func main() {
    jsonStr := `{"id":1,"username":"JohnDoe","languages":["Go","JavaScript","Python"]}`
    var user User
    err := json.Unmarshal([]byte(jsonStr), &user)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Printf("%+v\n", user)
}
```

이전과 같이 `User` 구조체를 주어졌을 때, 이 코드는 JSON 문자열을 User 인스턴스로 파싱합니다.

출력:

```go
{ID:1 Username:JohnDoe Languages:[Go JavaScript Python]}
```

## 심층 분석

Go의 `encoding/json` 패키지는 JSON 처리에서 관련된 많은 복잡성을 추상화하는 간단한 API를 제공합니다. Go 개발 초기에 도입된 이 패키지는 단순성과 효율성이라는 Go의 철학을 반영합니다. 하지만, `encoding/json`이 런타임에 구조체를 조사하고 수정하기 위해 리플렉션을 사용한다는 사실은 CPU 집약적 시나리오에서 최적의 성능이 되지 않을 수 있습니다.

`json-iterator/go`와 `ffjson` 같은 대안들이 나타나서, 정적 마샬링 및 언마샬링 코드를 생성함으로써 더 빠른 JSON 처리를 제공합니다. 하지만, `encoding/json`은 그 단순함, 강건함, 그리고 표준 라이브러리의 일부라는 사실 때문에 Go 버전에 걸쳐 호환성과 안정성을 보장하면서 가장 흔히 사용되는 패키지로 남아 있습니다.

상대적으로 느린 성능에도 불구하고, 사용의 용이성과 Go의 타입 시스템과의 통합은 `encoding/json`을 대부분의 애플리케이션에 적합하게 만듭니다. 성능이 중요한 맥락에서 일하는 이들에게는 외부 라이브러리를 탐색하는 것이 가치가 있을 수 있지만, 많은 경우에 표준 라이브러리는 속도, 단순성, 그리고 신뢰성 사이에 적절한 균형을 이룹니다.
