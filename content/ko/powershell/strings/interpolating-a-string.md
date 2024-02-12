---
title:                "문자열 보간하기"
aliases:
- /ko/powershell/interpolating-a-string/
date:                  2024-01-20T17:51:40.598542-07:00
model:                 gpt-4-1106-preview
simple_title:         "문자열 보간하기"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/powershell/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (무엇인가요? 왜 사용하나요?)
문자열 보간(string interpolation)은 문자열 내에 변수나 표현식의 값을 직접 삽입하는 방법입니다. 이것은 코드를 더 읽기 쉽고 유지 관리하기 편하게 만들기 위해 프로그래머들이 사용합니다.

## How to: (어떻게 사용하나요?)
```PowerShell
$name = "Jae"
$greeting = "안녕하세요, $name님!"
Write-Output $greeting
```
출력:
```
안녕하세요, Jae님!
```
변수로 채워진 문자열:
```PowerShell
$hoursWorked = 52
$salary = 40000
$sentence = "$name님이 이번 주에 $hoursWorked 시간을 일하셨습니다. 연봉은 $salary입니다."
Write-Output $sentence
```
출력:
```
Jae님이 이번 주에 52 시간을 일하셨습니다. 연봉은 40000입니다.
```
계산 결과를 포함한 문자열:
```PowerShell
$total = $hoursWorked * 15
$payCheck = "$name님의 이번 주 수입은 $($total)원입니다."
Write-Output $payCheck
```
출력:
```
Jae님의 이번 주 수입은 780원입니다.
```

## Deep Dive (심층 분석)
문자열 보간은 여러 프로그래밍 언어에서 `"` (쌍따옴표)로 묶인 텍스트 안에 `$` 기호를 통해 변수 값을 넣는 기능을 말합니다. PowerShell에서는 `$`과 변수 이름을 이용하거나, 복잡한 표현식은 `$()`을 사용합니다. 예전에는 문자열을 더하거나 `String.Format()`을 사용하는 방식이 있었지만, 보간은 이를 간단하게 해 줍니다. PowerShell 3.0 이상부터 사용 가능합니다. 성능 측면에서도 문자열 보간이 더하기 방식보다 유리할 때가 많습니다.

## See Also (참고 자료)
- [PowerShell에서의 문자열 보간 (String Interpolation in PowerShell)](https://ss64.com/ps/syntax-operators.html)
- [PowerShell에서 문자열을 다루는 방법 (Working with Strings in PowerShell)](https://docs.microsoft.com/en-us/powershell/scripting/developer/cmdlet/types-of-cmdlet-parameters?view=powershell-7.1#strings)
