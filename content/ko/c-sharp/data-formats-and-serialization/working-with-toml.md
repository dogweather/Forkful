---
date: 2024-01-26 04:20:53.488213-07:00
description: "TOML\uC740 \uD1B0\uC758 \uBA85\uBC31\uD558\uACE0 \uCD5C\uC18C\uD55C\uC758\
  \ \uC5B8\uC5B4(Tom's Obvious, Minimal Language)\uB97C \uC704\uD55C \uBA38\uB9BF\uAE00\
  \uC790\uB85C, \uBA85\uD655\uD55C \uC758\uBBF8\uB860 \uB355\uBD84\uC5D0 \uC27D\uAC8C\
  \ \uC77D\uD788\uB294 \uC124\uC815 \uD30C\uC77C \uD615\uC2DD\uC785\uB2C8\uB2E4. \uD504\
  \uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC2DC\uC2A4\uD15C\uAC04\uC758 \uB370\uC774\
  \uD130 \uAD50\uD658\uC744 \uB2E8\uC21C\uD654\uD558\uACE0 \uC778\uAC04\uC758 \uAC00\
  \uB3C5\uC131\uACFC \uAE30\uACC4\uC758 \uAD6C\uBB38 \uBD84\uC11D \uAC00\uB2A5\uC131\
  \ \uC0AC\uC774\uC758\u2026"
lastmod: '2024-03-13T22:44:55.269270-06:00'
model: gpt-4-0125-preview
summary: "TOML\uC740 \uD1B0\uC758 \uBA85\uBC31\uD558\uACE0 \uCD5C\uC18C\uD55C\uC758\
  \ \uC5B8\uC5B4(Tom's Obvious, Minimal Language)\uB97C \uC704\uD55C \uBA38\uB9BF\uAE00\
  \uC790\uB85C, \uBA85\uD655\uD55C \uC758\uBBF8\uB860 \uB355\uBD84\uC5D0 \uC27D\uAC8C\
  \ \uC77D\uD788\uB294 \uC124\uC815 \uD30C\uC77C \uD615\uC2DD\uC785\uB2C8\uB2E4."
title: "\uD504\uB85C\uADF8\uB798\uBA38\uB97C \uC704\uD55C TOML \uB2E4\uB8E8\uAE30"
weight: 39
---

## 방법:
먼저, `Tomlyn` 같은 TOML 파서를 설치하세요. 패키지 관리자를 사용합니다:

```csharp
dotnet add package Tomlyn
```

다음으로, TOML 파일을 구문 분석합니다:

```csharp
using Tomlyn;
using Tomlyn.Model;
using System;

var tomlContent = @"
[owner]
name = 'Tom Preston-Werner'
dob = 1979-05-27T07:32:00Z";

var tomlTable = Toml.Parse(tomlContent).ToModel();

Console.WriteLine($"소유자: {tomlTable["owner"]["name"]}");
// 출력:
// 소유자: Tom Preston-Werner
```

이제, TOML을 생성하고 작성합니다:

```csharp
using Tomlyn;
using Tomlyn.Syntax;
using System;
using System.IO;

var doc = new DocumentSyntax
{
    Tables =
    {
        new TableSyntax("owner")
        {
            Items =
            {
                { "name", "Tom Preston-Werner" },
                { "dob", "1979-05-27T07:32:00Z" }
            }
        }
    }
};

var tomlString = doc.ToString();
File.WriteAllText("config.toml", tomlString);
Console.WriteLine("config.toml에 TOML 작성됨");
// 출력:
// config.toml에 TOML 작성됨
```

## 심층 탐색:
TOML은 구성 설정에서 YAML과 JSON과 같은 기존 형식의 한계에 대한 반응으로 GitHub의 공동 창립자인 Tom Preston-Werner에 의해 2013년경에 만들어졌습니다. 이는 명확하고 모호하지 않은 것에 중점을 둔 구성을 위해 특별히 설계되었습니다.

다른 구성 형식으로는 YAML, JSON, 그리고 XML이 있습니다. 그러나 TOML은 특히 수동으로 편집하는 구성 파일에서 더 인간 친화적이라는 점에서 두드러집니다. JSON은 흔하긴 하지만 복잡한 구성의 경우 가독성이 떨어지고, XML은 장황합니다. YAML도 가독성 면에서 비슷하지만, 공백 사용이 많고 특정 내용에 대한 보안 위험이 있어 복잡해질 수 있습니다.

구현 측면에서 TOML은 해시 테이블에 깨끗하게 매핑되는 데 중점을 둬 데이터 추출이 예측 가능하도록 합니다. 1.0.0 버전이 출시되면서 TOML은 그 명세를 공고히 하고 안정성 및 도구 지원을 개선했습니다.

## 참고:
- 공식 TOML GitHub 저장소 & 명세: [github.com/toml-lang/toml](https://github.com/toml-lang/toml)
- .NET 라이브러리 Tomlyn: [github.com/xoofx/Tomlyn](https://github.com/xoofx/Tomlyn)
