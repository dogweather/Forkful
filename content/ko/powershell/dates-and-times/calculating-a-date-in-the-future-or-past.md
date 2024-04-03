---
date: 2024-01-20 17:32:00.688872-07:00
description: "\uB0A0\uC9DC \uACC4\uC0B0\uC740 \uBBF8\uB798\uB098 \uACFC\uAC70\uC758\
  \ \uD2B9\uC815 \uB0A0\uC9DC\uB97C \uAD6C\uD558\uB294 \uAC83\uC785\uB2C8\uB2E4. \uC2A4\
  \uCF00\uC904\uB9C1, \uB9CC\uAE30\uC77C \uD655\uC778, \uC774\uBCA4\uD2B8 \uC608\uC815\
  \uC77C \uC124\uC815 \uB4F1\uC744 \uC704\uD574 \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\
  \uC774 \uC774\uB97C \uC218\uD589\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.566568-06:00'
model: gpt-4-1106-preview
summary: "\uB0A0\uC9DC \uACC4\uC0B0\uC740 \uBBF8\uB798\uB098 \uACFC\uAC70\uC758 \uD2B9\
  \uC815 \uB0A0\uC9DC\uB97C \uAD6C\uD558\uB294 \uAC83\uC785\uB2C8\uB2E4."
title: "\uBBF8\uB798\uB098 \uACFC\uAC70\uC758 \uB0A0\uC9DC \uACC4\uC0B0\uD558\uAE30"
weight: 26
---

## How to: (방법)
```PowerShell
# 미래 날짜 계산하기
$daysToAdd = 30
$futureDate = (Get-Date).AddDays($daysToAdd)
Write-Output "30일 후 날짜: $futureDate"

# 출력 예시: 30일 후 날짜: Friday, April 14, 2023 5:52:48 PM

# 과거 날짜 계산하기
$daysToSubtract = 10
$pastDate = (Get-Date).AddDays(-$daysToSubtract)
Write-Output "10일 전 날짜: $pastDate"

# 출력 예시: 10일 전 날짜: Tuesday, March 21, 2023 5:52:48 PM
```

## Deep Dive (깊이 있는 정보)
PowerShell에서 날짜 계산은 .NET의 DateTime 객체를 사용하여 이루어집니다. 간단한 .AddDays() 메서드 호출로 날짜를 추가하거나 빼는 것이 가능합니다. 이 방법은 예정된 작업을 계획하거나 로그 파일을 처리할 때 유용합니다.

AddDays() 외에도 .AddHours(), .AddMinutes(), .AddMonths() 등 다양한 메서드가 있어 세밀한 날짜 조정이 가능합니다. PowerShell 1.0부터 사용 가능했으며, 후에 나온 버전들에서 기능이 더해지고 성능이 개선되었습니다.

.NET 대안으로 DateTimeOffset이 있지만, 특정 시간대와 관련된 계산이 필요할 때만 사용됩니다. PowerShell 5.1 이후 버전에서는 "New-TimeSpan" cmdlet을 사용하여 날짜 범위를 계산할 수도 있습니다.

내장된 날짜 계산 기능은 강력하며, 대부분의 경우 별도의 모듈을 설치할 필요가 없습니다. 그러나 복잡한 날짜 계산은 때때로 추가적인 라이브러리나 모듈의 도움을 필요로 할 수 있습니다.

## See Also (더 보기)
- 공식 PowerShell 문서의 날짜와 시간에 관한 섹션:
  [PowerShell Datetime](https://docs.microsoft.com/en-us/powershell/scripting/learn/deep-dives/everything-about-datetime?view=powershell-7.2)

- .NET DateTime 클래스:
  [.NET DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime?view=net-6.0)

- PowerShell Gallery에서 날짜 관련 모듈 검색하기:
  [PowerShell Gallery](https://www.powershellgallery.com/)
