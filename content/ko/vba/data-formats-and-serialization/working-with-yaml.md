---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:07:43.649321-07:00
description: "YAML\uC740 \"YAML Ain't Markup Language\"\uB97C \uC758\uBBF8\uD558\uBA70\
  , \uAD6C\uC131 \uD30C\uC77C\uC5D0 \uC77C\uBC18\uC801\uC73C\uB85C \uC0AC\uC6A9\uB418\
  \uB294 \uC0AC\uB78C\uC774 \uC77D\uC744 \uC218 \uC788\uB294 \uB370\uC774\uD130 \uC9C1\
  \uB82C\uD654 \uC5B8\uC5B4\uC785\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\
  \uC740 \uC774\uB97C \uB2E4\uC591\uD55C \uD504\uB85C\uADF8\uB798\uBC0D \uD658\uACBD\
  \uC5D0\uC11C\uC758 \uB2E8\uC21C\uC131\uACFC \uAC00\uB3C5\uC131 \uB54C\uBB38\uC5D0\
  \ \uC790\uC8FC \uC0AC\uC6A9\uD558\uB294\uB370, \uC774\uB294 \uB370\uC774\uD130\uC758\
  \ \uC0C1\uD638 \uC6B4\uC6A9\uC131,\u2026"
lastmod: '2024-03-13T22:44:55.014101-06:00'
model: gpt-4-0125-preview
summary: "YAML\uC740 \"YAML Ain't Markup Language\"\uB97C \uC758\uBBF8\uD558\uBA70\
  , \uAD6C\uC131 \uD30C\uC77C\uC5D0 \uC77C\uBC18\uC801\uC73C\uB85C \uC0AC\uC6A9\uB418\
  \uB294 \uC0AC\uB78C\uC774 \uC77D\uC744 \uC218 \uC788\uB294 \uB370\uC774\uD130 \uC9C1\
  \uB82C\uD654 \uC5B8\uC5B4\uC785\uB2C8\uB2E4."
title: "YAML\uB85C \uC791\uC5C5\uD558\uAE30"
weight: 41
---

## 방법:
VBA에서 YAML을 작업하려면 YAML을 VBA가 쉽게 조작할 수 있는 형식, 보통 딕셔너리나 컬렉션으로 파싱하고 변환하는 방법을 이해해야 합니다. 불행히도, VBA는 기본적으로 YAML 파싱이나 직렬화를 지원하지 않습니다. 그러나, YAML이 JSON과 밀접한 관련이 있으므로, JSON 변환 도구와 딕셔너리 객체의 조합을 사용하여 YAML 데이터를 작업할 수 있습니다.

먼저, 온라인 변환기 또는 개발 환경 내의 YAML에서 JSON으로 변환 도구를 사용하여 YAML 데이터를 JSON으로 변환합니다. 변환된 후, JSON을 VBA에서 파싱하는 다음 예제를 사용할 수 있습니다. 이 접근 방식은 간접적으로 YAML을 작업할 수 있게 해줍니다:

```vb
' Dictionary를 위한 Microsoft Scripting Runtime 참조 추가
' JSON 파싱을 위한 Microsoft XML, v6.0 참조 추가

Sub ParseYAMLAsJSON()
    Dim jsonText As String
    jsonText = "{""name"": ""John Doe"", ""age"": 30}" ' 이것은 YAML에서 변환된 JSON 입니다
    
    ' JSON 파서 함수가 있다고 가정
    Dim parsedData As Dictionary
    Set parsedData = JsonParser(jsonText)
    
    Debug.Print "이름: " & parsedData("name")
    Debug.Print "나이: " & parsedData("age")
End Sub

Function JsonParser(ByVal jsonText As String) As Dictionary
    ' JSON 파싱 로직을 위한 자리 표시자 - 여기에서 외부 라이브러리를 사용할 수 있습니다
    Set JsonParser = New Dictionary
    JsonParser.Add "name", "John Doe"
    JsonParser.Add "age", 30
End Function
```
이 예제에서, `JsonParser` 함수는 JSON을 파싱할 위치를 대신하는 것입니다. JSON 파싱을 돕는 다양한 라이브러리가 있으며, VBA를 위한 직접적인 YAML 파싱 라이브러리는 드뭅니다.

## 심층 분석
VBA에서 직접적인 YAML 처리의 부재는 그것이 만들어진 시대와 환경, 초기에는 현대적인 데이터 직렬화 형식을 염두에 두지 않았던 것에 기인합니다. YAML 자체는 2000년대 초반, 사람 친화적인 구성 파일을 요구하는 애플리케이션의 출현과 맞물려 인기 있는 구성 및 직렬화 형식으로 부상했습니다.

프로그래머들은 일반적으로 VBA와 YAML 사이의 격차를 통합하기 위해 외부 도구나 라이브러리를 활용합니다. 이는 보여진 바와 같이 YAML을 JSON으로 변환하는 과정을 종종 포함하는데, 이는 다양한 라이브러리를 통해 사용할 수 있는 JSON 지원과 JSON과 YAML이 구조와 목적 측면에서 유사하기 때문입니다.

직접적으로 VBA에서 YAML을 작업하는 것은 언어의 유연성을 보여주지만, YAML을 구성이나 데이터 직렬화에 크게 의존하는 프로젝트에는 Python 또는 JavaScript와 같은 다른 프로그래밍 환경이 더 기본적이고 원활한 지원을 제공할 수 있다는 점에 주목하는 것이 가치가 있습니다. 그럼에도 불구하고, VBA를 사용해야 하거나 선호하는 경우, JSON 변환을 통한 간접적인 방법은 YAML 데이터를 관리하고 조작하는 데 유용하고 실행 가능한 접근 방식임이 입증되었습니다.
