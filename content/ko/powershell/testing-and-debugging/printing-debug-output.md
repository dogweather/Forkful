---
date: 2024-01-20 17:53:22.709705-07:00
description: "\uB514\uBC84\uADF8 \uCD9C\uB825\uC740 \uCF54\uB4DC\uAC00 \uC5B4\uB5BB\
  \uAC8C \uC2E4\uD589\uB418\uB294\uC9C0 \uBCFC \uC218 \uC788\uB3C4\uB85D \uB3C4\uC640\
  \uC90D\uB2C8\uB2E4. \uBB38\uC81C\uB97C \uCC3E\uACE0, \uD574\uACB0\uD558\uBA70, \uCF54\
  \uB4DC \uC774\uD574\uB97C \uB3D5\uAE30 \uC704\uD574 \uD504\uB85C\uADF8\uB798\uBA38\
  \uB4E4\uC774 \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.550151-06:00'
model: gpt-4-1106-preview
summary: "\uB514\uBC84\uADF8 \uCD9C\uB825\uC740 \uCF54\uB4DC\uAC00 \uC5B4\uB5BB\uAC8C\
  \ \uC2E4\uD589\uB418\uB294\uC9C0 \uBCFC \uC218 \uC788\uB3C4\uB85D \uB3C4\uC640\uC90D\
  \uB2C8\uB2E4."
title: "\uB514\uBC84\uADF8 \uCD9C\uB825\uC744 \uCC0D\uC5B4\uBCF4\uAE30"
weight: 33
---

## How to: (어떻게:)
PowerShell에서 디버그 메시지를 출력하는 기본 방법은 `Write-Host`, `Write-Output` 그리고 `Write-Debug` 명령어를 사용하는 것입니다.

```PowerShell
# 콘솔에 메시지를 출력합니다.
Write-Host "이 메시지가 콘솔에 보입니다."

# 스크립트의 출력 스트림으로 메시지를 보냅니다.
Write-Output "이 메시지도 출력됩니다."

# 디버그 메시지를 출력합니다. `-Debug` 플래그가 필요합니다.
Write-Debug "디버그 메시지입니다." -Debug
```

출력 예시:
```
이 메시지가 콘솔에 보입니다.
이 메시지도 출력됩니다.
DEBUG: 디버그 메시지입니다.
```

## Deep Dive (심층 분석)
디버그 출력은 초기 컴퓨터 시절부터 있었습니다. `Write-Host`는 데이터를 콘솔에 직접 출력하지만, 다른 명령어에 파이프할 수 없습니다. `Write-Output`을 사용하면 출력을 다른 명령어로 파이프할 수 있죠. `Write-Debug`는 기본적으로 비활성화되어 있으며, 스크립트에서 `-Debug` 플래그를 명시적으로 사용할 때만 작동합니다.

PowerShell의 디버그 기능을 사용하면 코드 실행 중 발생하는 변수의 값과 프로세스의 흐름을 상세히 볼 수 있어 유용합니다. 스크립트를 작성할 때 `-Verbose`와 `-Debug` 매개변수를 추가하면 디버그와 자세한 정보를 얻을 수 있습니다. 이렇게 하면 스크립트의 문제를 좀 더 쉽게 진단할 수 있습니다.

## See Also (함께 보기)
- [Write-Host](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/write-host?view=powershell-7.1)
- [Write-Output](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/write-output?view=powershell-7.1)
- [Write-Debug](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/write-debug?view=powershell-7.1)
- PowerShell 스크립팅 가이드: https://docs.microsoft.com/ko-kr/powershell/scripting/overview?view=powershell-7.1
- PowerShell 디버깅: https://docs.microsoft.com/ko-kr/powershell/scripting/learn/deep-dives/everything-about-psdebug?view=powershell-7.1
