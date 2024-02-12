---
title:                "텍스트 파일 읽기"
aliases:
- ko/swift/reading-a-text-file.md
date:                  2024-01-20T17:55:10.575496-07:00
model:                 gpt-4-1106-preview
simple_title:         "텍스트 파일 읽기"

tag:                  "Files and I/O"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/swift/reading-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
텍스트 파일 읽기는 디스크에 저장된 텍스트 데이터를 읽고 Swift 프로그램에서 사용하는 것입니다. 파일에서 설정, 사용자 데이터, 또는 대량의 텍스트를 읽어야 할 때 프로그래머들이 사용합니다.

## How to: (어떻게:)
```Swift
import Foundation

// 파일 URL 지정
guard let fileURL = Bundle.main.url(forResource: "sample", withExtension: "txt") else {
    fatalError("File not found.")
}

do {
    // 텍스트 파일 읽기
    let contents = try String(contentsOf: fileURL, encoding: .utf8)
    print(contents)
} catch {
    // 에러 처리
    print("File read error: \(error)")
}
```
```
Sample Output:
이것은 샘플 텍스트 파일입니다.
여러 줄에 걸쳐 텍스트가 있을 수 있어요.
```

## Deep Dive (심화 학습)
Swift에서 텍스트 파일을 읽는 기능은 초기 Objective-C와 Cocoa 터치 프레임워크에서 유래합니다. `String(contentsOf:encoding:)` 메소드는 Swift의 String 타입에 추가되었습니다. 대안으로는 `NSData`를 사용하거나, 낮은 수준의 파일 스트림을 직접 다루는 방법이 있습니다. 구현 세부사항으로는 문자 인코딩 문제와 큰 파일을 읽을 때의 메모리 관리가 중요합니다.

## See Also (참고자료)
- [Swift String Documentation](https://developer.apple.com/documentation/swift/string)
- [Swift Book (The Swift Programming Language)](https://docs.swift.org/swift-book/)
