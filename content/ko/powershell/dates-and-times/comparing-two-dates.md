---
date: 2024-01-20 17:33:35.702869-07:00
description: "\uB0A0\uC9DC \uBE44\uAD50\uB294 \uB450 \uB0A0\uC9DC\uAC00 \uAC19\uC740\
  \uC9C0, \uC5B4\uB290 \uAC83\uC774 \uB354 \uC774\uC804\uC774\uB098 \uB354 \uCD5C\uC2E0\
  \uC778\uC9C0\uB97C \uD310\uB2E8\uD558\uB294 \uAC83\uC785\uB2C8\uB2E4. \uD504\uB85C\
  \uADF8\uB798\uBA38\uB294 \uAE30\uD55C \uAC80\uC0AC, \uC774\uBCA4\uD2B8 \uC21C\uC11C\
  \ \uD30C\uC545, \uC2DC\uAC04 \uAC04\uACA9 \uCE21\uC815 \uB4F1\uC744 \uC704\uD574\
  \ \uB0A0\uC9DC\uB97C \uBE44\uAD50\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.565418-06:00'
model: gpt-4-1106-preview
summary: "\uB0A0\uC9DC \uBE44\uAD50\uB294 \uB450 \uB0A0\uC9DC\uAC00 \uAC19\uC740\uC9C0\
  , \uC5B4\uB290 \uAC83\uC774 \uB354 \uC774\uC804\uC774\uB098 \uB354 \uCD5C\uC2E0\uC778\
  \uC9C0\uB97C \uD310\uB2E8\uD558\uB294 \uAC83\uC785\uB2C8\uB2E4."
title: "\uB450 \uB0A0\uC9DC \uBE44\uAD50\uD558\uAE30"
weight: 27
---

## How to: (방법:)
```PowerShell
# 예제 1: 날짜 비교 - 같음
$date1 = Get-Date '2023-03-15'
$date2 = Get-Date '2023-03-15'
$date1 -eq $date2  # 출력: True

# 예제 2: 날짜 비교 - 더 이전
$date3 = Get-Date '2021-06-10'
$date1 -gt $date3  # 출력: True

# 예제 3: 날짜 차이 계산
$diff = $date1 - $date3
$diff.Days  # 출력: 644
```

## Deep Dive (심층 탐구)
PowerShell에서 날짜 비교는 `Get-Date`, `-eq`, `-gt`, `-lt` 와 같은 Cmdlet과 연산자를 사용합니다. 이 기능은 .NET의 DateTime 객체를 기반으로 합니다. 초기 버전의 PowerShell에는 이렇게 간결하고 직관적인 방식이 없었지만, 버전이 업데이트되면서 개선되었습니다.

다른 방법으로 `[datetime]` 형 변환을 사용한 비교 또는 `.Compare()` 메소드를 사용할 수도 있습니다. `.Compare()`는 두 날짜를 비교하여 전자가 후자보다 이전이면 음수를, 같으면 0을, 늦으면 양수를 반환합니다.

비교를 구현할 때는 시간대를 고려해야 할 수 있습니다. 날짜가 서로 다른 시간대에서 온 것이라면, UTC로 변환하여 비교하는 것이 정확합니다.

## See Also (더 보기)
- [DateTime.Compare 메소드](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.compare?view=netframework-4.8)
- [PowerShell about_Comparison_Operators](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7.1)
