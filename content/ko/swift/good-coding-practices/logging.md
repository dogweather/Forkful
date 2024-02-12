---
title:                "로깅"
aliases:
- /ko/swift/logging/
date:                  2024-01-26T01:08:13.314779-07:00
model:                 gpt-4-1106-preview
simple_title:         "로깅"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/swift/logging.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?
로그 기록은 어플리케이션의 동작, 오류 및 중요한 정보를 파일이나 데이터베이스와 같은 지속적인 매체에 기록하는 과정입니다. 프로그래머들은 어플리케이션의 건강과 성능을 추적하고, 문제를 디버깅하며, 프로덕션 환경에서 무슨 일이 일어나고 있는지를 주시하기 위해 로깅을 합니다.

## 어떻게:
Swift 에서는 print 문을 사용해 콘솔에 로그를 기록하거나, Apple 플랫폼의 통합 로깅 시스템에 연결하는 더 유연한 `os.log` API를 사용할 수 있습니다.

```Swift
import os.log

let logger = OSLog(subsystem: "com.yourapp.domain", category: "network")

func fetchData() {
    // 간단한 print 문
    print("Fetch 시작됨")
    
    // os.log를 사용하여 정보 수준 이벤트 로깅
    os_log(.info, log: logger, "API 에서 데이터 가져오기.")
    
    do {
        let data = try performNetworkRequest()
        // 디버그 수준 이벤트 로깅
        os_log(.debug, log: logger, "데이터 수신됨: %@", data.description)
    } catch {
        // 오류 수준 이벤트 로깅
        os_log(.error, log: logger, "데이터를 가져오는 데 실패함: %@", error.localizedDescription)
    }
}

func performNetworkRequest() throws -> Data {
    // 네트워크 요청 시뮬레이션
    return Data()
}
```

콘솔에 나타나는 샘플 출력은 이런 모습일 것입니다:

```
Fetch 시작됨
API 에서 데이터 가져오기.
데이터 수신됨: 일부 데이터 바이트...
```

오류의 경우에는 다음과 같습니다:

```
데이터를 가져오는 데 실패함: 인터넷 연결이 오프라인 상태로 보임.
```

## 심층 분석
iOS 10과 macOS Sierra에서 소개된 통합 로깅 시스템으로 Swift 에서의 로깅은 새로운 힘과 효율성을 갖게 되었습니다. 콘솔로 바로 가는 `print` 문과 달리, 이 시스템은 활동 기반으로, 중요성과 디버그 또는 릴리스 빌드 여부에 따라 로그 메시지를 필터링할 수 있습니다.

역사적 맥락은 iOS와 macOS에서 기본적인 print 문에서부터 Instruments 앱과 Console과 통합되고, 로그를 분석하는 정교한 방법을 제공하는 종합적인 도구로의 로깅 진화를 설명합니다.

Swift 내의 로깅 대체 방법으로는, 통합 로깅 시스템을 위한 매크로 계층을 제공하는 CocoaLumberjack과 같은 서드파티 라이브러리가 있습니다. 이는 로그 포맷팅, 파일 관리 및 성능 옵션에 대한 향상된 제어력을 제공합니다.

마지막으로, OSLog는 효율적일 뿐만 아니라 개인 정보를 로깅할 때 은폐할 수 있는 개인 정보 보호를 고려하여 설계되었습니다. 오류, 정보, 디버그 수준의 로그를 분류하여 문제 해결을 위한 다양한 세분성을 제공합니다.

## 참고자료
- [Apple 의 통합 로깅 문서](https://developer.apple.com/documentation/os/logging)
- [Ray Wenderlich의 로깅 튜토리얼](https://www.raywenderlich.com/605079-logging-in-swift-oslog)
- [CocoaLumberjack GitHub 저장소](https://github.com/CocoaLumberjack/CocoaLumberjack)
