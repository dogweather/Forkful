---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:09:28.934969-07:00
description: "\uD504\uB85C\uADF8\uB798\uBC0D \uC5B8\uC5B4\uC5D0\uC11C \uD45C\uC900\
  \ \uC624\uB958(stderr)\uC5D0 \uC791\uC131\uD55C\uB2E4\uB294 \uAC83\uC740 \uC624\uB958\
  \ \uBA54\uC2DC\uC9C0\uC640 \uC9C4\uB2E8\uC744 \uD45C\uC900 \uCD9C\uB825(stdout)\uACFC\
  \ \uBD84\uB9AC\uB41C \uBCC4\uB3C4\uC758 \uC2A4\uD2B8\uB9BC\uC73C\uB85C \uBCF4\uB0B4\
  \uB294 \uAC83\uC744 \uC758\uBBF8\uD569\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\
  \uB294 \uC774\uB97C \uD1B5\uD574 \uC77C\uBC18 \uD504\uB85C\uADF8\uB7A8 \uCD9C\uB825\
  \uACFC \uC624\uB958 \uBA54\uC2DC\uC9C0\uB97C \uBD84\uB9AC\uD558\uC5EC \uB514\uBC84\
  \uAE45\uACFC \uB85C\uADF8 \uBD84\uC11D\uC744 \uBCF4\uB2E4 \uC27D\uAC8C \uB9CC\uB4ED\
  \uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:54.558094-06:00'
model: gpt-4-0125-preview
summary: "\uD504\uB85C\uADF8\uB798\uBC0D \uC5B8\uC5B4\uC5D0\uC11C \uD45C\uC900 \uC624\
  \uB958(stderr)\uC5D0 \uC791\uC131\uD55C\uB2E4\uB294 \uAC83\uC740 \uC624\uB958 \uBA54\
  \uC2DC\uC9C0\uC640 \uC9C4\uB2E8\uC744 \uD45C\uC900 \uCD9C\uB825(stdout)\uACFC \uBD84\
  \uB9AC\uB41C \uBCC4\uB3C4\uC758 \uC2A4\uD2B8\uB9BC\uC73C\uB85C \uBCF4\uB0B4\uB294\
  \ \uAC83\uC744 \uC758\uBBF8\uD569\uB2C8\uB2E4."
title: "\uD45C\uC900 \uC624\uB958\uC5D0 \uC4F0\uAE30"
weight: 25
---

## 방법:
Google Apps Script는 Google Apps 플랫폼 내에서 경량 애플리케이션 개발을 위한 스크립팅 언어로서, Node.js나 Python에서 찾을 수 있는 `console.error()`와 같은 표준 오류(stderr)에 작성을 위한 직접적인 내장 함수를 제공하지 않습니다. 그러나 Google Apps Script의 로깅 서비스나 사용자 정의 오류 처리를 사용하여 오류 출력을 관리하고 분리함으로써 이러한 동작을 모방할 수 있습니다.

### 예제: `Logger`를 사용한 오류 메시지
```javascript
function logError() {
  try {
    // 오류를 시뮬레이션
    const result = 1 / 0;
    if(!isFinite(result)) throw new Error("0으로 나누려고 시도함");
  } catch (e) {
    // 로그에 오류 메시지 작성
    Logger.log('오류: ' + e.message);
  }
}
```

`logError()`를 실행하면 Google Apps Script의 로그에 오류 메시지가 작성되며, `보기 > 로그`를 통해 이를 볼 수 있습니다. 이것은 정확히 stderr는 아니지만, 표준 출력과 오류 로그를 분리하는 비슷한 목적을 제공합니다.

### 고급 진단 로깅
보다 고급 디버깅 및 오류 로깅을 위해서는 Stackdriver 로깅, 현재는 Google Cloud의 Operations Suite로 알려져 있는 것을 사용할 수 있습니다.

```javascript
function advancedErrorLogging() {
  try {
    // 의도적으로 오류를 유발
    const obj = null;
    const result = obj.someProperty;
  } catch (e) {
    console.error('발생한 오류: ', e.toString());
  }
}
```

이렇게 하면 오류 메시지가 Stackdriver 로깅으로 직접 보내지며, 여기서 오류 레벨 로그로 관리됩니다. Stackdriver/Google Cloud의 Operations Suite 통합은 `Logger`보다 더 세밀하고 검색 가능한 로깅 솔루션을 제공한다는 점을 유의하십시오.

## 심층 분석
Google Apps Script에 전용 `stderr` 스트림이 없는 것은 클라우드 기반 스크립팅 언어로서의 그 특성과 기원을 반영하는 것으로, 전통적인 콘솔 또는 터미널 기반 출력(stdout 및 stderr)이 덜 관련이 있습니다. 역사적으로 Google Apps Script는 Google Apps 기능을 간단한 스크립트로 향상시키기 위해 설계되었으며, 보다 복잡한 프로그래밍 환경에서 사용 가능한 포괄적인 기능보다 사용의 용이성에 중점을 두었습니다.

그럼에도 불구하고, Google Apps Script가 보다 복잡한 애플리케이션 개발로 진화함에 따라 개발자들은 오류 처리 및 로깅을 위한 창의적인 접근 방법을 채택하게 되었으며, Logger와 Google Cloud의 Operations Suite를 통합하는 등 사용 가능한 서비스를 활용하고 있습니다. 이러한 방법들은 직접적인 stderr 구현은 아니지만, 클라우드 중심 환경에서 오류 관리 및 진단 로깅을 위한 강력한 대안을 제공합니다.

중요하게도 이러한 방법들은 Google Apps Script의 생태계 내에서 목적을 달성하면서도, 전통적인 프로그래밍 환경과 비교했을 때 플랫폼의 한계를 강조합니다. 자세하고 계층적인 오류 처리 전략이 필요한 개발자의 경우, 외부 로깅 서비스와 통합하거나 보다 전통적인 stderr 및 stdout 처리를 제공하는 Google Cloud Functions를 채택하는 것이 선호될 수 있습니다.
