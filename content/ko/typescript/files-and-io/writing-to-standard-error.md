---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:38.830702-07:00
description: "TypeScript\uC5D0\uC11C \uD45C\uC900 \uC624\uB958(stderr)\uC5D0 \uC4F0\
  \uAE30\uB294 \uD658\uACBD\uC758 \uC624\uB958 \uCD9C\uB825 \uC2A4\uD2B8\uB9BC(\uC608\
  : node.js \uB610\uB294 \uC6F9 \uBE0C\uB77C\uC6B0\uC800\uC758 \uCF58\uC194)\uC73C\
  \uB85C \uC9C1\uC811 \uC624\uB958 \uBA54\uC2DC\uC9C0\uB098 \uB85C\uADF8\uB97C \uBCF4\
  \uB0B4\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4. \uC774\uB294 \uD504\uB85C\uADF8\uB7A8\
  \ \uB370\uC774\uD130\uC5D0 \uC77C\uBC18\uC801\uC73C\uB85C \uC0AC\uC6A9\uB418\uB294\
  \ \uD45C\uC900 \uCD9C\uB825(stdout)\uACFC \uAC04\uC12D\uD558\uC9C0 \uC54A\uACE0\
  \ \uBB38\uC81C\uB97C\u2026"
lastmod: '2024-03-13T22:44:54.876619-06:00'
model: gpt-4-0125-preview
summary: "TypeScript\uC5D0\uC11C \uD45C\uC900 \uC624\uB958(stderr)\uC5D0 \uC4F0\uAE30\
  \uB294 \uD658\uACBD\uC758 \uC624\uB958 \uCD9C\uB825 \uC2A4\uD2B8\uB9BC(\uC608: node."
title: "\uD45C\uC900 \uC5D0\uB7EC\uC5D0 \uC4F0\uAE30"
weight: 25
---

## 방법:
TypeScript는 JavaScript의 상위 집합으로써, stderr에 쓰기 위해 기본적인 JS 런타임 환경(Node.js 같은)에 의존합니다. 직접 실행하는 방법은 다음과 같습니다:

```typescript
console.error("This is an error message.");
```

stderr로의 샘플 출력:
```
This is an error message.
```

Node.js 환경에서는 보다 저수준 쓰기를 위해 `process.stderr.write()` 메소드를 사용할 수도 있습니다:

```typescript
process.stderr.write("Low level error message.\n");
```

stderr로의 샘플 출력:
```
Low level error message.
```

더 구조화된 오류 로깅을 위해서는 `winston`이나 `pino`와 같은 인기 있는 서드파티 라이브러리를 사용할 수 있습니다. `winston`을 사용하여 오류를 로깅하는 방법은 다음과 같습니다:

먼저 `winston`을 설치하십시오:

```bash
npm install winston
```

그런 다음 TypeScript 파일에서 사용하십시오:

```typescript
import * as winston from 'winston';

const logger = winston.createLogger({
  levels: winston.config.syslog.levels,
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'error.log', level: 'error' })
  ],
});

logger.error('Error logged using winston.');
```

이렇게 하면 오류가 콘솔과 `error.log`라는 이름의 파일에 모두 기록됩니다. 파일에 쓸 때는 파일 권한과 롤오버를 관리하여 디스크 공간 사용과 관련된 문제를 방지하는 것이 중요합니다.
