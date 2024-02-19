---
aliases:
- /ko/powershell/concatenating-strings/
date: 2024-01-20 17:35:20.507995-07:00
description: "\uBB38\uC790\uC5F4 \uC5F0\uACB0(concatenating strings)\uC740 \uC11C\uB85C\
  \ \uB2E4\uB978 \uBB38\uC790\uC5F4\uC744 \uBD99\uC5EC \uD558\uB098\uB85C \uB9CC\uB4DC\
  \uB294 \uAC83\uC785\uB2C8\uB2E4. \uB370\uC774\uD130\uC640 \uD14D\uC2A4\uD2B8\uB97C\
  \ \uB3D9\uC801\uC73C\uB85C \uC870\uC791\uD558\uAC70\uB098 \uCD9C\uB825\uC744 \uD3EC\
  \uB9F7\uD558\uAE30 \uC704\uD574 \uAC1C\uBC1C\uC790\uB4E4\uC774 \uC790\uC8FC \uC0AC\
  \uC6A9\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: 2024-02-18 23:09:06.538294
model: gpt-4-1106-preview
summary: "\uBB38\uC790\uC5F4 \uC5F0\uACB0(concatenating strings)\uC740 \uC11C\uB85C\
  \ \uB2E4\uB978 \uBB38\uC790\uC5F4\uC744 \uBD99\uC5EC \uD558\uB098\uB85C \uB9CC\uB4DC\
  \uB294 \uAC83\uC785\uB2C8\uB2E4. \uB370\uC774\uD130\uC640 \uD14D\uC2A4\uD2B8\uB97C\
  \ \uB3D9\uC801\uC73C\uB85C \uC870\uC791\uD558\uAC70\uB098 \uCD9C\uB825\uC744 \uD3EC\
  \uB9F7\uD558\uAE30 \uC704\uD574 \uAC1C\uBC1C\uC790\uB4E4\uC774 \uC790\uC8FC \uC0AC\
  \uC6A9\uD569\uB2C8\uB2E4."
title: "\uBB38\uC790\uC5F4 \uC5F0\uACB0\uD558\uAE30"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
문자열 연결(concatenating strings)은 서로 다른 문자열을 붙여 하나로 만드는 것입니다. 데이터와 텍스트를 동적으로 조작하거나 출력을 포맷하기 위해 개발자들이 자주 사용합니다.

## How to: (방법)
```PowerShell
# '+' 연산자를 이용한 연결
$name = '세계'
$greeting = '안녕, ' + $name + '!'
echo $greeting
# 출력: 안녕, 세계!

# '-f' 포맷 연산자를 이용한 연결
$place = 'PowerShell'
$welcome = '어서 오세요. {0}에 도착하셨습니다.' -f $place
echo $welcome
# 출력: 어서 오세요. PowerShell에 도착하셨습니다.

# '$()' 서브 익스프레션을 이용한 연결
$first = 'Power'
$second = 'Shell'
$full = "$($first)$($second)은 강력합니다."
echo $full
# 출력: PowerShell은 강력합니다.
```

## Deep Dive (심층 분석)
초기에는 문자들의 배열이었던 문자열을 오늘날과 같은 편리한 형태로 만들기까지 오랜 시간이 걸렸습니다. 문자열 연결은 메모리 사용과 성능에 영향을 미칠 수 있기 때문에 고로 만들어진 방법입니다. PowerShell에서는 여러가지 방법(`+, +=, -f, $()` 등)으로 문자열을 연결할 수 있지만 각 방법은 성능과 사용 상황에 따라 다르게 적합합니다.

예를 들어, '+' 연산자는 간단한 시나리오에 적합하지만 많은 수의 문자열을 반복적으로 연결할 때는 성능적으로 비효율적일 수 있습니다. 대규모 연결 작업에는 .NET의 `StringBuilder` 클래스를 활용할 수도 있습니다.

부가적으로, `-f` 연산자는 포맷을 지정하며 여러 값들을 묶는데 적합하며, `$()` 서브 익스프레션은 복잡한 변수 결합이나 커맨드 렛의 결과를 문자열과 결합할 때 유용합니다.

## See Also (참고자료)

- [About Join](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_join)
- [StringBuilder 클래스에 대한 MSDN 문서](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder)
