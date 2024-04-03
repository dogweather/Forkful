---
date: 2024-01-20 17:43:10.529185-07:00
description: "\uD328\uD134\uACFC \uC77C\uCE58\uD558\uB294 \uBB38\uC790\uB97C \uC0AD\
  \uC81C\uD558\uB294 \uAC83\uC740 \uBB38\uC790\uC5F4\uC5D0\uC11C \uD2B9\uC815 \uD328\
  \uD134(\uC608: \uC22B\uC790, \uD2B9\uC218 \uBB38\uC790)\uC744 \uC81C\uAC70\uD558\
  \uB294 \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4. \uC774\uB97C \uD1B5\uD574 \uB370\uC774\
  \uD130\uB97C \uC815\uC81C\uD558\uACE0, \uD615\uC2DD\uC744 \uD1B5\uC77C\uD558\uBA70\
  , \uCC98\uB9AC\uB97C \uB2E8\uC21C\uD654\uD558\uAE30 \uC704\uD574 \uD504\uB85C\uADF8\
  \uB798\uBA38\uB4E4\uC774 \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.520334-06:00'
model: gpt-4-1106-preview
summary: "\uD328\uD134\uACFC \uC77C\uCE58\uD558\uB294 \uBB38\uC790\uB97C \uC0AD\uC81C\
  \uD558\uB294 \uAC83\uC740 \uBB38\uC790\uC5F4\uC5D0\uC11C \uD2B9\uC815 \uD328\uD134\
  (\uC608: \uC22B\uC790, \uD2B9\uC218 \uBB38\uC790)\uC744 \uC81C\uAC70\uD558\uB294\
  \ \uAC83\uC744 \uB9D0\uD569\uB2C8\uB2E4."
title: "\uD328\uD134\uC5D0 \uC77C\uCE58\uD558\uB294 \uBB38\uC790 \uC0AD\uC81C"
weight: 5
---

## How to: (방법)
PowerShell에서 문자열의 패턴을 삭제하는 기본적인 방법은 `-replace` 연산자를 사용하는 것입니다. 아래 예시를 확인해 보세요.

```PowerShell
# 숫자를 제거하려면
$string = "Hello123World"
$cleanString = $string -replace '\d', ''
$cleanString
# 출력: HelloWorld

# 특수 문자를 제거하려면
$string = "Hello!@#World"
$cleanString = $string -replace '[^\w]', ''
$cleanString
# 출력: HelloWorld

# 소문자만 제거하려면
$string = "HelloWorld"
$cleanString = $string -replace '[a-z]', ''
$cleanString
# 출력: HW
```

## Deep Dive (심화학습)
PowerShell에서는 `-replace` 연산자를 사용하여 정규 표현식(Regex)을 기반으로 문자열을 변형합니다. `-replace`는 .NET의 Regex 클래스를 내부적으로 사용하며, PowerShell 버전 2.0부터 사용 가능합니다.

대체 기법 중 하나는 `Select-String`을 사용하는 것이지만, 이는 주로 문자열 검색에 초점을 맞추고 있습니다. `-replace`는 텍스트 정제에 더욱 강력하고 효율적입니다.

성능 측면에서, `-replace`는 PowerShell 스크립트 내에서 빠르게 실행되며 대용량 텍스트 처리에서도 우수한 성능을 발휘합니다. 그러나 매우 큰 데이터를 다룰 때는 성능 차이를 고려해야 합니다.

## See Also (더 보기)
- [about_Comparison_Operators](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_Comparison_Operators?view=powershell-7.1)
- [Regular Expressions (.NET)](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)
- [PowerShell String Manipulation](https://ss64.com/ps/syntax-regex.html)

이 외에도 PowerShell 관련 정보는 [PowerShell 공식 문서](https://docs.microsoft.com/powershell/)를 참조하십시오.
