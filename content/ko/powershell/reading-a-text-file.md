---
title:                "텍스트 파일 읽기"
date:                  2024-01-20T17:55:08.945475-07:00
model:                 gpt-4-1106-preview
simple_title:         "텍스트 파일 읽기"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Files and I/O"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/powershell/reading-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
텍스트 파일을 읽는 것은 파일 안에 있는 글자들을 불러오는 거예요. 프로그래머들이 이걸 하려는 이유? 데이터를 처리하거나, 설정을 읽거나, 간단한 입력을 받기 위해서죠.

## How to: (어떻게:)
```PowerShell
# 파일 전체를 한번에 읽기
Get-Content -Path "example.txt"

# 각 줄을 개별적으로 처리
Get-Content -Path "example.txt" | ForEach-Object {
  # 여기서 $_ 변수는 현재 줄을 나타냅니다.
  Write-Output "Reading line: $_"
}

# 출력 예시
Reading line: 첫 번째 줄입니다.
Reading line: 두 번째 줄입니다.
...
```

## Deep Dive (심화 학습)
파워셸에서 텍스트 파일을 읽는 것은 스크립트 언어가 등장한 초기부터 있었던 기능입니다. `Get-Content`는 가장 일반적인 방법인데, 이 명령어는 파일을 한 번에 메모리로 읽어들이기 때문에 큰 파일을 다룰 때는 성능 문제가 발생할 수도 있어요. 대안으로 `[System.IO.File]::ReadLines()` 같은 .NET 메서드를 사용할 수도 있고, `StreamReader` 객체를 통해 더 세밀한 제어가 가능합니다.

```PowerShell
# .NET의 ReadLines 활용
[System.IO.File]::ReadLines("example.txt")

# StreamReader 사용 예
$reader = [System.IO.StreamReader]::new("example.txt")
while($line = $reader.ReadLine()){
  Write-Output "Reading line: $line"
}
$reader.Close()
```

이런 방식들은 파일 크기가 큰 경우나 메모리 사용을 제한해야 할 때 유리합니다. 스트림을 통해 한 줄씩 읽기 때문에 전체 파일을 메모리에 로드할 필요가 없죠.

## See Also (관련 링크)
- 공식 PowerShell 문서에서 Get-Content에 대해 자세히 알아보기: [Get-Content](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.2)
- .NET의 파일 시스템 메서드에 대한 설명: [System.IO Namespace](https://docs.microsoft.com/en-us/dotnet/api/system.io?view=net-6.0)
- StackOverflow의 PowerShell 관련 질문들: [PowerShell Questions](https://stackoverflow.com/questions/tagged/powershell)
