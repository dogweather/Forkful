---
title:                "코드를 함수로 구성하기"
date:                  2024-01-26T01:09:57.978801-07:00
model:                 gpt-4-1106-preview
simple_title:         "코드를 함수로 구성하기"
programming_language: "C#"
category:             "C#"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/c-sharp/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## 무엇이며 왜 그런가?
코드를 함수로 나누는 것은 LEGO 블록을 상자에 정리하는 것과 같아서, 찾고 사용하기가 더 쉬워집니다. 우리는 반복을 피하고, 이해를 단순하게 하며, 유지보수를 덜 번거롭게 하기 위해서 이렇게 합니다.

## 어떻게 하나:
여러 번 인사말을 출력하는 코드가 있다고 상상해 보세요. 함수가 없으면 지저분합니다. 함수가 있으면 깔끔합니다.

```C#
// 함수 없이 - 반복적
Console.WriteLine("Hello, Amy!");
Console.WriteLine("Hello, Bob!");
Console.WriteLine("Hello, Charlie!");

// 함수로 - 깔끔하게 
void Greet(string name) {
    Console.WriteLine($"Hello, {name}!");
}

Greet("Amy");
Greet("Bob");
Greet("Charlie");
```

출력은 같지만, 두 번째 버전이 훨씬 더 정돈되어 있습니다.

## 깊이있게 알아보기
예전에 어셈블리 언어 시절에는 GOTO를 사용해 다른 코드 위치로 점프했었는데, 이는 혼란스럽고 추적하기 어려웠습니다. 함수는 마치 공구함의 정리된 서랍과 같은, 주요한 개선점입니다. 대안이 있나요? 물론입니다. 클래스 상황에서 함수인 메소드가 있죠. 그리고 람다와 인라인 함수가 있어서, 빠르고 일회성 작업을 위해 사용됩니다.

구현에 대해서—작고 집중된 함수는 금이죠. 테스트하고 디버그하는 게 더 쉽습니다. 많은 책임을 지는 큰 함수는 괴물이 될 수 있어서, "스파게티 코드"라는 의심스러운 칭호를 얻게 됩니다. 함수당 하나의 작업을 맡겨, 나중에 자신이 감사하게 될 것입니다.

## 참고자료
함수와 최선의 관행에 대해 더 알아보고 싶다면 아래를 확인하세요:

- Robert C. Martin의 Clean Code: 함수를 깔끔하게 유지하는 원칙.
- Martin Fowler의 Refactoring: 기존 코드를 개선하는 방법.
- Microsoft C# 가이드 - Methods: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods
