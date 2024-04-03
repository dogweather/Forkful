---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:55:49.900099-07:00
description: "Google Apps \uC2A4\uD06C\uB9BD\uD2B8\uC5D0\uC11C\uB294 `Logger` \uD074\
  \uB798\uC2A4\uC640 `console.log()`\uC640 \uAC19\uC740 \uC5EC\uB7EC \uAC00\uC9C0\
  \ \uBC29\uBC95\uC744 \uC0AC\uC6A9\uD558\uC5EC \uB85C\uAE45\uC744 \uC218\uD589\uD560\
  \ \uC218 \uC788\uC2B5\uB2C8\uB2E4. Logger \uD074\uB798\uC2A4\uB294 \uC804\uD1B5\uC801\
  \uC778 \uBC29\uBC95\uC73C\uB85C \uAC04\uB2E8\uD55C \uB514\uBC84\uAE45 \uBC0F \uAC1C\
  \uBC1C \uBAA9\uC801\uC5D0 \uC801\uD569\uD569\uB2C8\uB2E4. \uCD5C\uADFC \uC5C5\uB370\
  \uC774\uD2B8\uC5D0\uC11C\uB294\u2026"
lastmod: '2024-03-13T22:44:54.541160-06:00'
model: gpt-4-0125-preview
summary: "Google Apps \uC2A4\uD06C\uB9BD\uD2B8\uC5D0\uC11C\uB294 `Logger` \uD074\uB798\
  \uC2A4\uC640 `console."
title: "\uB85C\uAE45"
weight: 17
---

## 방법:
Google Apps 스크립트에서는 `Logger` 클래스와 `console.log()`와 같은 여러 가지 방법을 사용하여 로깅을 수행할 수 있습니다. Logger 클래스는 전통적인 방법으로 간단한 디버깅 및 개발 목적에 적합합니다. 최근 업데이트에서는 `console.log()`가 Stackdriver Logging과의 더 큰 유연성과 통합을 제공하여 Google Cloud Platform에서 Apps 스크립트를 모니터링하기 위한 더 강력한 솔루션을 제공합니다.

**Logger 사용하기:**

```javascript
function logSample() {
  Logger.log('이것은 간단한 로그 메시지입니다');
  
  var value = 5;
  Logger.log('값은: %s', value); // 문자열 포맷팅
}

// 로그를 보려면:
// 1. logSample 함수를 실행합니다.
// 2. 보기 -> 로그
```

**Logger 샘플 출력:**

```
[22-04-20 10:00:00:000 PDT] 이것은 간단한 로그 메시지입니다
[22-04-20 10:00:00:001 PDT] 값은: 5
```

**console.log() 사용하기:**

```javascript
function consoleLogSample() {
  console.log('이 메시지는 Stackdriver Logging으로 갑니다');
  const obj = {name: 'Jane', role: 'Developer'};
  console.info('객체를 로깅합니다:', obj);
}

// 로그는 Google Cloud Platform (GCP) 콘솔에서 Stackdriver Logging 아래에서 볼 수 있습니다
```

**console.log() 샘플 출력:**

```
이 메시지는 Stackdriver Logging으로 갑니다
객체를 로깅합니다: {name: "Jane", role: "Developer"}
```

복잡한 애플리케이션을 위해 `console.log()`로 전환함으로써, 개발자들은 GCP에서 제공하는 강력한 필터와 도구를 사용하여 로그를 효과적으로 파싱하고 분석할 수 있으며, 이는 전통적인 Logger 클래스에서는 그렇게 직관적이지 않습니다.

## 심화:
Google Apps 스크립트에서의 로깅은 상당히 발전했습니다. 초기에는 `Logger` 클래스가 개발자들이 스크립트를 디버깅하기 위한 주요 방법이었습니다. 이 방법은 기본 스크립트에는 간단하고 충분하지만, 시간에 따른 로그 추세 분석이나 로그 검색과 같은 현대 클라우드 애플리케이션에 필요한 기능을 제공하지 못했습니다.

`console.log()`의 도입은 Google Cloud의 Stackdriver Logging(현재는 Operations Suite로 불림)과 Google Apps 스크립트 로깅을 통합함으로써 이 격차를 해소했습니다. 이는 로깅, 모니터링 및 애플리케이션 디버깅을 위한 중앙 집중식 플랫폼을 제공하며, 규모에 맞는 로깅 뿐만 아니라 실시간 로그 분석, 로그 기반 메트릭, 다른 Google Cloud 서비스와의 통합과 같은 고급 로그 관리 기능을 사용할 수 있게 했습니다.

`Logger`는 여전히 작은 스크립트에서 빠른 디버깅과 로깅을 위한 목적으로 사용되지만, `console.log()`를 사용하려는 방향 전환은 클라우드 네이티브 애플리케이션을 개발하는 데 있어 더 넓은 변화를 반영합니다. 이는 Google이 오늘날의 애플리케이션의 복잡성과 규모에 맞는 도구를 개발자에게 제공하려는 약속을 강조합니다. 그러나, 초보자들은 Google Cloud Platform 개념에 익숙해지는 것이 필요하다는 점과 약간 더 가파른 학습 곡선을 인지해야 합니다. 이러한 이동은 개발자가 클라우드 기능을 완전히 활용하려는 데에 유리하며, 클라우드 서비스와의 연계는 클라우드 컴퓨팅 시대에 견고하고 확장 가능한 로깅 메커니즘의 중요성을 강조하는 소프트웨어 개발의 더 넓은 추세의 일부입니다.
